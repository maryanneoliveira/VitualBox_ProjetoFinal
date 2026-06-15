# Testes de Acesso Remoto (SSH)

Nesta seção são apresentados os resultados dos testes de acesso SSH das VMs do Grupo 6, validando:
- Acesso **por IP**
- Acesso **por hostname** (nome curto)
- Acesso **por FQDN** (nome totalmente qualificado)
- Funcionamento dos **usuários criados**

Para cada teste, executou-se o comando:
```bash
ssh [usuario]@[alvo]
```

---

## 1. Testes de Bruno (bruno.gabriel)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:

#### Por IP (192.168.26.81)
```bash
ssh bruno.gabriel@192.168.26.81
```
<img width="1280" height="800" alt="BRUNO-E-MONICA_POR_IP" src="https://github.com/user-attachments/assets/6e7ac210-5799-46fd-9b60-b3c77cea88f4" />


#### Por hostname (monica)
```bash
ssh bruno.gabriel@monica
```
<img width="1280" height="800" alt="BRUNO-E-MONICA_POR_HOSTENAME" src="https://github.com/user-attachments/assets/5337fad9-828a-494f-8559-e30c2ffd328d" />


#### Por FQDN
```bash
ssh bruno.gabriel@monica.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="BRUNO-E-MONICA_POR_FQDN" src="https://github.com/user-attachments/assets/e8a249f5-9255-4c69-b2c6-14bc083d998f" />

---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh bruno.gabriel@192.168.26.82
```
<img width="1280" height="800" alt="BRUNO-E-WLADIA-POR-IP" src="https://github.com/user-attachments/assets/afd41b08-2372-44c9-8ed7-617228e7ce44" />


#### Por hostname (wladia)
```bash
ssh bruno.gabriel@wladia
```
<img width="1280" height="800" alt="BRUNO-E-WLADIA-POR-HOSTNAME" src="https://github.com/user-attachments/assets/f877a122-17b7-41c4-bf2c-e9d8d46375c4" />


#### Por FQDN
```bash
ssh bruno.gabriel@wladia.grupo6.bsi-26-1.maceio.lab
```

<img width="1280" height="800" alt="BRUNO-E-WLADIA-POR-FWND" src="https://github.com/user-attachments/assets/478ecb58-9a80-4b9a-9a04-d8004a316312" />

---

## 2. Testes de Alex (alex.rodrigo)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:
#### Por IP (192.168.26.81)
```bash
ssh alex.rodrigo@192.168.26.81
```
<img width="1280" height="800" alt="ALEX-E-MONICA_POR_IP" src="https://github.com/user-attachments/assets/a58e1f1d-240f-4069-acbc-a3f0ba625e3b" />

#### Por hostname (monica)
```bash
ssh alex.rodrigo@monica
```
<img width="1280" height="800" alt="ALEX-E-MONICA_POR_HOSTENAME" src="https://github.com/user-attachments/assets/21dd609d-20e5-4421-b19a-738fa9de928f" />


#### Por FQDN
```bash
ssh alex.rodrigo@monica.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="ALEX-E-MONICA_POR_FQDN" src="https://github.com/user-attachments/assets/de0d7666-e9f8-4d5e-b3f5-608b787d5421" />

---

### Em Fabrisia

Os testes foram executados e documentados nas imagens abaixo:
#### Por IP (192.168.26.83)
```bash
ssh alex.rodrigo@192.168.26.83
```
<img width="1280" height="800" alt="ALEX-E-FABRISIA-POR-IP" src="https://github.com/user-attachments/assets/8b4e8a35-4786-40a9-af1a-9c132cbc6429" />

#### Por hostname (fabrisia)
```bash
ssh alex.rodrigo@fabrisia
```
<img width="1280" height="800" alt="ALEX-FABRISIA-POR-HOSTNAME" src="https://github.com/user-attachments/assets/64808350-8af9-4d26-a0e5-620d5eaabce1" />

#### Por FQDN
```bash
ssh alex.rodrigo@fabrisia.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="ALEX-E-FABRISIA-POR-FQDN" src="https://github.com/user-attachments/assets/35d6f6fb-2a7b-45c8-b9fc-bef88d483838" />
---

## 3. Testes de Maryane (maryane.oliveira)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:
#### Por IP (192.168.26.81)
```bash
ssh maryane.oliveira@192.168.26.81
```
<img width="1280" height="800" alt="MARYANE-E-MONICA-POR-IP" src="https://github.com/user-attachments/assets/6a29bb79-6f57-4a1f-b0e6-0d6b174dce0c" />

#### Por hostname (monica)
```bash
ssh maryane.oliveira@monica
```
<img width="1280" height="800" alt="MARYANE-E-MONICA-POR-HOSTNAME" src="https://github.com/user-attachments/assets/e23e65d9-cdb0-48fc-bce3-cb57625040f8" />
#### Por FQDN
```bash
ssh maryane.oliveira@monica.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="MARYANE-E-MONICA-POR-FWND" src="https://github.com/user-attachments/assets/c3c3a2de-1391-47ec-b95c-ad076fe59fc1" />
---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
#### Por IP (192.168.26.81)
```bash
ssh maryane.oliveira@192.168.26.
```
<img width="1280" height="800" alt="MARYANE-E-WLADIA-POR-IP" src="https://github.com/user-attachments/assets/524e0227-c3fe-412f-aa6b-9114b26b2129" />

#### Por hostname (wladia)
```bash
ssh maryane.oliveira@wladia
```
<img width="1280" height="800" alt="MARYANE-E-WLADIA-POR-HOSTNAME" src="https://github.com/user-attachments/assets/b61c0842-306c-4e93-84d8-4a0eae0b36b6" />
#### Por FQDN
```bash
ssh maryane.oliveira@wladia.grupo6.bsi-26-1.maceio.lab
```
<img width="1280" height="800" alt="MARYANE-E-WLADIA-POR-FWND" src="https://github.com/user-attachments/assets/a3ace4f4-ab7e-4071-83dc-105c9a9b1aa0" />
---

## 4. Testes de Joao (joao.guilherme)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh joao.guilherme@192.168.26.81
```
Espaço IMG

#### Por hostname (monica)
```bash
ssh joao.guilherme@monica
```
Espaço IMG

#### Por FQDN
```bash
ssh joao.guilherme@monica.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh joao.guilhermes@192.168.26.82
```
Espaço IMG

#### Por hostname (wladia)
```bash
ssh joao.guilherme@wladia
```
Espaço IMG

#### Por FQDN
```bash
ssh joao.guilherme@wladia.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

## 5. Testes aleatórios cruzados

Testes avulsos onde cada usuário acessa uma VM que não é a sua, usando um tipo de identificação variado. Confirma que todos os usuários foram criados em todas as máquinas e que o SSH funciona entre qualquer par de VMs.

**bruno.gabriel → monica** (IP)

```bash
ssh bruno.gabriel@192.168.26.81
```

Espaço IMG

---

**bruno.gabriel → wladia** (FQDN)

```bash
ssh bruno.gabriel@wladia.grupo6.bsi-26-1.maceio.lab
```

Espaço IMG

---

**alex.rodrigo → monica** (hostname)

```bash
ssh alex.rodrigo@monica
```

Espaço IMG

---

**alex.rodrigo → wladia** (FQDN)

```bash
ssh alex.rodrigo@wladia.grupo6.bsi-26-1.maceio.lab
```

Espaço IMG

---

**maryane.oliveira → wladia (IP)

```bash
ssh maryane.oliveira@192.168.26.82
```

Espaço IMG
---

**maryane.oliveira → monica** (hostname)

```bash
ssh maryane.oliveira@monica
```

Espaço IMG

---

**joao.guilherme → monica** (IP)

```bash
ssh joao.guilherme@192.168.26.81
```

Espaço IMG

---

**joao.guilherme → wladia** (FQDN)

```bash
ssh joao.guilherme@wladia.grupo6.bsi-26-1.maceio.lab
```

Espaço IMG

---

## 6. Resumo

**Total de testes:** 32 prints (24 originais + 8 cruzados aleatórios)

Todos os testes de SSH foram bem-sucedidos, demonstrando:
- ✅ Acesso remoto funcionando com todos os usuários
- ✅ Resolução de nomes por IP habilitada
- ✅ Resolução de nomes por hostname habilitada
- ✅ Resolução de nomes por FQDN habilitada
- ✅ Autenticação funcionando em todas as máquinas
- ✅ Usuários criados corretamente em VMs de outros integrantes
- ✅ Comunicação SSH segura estabelecida
