# PrintSploit

🇺🇸 **English** | 🇧🇷 **Português**

---

# 🇺🇸 English

## Overview

PrintSploit is a Python proof-of-concept library that demonstrates how to invoke Roblox's internal logging function from an external process. It was created for educational purposes, Windows internals research, and reverse engineering studies.

## Features

* Print custom messages to the Roblox output.
* Supports multiple log levels:

  * `RBX_PRINT`
  * `RBX_INFO`
  * `RBX_WARNING`
  * `RBX_ERROR`
* Built entirely with Python using `ctypes`.
* Automatically locates the Roblox process.
* Enables the required Windows privileges before interacting with the target process.

## How It Works

The library follows these steps:

1. Enables `SeDebugPrivilege`.
2. Locates the `RobloxPlayerBeta.exe` process.
3. Builds a small x64 shellcode containing the desired message.
4. Allocates executable memory inside the target process.
5. Writes the shellcode into the allocated memory.
6. Triggers execution through an internal callback mechanism.
7. Closes opened handles and reports the execution status.

## Example

```python
from printsploit import *

printsploit("Hello from PrintSploit!", RBX_INFO)
```

### Available Log Levels

```python
RBX_PRINT
RBX_INFO
RBX_WARNING
RBX_ERROR
```

## Requirements

* Windows x64
* Python 3.10+
* Roblox running
* Administrator privileges

## Disclaimer

This project is intended exclusively for educational purposes, reverse engineering research, and studying Windows internals. Use it only in environments where you have authorization to perform such research. Reverse engineering or modifying third-party software may violate its Terms of Service.

---

# 🇧🇷 Português

## Visão Geral

PrintSploit é uma biblioteca em Python desenvolvida como prova de conceito para demonstrar a chamada da função interna de logs do Roblox a partir de um processo externo. O projeto foi criado para fins educacionais, estudos sobre internals do Windows e pesquisas de engenharia reversa.

## Recursos

* Envia mensagens personalizadas para o console do Roblox.
* Suporta diferentes níveis de log:

  * `RBX_PRINT`
  * `RBX_INFO`
  * `RBX_WARNING`
  * `RBX_ERROR`
* Desenvolvido inteiramente em Python utilizando `ctypes`.
* Localiza automaticamente o processo do Roblox.
* Habilita os privilégios necessários antes de interagir com o processo alvo.

## Como Funciona

A biblioteca executa as seguintes etapas:

1. Habilita o privilégio `SeDebugPrivilege`.
2. Localiza o processo `RobloxPlayerBeta.exe`.
3. Constrói um pequeno shellcode x64 contendo a mensagem desejada.
4. Aloca memória executável dentro do processo alvo.
5. Escreve o shellcode na memória alocada.
6. Aciona sua execução por meio de um mecanismo interno de callback.
7. Fecha os handles abertos e informa o resultado da operação.

## Exemplo

```python
from printsploit import *

printsploit("Olá do PrintSploit!", RBX_INFO)
```

### Níveis de Log

```python
RBX_PRINT
RBX_INFO
RBX_WARNING
RBX_ERROR
```

## Requisitos

* Windows x64
* Python 3.10 ou superior
* Roblox em execução
* Privilégios de Administrador

## Aviso

Este projeto destina-se exclusivamente a fins educacionais, pesquisas de engenharia reversa e estudos sobre o funcionamento interno do Windows. Utilize-o apenas em ambientes nos quais você tenha autorização para realizar esse tipo de pesquisa. A engenharia reversa ou modificação de softwares de terceiros pode violar seus Termos de Serviço.
