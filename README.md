# Projeto Final - Fundamentos de Redes de Computadores

### Informações do Projeto
* **Instituição:** Instituto Federal de Alagoas (IFAL) - Campus Maceió
* **Disciplina:** Fundamentos de Redes de Computadores
* **Professor:** Alaelson de Castro Jatoba Neto
* **Curso:** Bacharelado em Sistemas de Informação (BSI)
* **Turma:** bsi-26-1 (2026.1)
* **Grupo:** Grupo 6
* **Repositório:** https://github.com/maryanneoliveira/VitualBox_ProjetoFinal
---

## 1. Visão Geral

Este documento descreve o passo-a-passo para implementar um ambiente de rede virtualizado com **8 máquinas virtuais Ubuntu Server** para a disciplina de Fundamentos de Redes de Computadores. O projeto consiste em criar uma infraestrutura de rede com configuração estática de IPs, hostnames, usuários e testes de conectividade entre os servidores.

O laboratório prático consiste na simulação de uma infraestrutura de rede local dividida em sub-redes. Cada ativo da rede foi configurado com IP estático, nome de domínio totalmente qualificado (FQDN), serviço de resolução de nomes local e permissão de gerência remota via protocolo SSH. A finalidade didática desta atividade é aplicar, de forma integrada, os fundamentos de endereçamento IPv4, divisão de sub-redes (subnetting) com máscara `/28`, padrões de nomenclatura de hosts, mapeamento de DNS local e administração remota segura.

## 🗂️ Organização da Documentação

| Documento / Diretório | Conteúdo e Descrição |
| :--- | :--- |
| **`README.md`** (este arquivo) | Visão geral do projeto, integrantes do Grupo 6, tabelas consolidadas de hardware, mapeamento de IPs, nomenclatura padrão, topologia e estrutura geral do repositório no GitHub. |
| **`docs/tutorial.md`** | Roteiro técnico detalhado documentando os passos de instalação e parametrização do sistema operacional de cada VM. |
| **`docs/teste_ping.md`** | Evidências, logs e relatórios dos testes de conectividade local (`ping`) realizados entre os hosts da sub-rede. |
| **`docs/teste_ssh.md`** | Relatório de validação e logs comprovando o correto funcionamento do acesso remoto seguro (`ssh`) nas instâncias. |
| **`GoogleDrive/`** | Diretório contendo os arquivos individuais de especificação de cada máquina (Fichas Técnicas) e as orientações/links para download dos arquivos de exportação `.ova`. |

---

## 2. Integrantes do Grupo

| Nome Completo | Usuário (login) | E-mail | GitHub |
| :--- | :--- | :--- | :--- |
| Alex Rodrigo Lima de Arruda Santos| `alex.rodrigo` | arlas1@aluno.ifal.edu.br | [@arlasx](https://github.com/arlasx) |
| Bruno Gabriel dos Santos Lima | `bruno.gabriel ` | bgsl2@aluno.ifal.edu.br | [@bgsl2](https://github.com/bgsl2) |
| João Guilherme Amaro da Silva Gomes | `joao.guilherme` | jgasg1@aluno.ifal.edu.br | [@Joao-Guilhere-Amaro](https://github.com/Joao-Guilhere-Amaro) |
| Maryane Santos de Oliveira | `maryane.oliveira` | mso12@aluno.ifal.edu.br | [@maryanneoliveira](https://github.com/maryanneoliveira) |

---

## 3. Topologia da Rede

A topologia adotada segue o diagrama de referência fornecido na especificação do projeto. As 8 VMs pertencem à mesma sub-rede **192.168.26.80**, comunicando-se em camada de enlace por meio de uma rede interna virtual do hipervisor (VirtualBox).

---

## 4. Configuração de Hardware das VMs

Todas as VMs foram criadas com configuração idêntica, dimensionada para o papel de servidor leve (Ubuntu Server, sem ambiente gráfico):

| Recurso | Especificação | Justificativa |
| :--- | :--- | :--- |
| **Memória RAM** | 2048 MB (2 GB) | Adequado para o Ubuntu Server em modo texto e os serviços do projeto (SSH), permitindo operações mais fluidas. |
| **Processador** | 2 vCPU (2 núcleos) | Garante melhor desempenho em operações do sistema e processamento de múltiplas conexões SSH simultâneas. |
| **Disco** | 10 GB | Garante melhor funcionamento da maquina no virtual box |
| **Sistema Operacional** | Ubuntu Server | Distribuição voltada a servidores, sem interface gráfica, alinhada ao objetivo do projeto. |
| **Interface de rede** | 1 adaptador | Configurado como **Rede Interna** do hipervisor para conectar as VMs na mesma sub-rede isolada. |

---

## 5. Endereçamento IP

### 5.1. Organização do Subnetting

A turma `bsi-26-1` utiliza a rede principal `192.168.26.0/24`. Essa rede é dividida em sub-redes de máscara `/28` (`255.255.255.240`), o que produz blocos de 16 endereços cada ($2^4 = 16$), sendo **14 endereços úteis** por bloco (descontados os endereços de rede e de broadcast). 

A atribuição por grupo ocorre de forma sequencial:

| Grupo | Faixa IP (/28) | Endereço de Rede | Endereço de Broadcast |
| :--- | :--- | :--- | :--- |
| Grupo 1 | 192.168.26.0 – 192.168.26.15 | 192.168.26.0 | 192.168.26.15 |
| Grupo 2 | 192.168.26.16 – 192.168.26.31 | 192.168.26.16 | 192.168.26.31 |
| Grupo 3 | 192.168.26.32 – 192.168.26.47 | 192.168.26.32 | 192.168.26.47 |
| Grupo 4 | 192.168.26.48 – 192.168.26.63 | 192.168.26.48 | 192.168.26.63 |
| Grupo 5 | 192.168.26.64 – 192.168.26.79 | 192.168.26.64 | 192.168.26.79 |
| **Grupo 6 (Este)** | **192.168.26.80 – 192.168.26.95** | **192.168.26.80** | **192.168.26.95** |

**Parâmetros Técnicos da Sub-rede (Grupo 6)**
* **Máscara Decimal:** `255.255.255.240`
* **Primeiro IP Válido (Hosts):** `192.168.26.81`
* **Último IP Válido (Hosts):** `192.168.26.94`
* **Quantidade de IPs Úteis:** 14 endereços disponíveis para as 8 máquinas virtuais.

### 5.2. Mapeamento de Hosts (FQDN) e Endereçamento

| VM | Hostname | Interface | FQDN (Nome de Domínio Completo) | Endereço IP | Máscara de Rede |
| :---: | :---: | :---: | :--- | :---: | :---: |
| **VM 1** | `monica` | `enp0s3` | `monica.grupo6.bsi-26-1.maceio.lab` | `192.168.26.81` | `255.255.255.240` |
| **VM 2** | `wladia` | `enp0s3` | `wladia.grupo6.bsi-26-1.maceio.lab` | `192.168.26.82` | `255.255.255.240` |
| **VM 3** | `fabrisia` | `enp0s3` | `fabrisia.grupo6.bsi-26-1.maceio.lab` | `192.168.26.83` | `255.255.255.240` |
| **VM 4** | `alaelson` | `enp0s3` | `alaelson.grupo6.bsi-26-1.maceio.lab` | `192.168.26.84` | `255.255.255.240` |
| **VM 5** | `tarcio` | `enp0s3` | `tarcio.grupo6.bsi-26-1.maceio.lab` | `192.168.26.85` | `255.255.255.240` |
| **VM 6** | `kenji` | `enp0s3` | `kenji.grupo6.bsi-26-1.maceio.lab` | `192.168.26.86` | `255.255.255.240` |
| **VM 7** | `frederico` | `enp0s3` | `frederico.grupo6.bsi-26-1.maceio.lab` | `192.168.26.87` | `255.255.255.240` |
| **VM 8** | `ricardo` | `enp0s3` | `ricardo.grupo6.bsi-26-1.maceio.lab` | `192.168.26.88` | `255.255.255.240` |
---
