# Vamos criar os arquivos Markdown estruturados para cada máquina do Grupo 6 com base no modelo fornecido.
# Como o usuário pediu para "ajudar a criar um arquivo markdown nesse estilo", e forneceu uma lista de 8 máquinas e 4 usuários,
# vamos gerar o conteúdo Markdown correspondente em um arquivo .txt ou .md bem formatado para download,
# além de exibir um exemplo claro na tela.

# Dados fornecidos:
vms = [
    {"hostname": "monica", "fqdn": "monica.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.81"},
    {"hostname": "wladia", "fqdn": "wladia.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.82"},
    {"hostname": "fabrisia", "fqdn": "fabrisia.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.83"},
    {"hostname": "alaelson", "fqdn": "alaelson.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.84"},
    {"hostname": "tarcio", "fqdn": "tarcio.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.85"},
    {"hostname": "kenji", "fqdn": "kenji.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.86"},
    {"hostname": "frederico", "fqdn": "frederico.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.87"},
    {"hostname": "ricardo", "fqdn": "ricardo.grupo6.bsi-26-1.maceio.lab", "ip": "192.168.26.88"}
]

usuarios = [
    "bruno.gabriel",
    "alex.rodrigo",
    "maryane.oliveira",
    "joao.guilherme"
]

# A máscara dada é 255.255.255.240, que equivale a um /28.
# O IP de rede para essa faixa (192.168.26.80/28 vai de .80 a .95). Portanto, sub-rede é 192.168.26.80/28.

content = ""

for vm in vms:
    hostname_upper = vm["hostname"].upper()
    content += f"""# G6-{hostname_upper}

Ficha individual da máquina virtual no ambiente de rede do Grupo 6.

## Identificação

| Campo | Valor |
| :--- | :--- |
| **Hostname** | {vm["hostname"]} |
| **FQDN** | {vm["fqdn"]} |
| **Apelido (alias)** | {vm["hostname"]} |
| **Endereço IP** | {vm["ip"]}/28 |
| **Sub-rede** | 192.168.26.80/28 (255.255.255.240) |
| **Responsável (admin)** | {vm["hostname"]} (Admin da VM) |

## Hardware

| Recurso | Valor |
| :--- | :--- |
| **RAM** | 2048 MB (2 GB) *(Ajuste se necessário)* |
| **vCPU** | 2 núcleos *(Ajuste se necessário)* |
| **Disco** | 32 GB *(Ajuste se necessário)* |
| **SO** | Ubuntu Server *(Ajuste se necessário)* |

## Usuários criados nesta VM

* `bruno.gabriel`
* `alex.rodrigo`
* `maryane.oliveira`
* `joao.guilherme`
* `administrador` (conta administrativa padrão)

> **Membro do grupo sudo nesta máquina:** bruno.gabriel (ou o responsável correspondente)

## Configuração aplicada

A configuração seguiu o tutorial em `../docs/passo-a-passo.md`.

## Arquivo da VM

Pasta da VM no Google Drive com os arquivos para download:
[Acessar pasta no Google Drive](https://link-para-o-seu-drive.com)

*A pasta contém a VM exportada nos formatos .ova (requisito do professor) e .vdi.*

---

"""

with open("fichas_maquinas_grupo6.md", "w", encoding="utf-8") as f:
    f.write(content)

print("Arquivo gerado com sucesso.")
