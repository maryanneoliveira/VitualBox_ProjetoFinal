# Testes de Conectividade (Ping)

Nesta seção, registramos os testes de conectividade de rede ICMP realizados de forma cruzada entre as VMs do Grupo 6. Foram validadas três camadas de resolução: por endereço IP direto, por nome curto (hostname) e por nome totalmente qualificado (FQDN).

Os comandos de destino foram disparados em lote no terminal para que uma única captura de tela registre as três validações em sequência.

## Testes efetuados a partir de monica
Destino: wladia

```bash
ping -c 4 192.168.26.82 
ping -c 4 wladia
ping -c 4 wladia.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="monica-pra-wladia-3 (1)" src="https://github.com/user-attachments/assets/9f7c06ee-3261-46c0-89c6-fec079f2c95a" />

Destino: fabrisia
```bash
ping -c 4 192.168.26.83
ping -c 4 fabrisia
ping -c 4 fabrisia.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="monica-pra-fabrisia-1" src="https://github.com/user-attachments/assets/81a010fc-dcca-4e48-9b5b-1bd5508ff609" />
<img width="1280" height="800" alt="monica-pra-fabrisia-2" src="https://github.com/user-attachments/assets/311ef711-b978-43c8-8fe8-73af88ab208f" />
<img width="1280" height="800" alt="monica-pra-fabrisia-3" src="https://github.com/user-attachments/assets/02370e47-5fe8-404e-9145-5b63aec79f0a" />


Destino: alaelson
```bash
ping -c 4 192.168.26.84
ping -c 4 alaelson
ping -c 4 alaelson.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="monica-pra-alaelson-1" src="https://github.com/user-attachments/assets/4b6f3a13-e688-4bf4-9018-19ad7cbfbedf" />
<img width="1280" height="800" alt="monica-pra-alaelson-2" src="https://github.com/user-attachments/assets/bcc85aa6-8106-4529-b550-699c82f8a962" />
<img width="1280" height="800" alt="monica-pra-alaelson-3" src="https://github.com/user-attachments/assets/f9344c55-d8c6-4e36-bec2-92fa15f4506a" />

## Testes efetuados a partir de wladia
Destino: monica
```bash
ping -c 4 192.168.26.81
ping -c 4 monica
ping -c 4 monica.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="wladia-pra-monica" src="https://github.com/user-attachments/assets/5b83ca75-7639-4d91-9824-cfae3d1bacd5" />

Destino: tarcio
```bash
ping -c 4 192.168.26.85
ping -c 4 tarcio
ping -c 4 tarcio.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="wladia-pra-tarcio" src="https://github.com/user-attachments/assets/b24e6c2a-3020-459b-a678-e0b455c6a64b" />

Destino: kenji
```bash
ping -c 4 192.168.26.86
ping -c 4 kenji
ping -c 4 kenji.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="wladia-pra-kenji" src="https://github.com/user-attachments/assets/f35f7b72-6ec3-4a88-bfd0-ee9f5cc0ff21" />

## Testes efetuados a partir de fabrisia
Destino: frederico
```bash
ping -c 4 192.168.26.87
ping -c 4 frederico
ping -c 4 frederico.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="fabrisia-para-frederico" src="https://github.com/user-attachments/assets/6f6d5e05-3f74-41fd-b27a-e5f19595f5b6" />

Destino: ricardo
```bash
ping -c 4 192.168.26.88
ping -c 4 ricardo
ping -c 4 ricardo.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="alaelson-pra-ricardo" src="https://github.com/user-attachments/assets/4e2bc3d1-ee38-4080-bc26-e3811c4587c0" />

## Testes efetuados a partir de alaelson
Destino: monica
```bash
ping -c 4 192.168.26.81
ping -c 4 monica
ping -c 4 monica.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="alaelson-pra-monica" src="https://github.com/user-attachments/assets/d30144e3-9348-484e-a142-83acdd270a9a" />

Destino: tarcio
```bash
ping -c 4 192.168.26.85
ping -c 4 tarcio
ping -c 4 tarcio.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="alaelson-pra-tarcio" src="https://github.com/user-attachments/assets/fa9a6177-c6c4-4ae6-b0ea-206c62c7e362" />

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
