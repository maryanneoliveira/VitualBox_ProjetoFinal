# Testes de Conectividade (Ping)

Nesta seção, registramos os testes de conectividade de rede ICMP realizados de forma cruzada entre as VMs do Grupo 6. Foram validadas três camadas de resolução: por endereço IP direto, por nome curto (hostname) e por nome totalmente qualificado (FQDN).

Os comandos de destino foram disparados em lote no terminal para que uma única captura de tela registre as três validações em sequência.

## Testes efetuados a partir de monica
Destino: wladia


ping -c 4 192.168.26.82 
<img width="1280" height="800" alt="monica-pra-wladia-1" src="https://github.com/user-attachments/assets/fb09e8f9-eed7-468c-9944-150b4d0fd42e" />

ping -c 4 wladia
<img width="1280" height="800" alt="monica-pra-wladia-2" src="https://github.com/user-attachments/assets/a8ec4d76-37d4-4738-b3ac-c5c6d5ade4c1" />

ping -c 4 wladia.grupo6.bsi-26-1.maceio.lab
<img width="1280" height="800" alt="monica-pra-wladia-3" src="https://github.com/user-attachments/assets/19899378-1c8d-49b4-98ef-524136092e3d" />

```
Destino: fabrisia
```bash
ping -c 4 192.168.26.83
ping -c 4 fabrisia
ping -c 4 fabrisia.grupo6.bsi-26-1.maceio.lab
```
Destino: alaelson
```bash
ping -c 4 192.168.26.84
ping -c 4 alaelson
ping -c 4 alaelson.grupo6.bsi-26-1.maceio.lab
```
## Testes efetuados a partir de wladia
Destino: monica
```bash
ping -c 4 192.168.26.81
ping -c 4 monica
ping -c 4 monica.grupo6.bsi-26-1.maceio.lab
```
Destino: tarcio
```bash
ping -c 4 192.168.26.85
ping -c 4 tarcio
ping -c 4 tarcio.grupo6.bsi-26-1.maceio.lab
```
Destino: kenji
```bash
ping -c 4 192.168.26.86
ping -c 4 kenji
ping -c 4 kenji.grupo6.bsi-26-1.maceio.lab
```
## Testes efetuados a partir de fabrisia
Destino: frederico
```bash
ping -c 4 192.168.26.87
ping -c 4 frederico
ping -c 4 frederico.grupo6.bsi-26-1.maceio.lab
```
Destino: ricardo
```bash
ping -c 4 192.168.26.88
ping -c 4 ricardo
ping -c 4 ricardo.grupo6.bsi-26-1.maceio.lab
```
## Testes efetuados a partir de alaelson
Destino: monica
```bash
ping -c 4 192.168.26.81
ping -c 4 monica
ping -c 4 monica.grupo6.bsi-26-1.maceio.lab
```
Destino: tarcio
```bash
ping -c 4 192.168.26.85
ping -c 4 tarcio
ping -c 4 tarcio.grupo6.bsi-26-1.maceio.lab
```
## Amostragem Cruzada e Testes Aleatórios Adicionais
**Para garantir a cobertura completa de rotas ponto a ponto em todas as direções residuais da malha, executamos disparos pontuais adicionais alternando os formatos de identificação.**

tarcio → kenji (Por IP direto)
```bash
ping -c 4 192.168.26.86
````

kenji → frederico (Por FQDN completo)
```bash
ping -c 4 frederico.grupo6.bsi-26-1.maceio.lab
````

frederico → ricardo (Por Hostname curto)
```bash
ping -c 4 ricardo
````

ricardo → monica (Por IP direto)
```bash
ping -c 4 192.168.26.81
```

monica → tarcio (Por Hostname curto)
```bash
ping -c 4 tarcio
```

fabrisia → kenji (Por FQDN completo)
```bash
ping -c 4 kenji.grupo6.bsi-26-1.maceio.lab
```

wladia → frederico (Por IP direto)
```bash
ping -c 4 192.168.26.87
```

alaelson → ricardo (Por Hostname curto)
```bash
ping -c 4 ricardo
```
