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
Espaço IMG

#### Por hostname (monica)
```bash
ssh bruno.gabriel@monica
```
Espaço IMG

#### Por FQDN
```bash
ssh bruno.gabriel@monica.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh bruno.gabriel@192.168.26.82
```
Espaço IMg

#### Por hostname (wladia)
```bash
ssh bruno.gabriel@wladia
```
Espaço IMG

#### Por FQDN
```bash
ssh bruno.gabriel@wladia.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

## 2. Testes de Alex (alex.rodrigo)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh alex.rodrigo@192.168.26.81
```
Espaço IMG

#### Por hostname (monica)
```bash
ssh alex.rodrigo@monica
```
Espaço IMG

#### Por FQDN
```bash
ssh alex.rodrigo@monica.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh alex.rodrigo@192.168.26.82
```
Espaço IMG

#### Por hostname (wladia)
```bash
ssh alex.rodrigo@wladia
```
Espaço IMG

#### Por FQDN
```bash
ssh alex.rodrigo@wladia.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

## 3. Testes de Maryane (maryane.oliveira)

### Em monica

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh maryane.oliveira@192.168.26.81
```
Espaço IMG

#### Por hostname (monica)
```bash
ssh maryane.oliveira@monica
```
Espaço IMG

#### Por FQDN
```bash
ssh maryane.oliveira@monica.grupo6.bsi-26-1.maceio.lab
```
Espaço IMG

---

### Em wladia

Os testes foram executados e documentados nas imagens abaixo:
```bash
ssh maryane.oliveira@192.168.26.54
```
Espaço IMG

#### Por hostname (wladia)
```bash
ssh maryane.oliveira@wladia
```
Espaço IMG

#### Por FQDN
```bash
ssh maryane.oliveira@wladia.grupo6.bsi-26-1.maceio.lab
Espaço IMG

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

**alex.rodrigo → monica** (FQDN)

```bash
ssh alex.rodrigo@monica.grupo6.bsi-26-1.maceio.lab
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
