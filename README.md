# pendrive-bitlocker
como transforma eu pendrive em uma chave bitlocke
# 🔐 BitLocker USB Startup Key

Transformando um pendrive comum em uma **chave física de inicialização do Windows usando o BitLocker**.

Este projeto documenta como configurar o BitLocker para utilizar simultaneamente:

- TPM do computador
- Pendrive USB como Startup Key
- Chave de recuperação de 48 dígitos como método de recuperação

> ⚠️ **IMPORTANTE:** este projeto ensina a configuração. Nenhuma chave `.BEK` real deve ser publicada neste repositório.

---

## 📌 Como funciona

O BitLocker normalmente utiliza o TPM para liberar automaticamente a unidade do Windows durante a inicialização.

Neste projeto, adicionamos uma **Startup Key armazenada em um pendrive USB**.

O fluxo fica:

```text
┌─────────────────┐
│   Computador    │
│                 │
│      TPM        │
└────────┬────────┘
         │
         │
         ▼
┌─────────────────┐
│ Pendrive USB    │
│                 │
│  Chave.BEK      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    BitLocker    │
│                 │
│ Libera o Windows│
└─────────────────┘
