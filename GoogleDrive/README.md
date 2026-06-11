# Ambiente de Redes - Grupo 6

Repositório central de documentação das Máquinas Virtuais (VMs) do Grupo 6 para o ambiente de laboratório em Maceió (`bsi-26-1.maceio.lab`).

## 📁 Repositório de Arquivos (Google Drive)

Todos os arquivos de exportação das máquinas virtuais (formatos `.ova`) e mídias associadas estão centralizados na pasta oficial do grupo:
👉 [Acessar Pasta das VMs no Google Drive](https://drive.google.com/drive/folders/1u9IyqkYuf8fma2Ci4PTQjKcYpeCI2SyH?usp=sharing)

---

## 🖥️ Visão Geral do Parque de Máquinas (Inventário de Rede)

Toda a sub-rede do grupo está sob o escopo do bloco **192.168.26.80/28** utilizando a máscara de rede **255.255.255.240**.

| Nome da Máquina | FQDN Completo | Endereço IP | Máscara | Sub-rede |
| :--- | :--- | :--- | :--- | :--- |
| **monica** | monica.grupo6.bsi-26-1.maceio.lab | `192.168.26.81/28` | 255.255.255.240 | 192.168.26.80/28 |
| **wladia** | wladia.grupo6.bsi-26-1.maceio.lab | `192.168.26.82/28` | 255.255.255.240 | 192.168.26.80/28 |
| **fabrisia** | fabrisia.grupo6.bsi-26-1.maceio.lab | `192.168.26.83/28` | 255.255.255.240 | 192.168.26.80/28 |
| **alaelson** | alaelson.grupo6.bsi-26-1.maceio.lab | `192.168.26.84/28` | 255.255.255.240 | 192.168.26.80/28 |
| **tarcio** | tarcio.grupo6.bsi-26-1.maceio.lab | `192.168.26.85/28` | 255.255.255.240 | 192.168.26.80/28 |
| **kenji** | kenji.grupo6.bsi-26-1.maceio.lab | `192.168.26.86/28` | 255.255.255.240 | 192.168.26.80/28 |
| **frederico** | frederico.grupo6.bsi-26-1.maceio.lab | `192.168.26.87/28` | 255.255.255.240 | 192.168.26.80/28 |
| **ricardo** | ricardo.grupo6.bsi-26-1.maceio.lab | `192.168.26.88/28` | 255.255.255.240 | 192.168.26.80/28 |

---

## 👥 Credenciais e Usuários Homologados

Os seguintes usuários foram provisionados localmente em todas as instâncias do ecossistema do Grupo 6:

*   `bruno.gabriel`
*   `alex.rodrigo`
*   `maryane.oliveira`
*   `joao.guilherme`
*   `administrador` *(Conta administrativa padrão do sistema)*

---

## 🛠️ Especificações de Hardware Padrão (Por VM)

*   **Sistema Operacional:** Ubuntu Server
*   **Memória RAM:** 2048 MB (2 GB)
*   **Processamento (vCPU):** 2 núcleos
*   **Armazenamento (Disco):** 10 GB

---

## 📖 Instruções de Implantação

Os procedimentos detalhados de configuração de serviços, roteamento, segurança e parametrização local encontram-se documentados no roteiro passo-a-passo em:
`../docs/tutorial.md`
