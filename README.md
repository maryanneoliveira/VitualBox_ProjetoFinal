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

Olaboratório prático consiste na simulação de uma infraestrutura de rede local dividida em sub-redes. Cada ativo da rede foi configurado com IP estático, nome de domínio totalmente qualificado (FQDN), serviço de resolução de nomes local e permissão de gerência remota via protocolo SSH. A finalidade didática desta atividade é aplicar, de forma integrada, os fundamentos de endereçamento IPv4, divisão de sub-redes (subnetting) com máscara `/28`, padrões de nomenclatura de hosts, mapeamento de DNS local e administração remota segura.

### Organização da Documentação

| Documento | Conteúdo |
| :--- | :--- |
| **`README.md`** (este arquivo) | Visão geral, integrantes, tabelas de hardware, IPs e nomenclatura, topologia e estrutura do repositório no github. |
| **`tutorial.md`** | Tutorial técnico detalhado de instalação e configuração de cada VM. |
| **`imagens.md`** | Resultados do processo de criação do ambiente virtual. |
| **`Ficha_gp6.md`** | Ficha individual de cada VM (hostname, IP, responsável). |
| **Google Drive** (Pasta externa) | Arquivos das VMs nos formatos `.ova` para download. |

---

## 2. Integrantes do Grupo

| Nome Completo | Usuário (login) | E-mail | GitHub | Máquinas sob Responsabilidade |
| :--- | :--- | :--- | :--- | :--- |
| Andrezza Abreu de Magalhães | `andrezza.magalhaes` | aam6@aluno.ifal.edu.br | [@dzzabreu](https://github.com/dzzabreu) | G4-PC1-VM1, G4-PC1-VM2 |
| Isaque de Souza Braga | `isaque.braga` | isb15@aluno.ifal.edu.br | [@isaquebraga](https://github.com/isaquebraga) | G4-PC2-VM1, G4-PC2-VM2 |
| Maria Luisa Alaquoke F. dos Santos | `maria.santos` | mlafs2@aluno.ifal.edu.br | [@quokequack](https://github.com/quokequack) | G4-PC3-VM1, G4-PC3-VM2 |
| Renilson José da Silva Santos | `renilson.santos` | rjss7@aluno.ifal.edu.br | [@renilsou](https://github.com/renilsou) | G4-PC4-VM1, G4-PC4-VM2 |

> 📌 **Nota de Administração:** Cada integrante é o administrador (membro do grupo `sudo`) das duas máquinas sob sua responsabilidade. Ainda assim, em todas as VMs são criados os usuários de todos os integrantes, conforme exigência do projeto.

---

## 3. Topologia da Rede

A topologia adotada segue o diagrama de referência fornecido na especificação do projeto. As 8 VMs pertencem à mesma sub-rede **192.168.26.48/28**, comunicando-se em camada de enlace por meio de uma rede interna virtual do hipervisor (VirtualBox).

---

## 4. Configuração de Hardware das VMs

Todas as VMs foram criadas com configuração idêntica, dimensionada para o papel de servidor leve (Ubuntu Server, sem ambiente gráfico):

| Recurso | Especificação | Justificativa |
| :--- | :--- | :--- |
| **Memória RAM** | 2048 MB (2 GB) | Adequado para o Ubuntu Server em modo texto e os serviços do projeto (SSH), permitindo operações mais fluidas. |
| **Processador** | 2 vCPU (2 núcleos) | Garante melhor desempenho em operações do sistema e processamento de múltiplas conexões SSH simultâneas. |
| **Disco** | 32 GB | Acomoda o sistema base, pacotes adicionais (idioma, SSH) e margem para logs. |
| **Sistema Operacional** | Ubuntu Server | Distribuição voltada a servidores, sem interface gráfica, alinhada ao objetivo do projeto. |
| **Interface de rede** | 1 adaptador | Configurado como **Rede Interna** do hipervisor para conectar as VMs na mesma sub-rede isolada. |

---

## 5. Endereçamento IP

### 5.1. Fundamentação do Subnetting

A turma `bsi-26-1` utiliza a rede principal `192.168.26.0/24`. Essa rede é dividida em sub-redes de máscara `/28` (`255.255.255.240`), o que produz blocos de 16 endereços cada ($2^4 = 16$), sendo **14 endereços úteis** por bloco (descontados os endereços de rede e de broadcast). 

A atribuição por grupo ocorre de forma sequencial:

| Grupo | Faixa IP (/28) | Endereço de Rede | Endereço de Broadcast |
| :--- | :--- | :--- | :--- |
| Grupo 1 | 192.168.26.0 – 192.168.26.15 | 192.168.26.0 | 192.168.26.15 |
| Grupo 2 | 192.168.26.16 – 192.168.26.31 | 192.168.26.16 | 192.168.26.31 |
| Grupo 3 | 192.168.26.32 – 192.168.26.47 | 192.168.26.32 | 192.168.26.47 |
| **Grupo 4 (Este)** | **192.168.26.48 – 192.168.26.63** | **192.168.26.48** | **192.168.26.63** |

**Resumo da Sub-rede do Grupo 4:**
* **Endereço de rede:** `192.168.26.48`
* **Primeiro endereço útil:** `192.168.26.49`
* **Último endereço útil:** `192.168.26.62`
* **Endereço de broadcast:** `192.168.26.63`
* **Máscara de sub-rede:** `255.255.255.240` (`/28`)
* **Hosts úteis disponíveis:** 14 (As 8 VMs ocupam os IPs `.49` ao `.56`, restando do `.57` ao `.62` livres)

### 5.2. Tabela de Endereços das VMs

| VM | Endereço IP | Máscara |
| :--- | :--- | :--- |
| G4-PC1-VM1 | `192.168.26.49` | `/28` (`255.255.255.240`) |
| G4-PC1-VM2 | `192.168.26.50` | `/28` |
| G4-PC2-VM1 | `192.168.26.51` | `/28` |
| G4-PC2-VM2 | `192.168.26.52` | `/28` |
| G4-PC3-VM1 | `192.168.26.53` | `/28` |
| G4-PC3-VM2 | `192.168.26.54` | `/28` |
| G4-PC4-VM1 | `192.168.26.55` | `/28` |
| G4-PC4-VM2 | `192.168.26.56` | `/28` |

---

## 6. Nomenclatura e Domínio (FQDN)

O domínio do grupo segue o formato estrito definido pela disciplina. O nome curto (*hostname*) é utilizado como apelido (*alias*) na resolução local, e o FQDN é o nome canônico do host.

| VM | Hostname | FQDN | Apelido (Alias) | IP |
| :--- | :--- | :--- | :--- | :--- |
| G4-PC1-VM1 | `g4-pc1-vm1` | `g4-pc1-vm1.grupo4-bsi-26-1.maceio.lab` | `g4-pc1-vm1` | `192.168.26.49` |
| G4-PC1-VM2 | `g4-pc1-vm2` | `g4-pc1-vm2.grupo4-bsi-26-1.maceio.lab` | `g4-pc1-vm2` | `192.168.26.50` |
| G4-PC2-VM1 | `g4-pc2-vm1` | `g4-pc2-vm1.grupo4-bsi-26-1.maceio.lab` | `g4-pc2-vm1` | `192.168.26.51` |
| G4-PC2-VM2 | `g4-pc2-vm2` | `g4-pc2-vm2.grupo4-bsi-26-1.maceio.lab` | `g4-pc2-vm2` | `192.168.26.52` |
| G4-PC3-VM1 | `g4-pc3-vm1` | `g4-pc3-vm1.grupo4-bsi-26-1.maceio.lab` | `g4-pc3-vm1` | `192.168.26.53` |
| G4-PC3-VM2 | `g4-pc3-vm2` | `g4-pc3-vm2.grupo4-bsi-26-1.maceio.lab` | `g4-pc3-vm2` | `192.168.26.54` |
| G4-PC4-VM1 | `g4-pc4-vm1` | `g4-pc4-vm1.grupo4-bsi-26-1.maceio.lab` | `g4-pc4-vm1` | `192.168.26.55` |
| G4-PC4-VM2 | `g4-pc4-vm2` | `g4-pc4-vm2.grupo4-bsi-26-1.maceio.lab` | `g4-pc4-vm2` | `192.168.26.56` |
