<p align="center">
  <a href="#português">🇧🇷 Português</a> | <a href="#english">🇬🇧 English</a>
</p>

---

## Português

# Simple Port Scanner em C

Este é um projeto simples de segurança ofensiva desenvolvido em linguagem C que funciona como um **Port Scanner**. O programa interage com a pilha de protocolos TCP/IP através de *sockets* de baixo nível para verificar se uma porta de rede específica está aberta ou fechada no sistema local.

## O que faz

* **Interação via Terminal:** Solicita ao utilizador que introduza o número de uma porta.
* **Criação de Sockets:** Utiliza a API de *sockets* do Linux (`SOCK_STREAM`) para iniciar uma comunicação TCP.
* **Diagnóstico de Conexão:** Tenta estabelecer uma ligação (*3-way handshake*). Se for bem-sucedido, informa que a porta está aberta (`open`). Caso contrário, reporta o erro do sistema (como `Connection refused`).

## Pré-requisitos

Para compilar e testar este projeto, necessita de:
* Um sistema operativo baseado em **Linux** ou **macOS**.
* O compilador **GCC** instalado.
* A ferramenta **Netcat (`nc`)** (opcional, para criar portas de teste).

## Como Compilar e Testar

Siga os passos abaixo no seu terminal para testar a aplicação:

### 1. Compilar
```bash
gcc -Wall main.c
```

### 2. Preparar o Ambiente de Teste (Simular Porta Aberta)
Para validar que o scanner deteta corretamente uma porta aberta, abra um novo terminal e utilize o `netcat` para colocar a porta `8080` a escutar conexões:
```bash
nc -l 8080
```

### 3. Executar o Scanner
No seu terminal principal, execute o programa:
```bash
./a.out
```

* **Cenário de Porta Aberta:** Quando o programa pedir `Enter the number of port:`, digite `8080`. O resultado esperado será:
  ```text
  8080 open.
  ```
* **Cenário de Porta Fechada:** Execute o programa novamente e digite uma porta que não esteja a ser usada. O resultado esperado será:
  ```text
  connect: Connection refused
  ```

## 🔒 Aviso Legal
Este projeto foi desenvolvido estritamente para fins **educativos e de aprendizagem** em cibersegurança. O uso de ferramentas de varredura de portas em redes ou sistemas sem autorização prévia é ilegal.

<p align="right"><a href="#top">🔼 back to top</a></p>

---

## English

# Simple Port Scanner in C

This is a simple offensive security project developed in C that works as a **Port Scanner**. The program interacts with the TCP/IP protocol stack through low-level *sockets* to check whether a specific network port is open or closed on the local system.

## What it does

* **Terminal Interaction:** Prompts the user to enter a port number.
* **Socket Creation:** Uses the Linux *socket* API (`SOCK_STREAM`) to initiate a TCP communication.
* **Connection Diagnosis:** Attempts to establish a connection (*3-way handshake*). If successful, it reports that the port is open (`open`). Otherwise, it reports the system error (such as `Connection refused`).

## Prerequisites

To compile and test this project, you need:
* A **Linux** or **macOS** based operating system.
* The **GCC** compiler installed.
* The **Netcat (`nc`)** tool (optional, for creating test ports).

## How to Compile and Test

Follow the steps below in your terminal to test the application:

### 1. Compile
```bash
gcc -Wall main.c
```

### 2. Set Up the Test Environment (Simulate an Open Port)
To validate that the scanner correctly detects an open port, open a new terminal and use `netcat` to make port `8080` listen for connections:
```bash
nc -l 8080
```

### 3. Run the Scanner
In your main terminal, run the program:
```bash
./a.out
```

* **Open Port Scenario:** When the program asks `Enter the number of port:`, type `8080`. The expected result will be:
  ```text
  8080 open.
  ```
* **Closed Port Scenario:** Run the program again and enter a port that isn't in use. The expected result will be:
  ```text
  connect: Connection refused
  ```

## 🔒 Legal Disclaimer
This project was developed strictly for **educational and learning purposes** in cybersecurity. Using port scanning tools on networks or systems without prior authorization is illegal.

<p align="right"><a href="#top">🔼 back to top</a></p>
