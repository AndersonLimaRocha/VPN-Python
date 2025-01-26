# Gerenciador de Túnel SSH em Python

Este repositório contém um script Python para estabelecer e monitorar um túnel SSH utilizando a biblioteca `sshtunnel`. O objetivo é criar uma conexão segura e persistente entre a máquina local e um banco de dados MySQL remoto hospedado em um servidor acessível via VPN.

---

## Funcionalidades

- **Estabelecimento de túnel SSH**: Redireciona o tráfego da porta local para um servidor remoto através de um túnel SSH seguro.
- **Monitoramento e reconexão automática**: O script monitora o status do túnel e tenta reconectar automaticamente em caso de interrupções.
- **Pacotes Keep-Alive**: Garante que a conexão seja mantida ativa por meio do envio de pacotes periódicos.

---

## Pré-requisitos

1. **Chave privada SSH (PEM)**: Certifique-se de que a chave privada no formato PEM está configurada corretamente.
2. **Python 3.7+** com as bibliotecas:
   - [`sshtunnel`](https://pypi.org/project/sshtunnel/)
   - [`paramiko`](https://pypi.org/project/paramiko/)
3. **Permissões de rede**: A máquina local deve ter permissão para acessar o servidor SSH.

---

## Configurações

As principais variáveis configuráveis no script incluem:

### Credenciais de SSH
- `private_key_path`: Caminho para o arquivo de chave privada.
- `hostname`: Endereço do servidor SSH.
- `username`: Usuário para autenticação.
- `port`: Porta do servidor SSH.

### Redirecionamento de portas
- `remote_host`: Endereço do host remoto (banco de dados MySQL).
- `remote_port`: Porta do banco de dados remoto.
- `local_port`: Porta local para redirecionamento.

### Configurações de reconexão
- `MAX_RETRIES`: Número máximo de tentativas de reconexão.
- `RETRY_DELAY`: Tempo entre tentativas de reconexão.
- `KEEP_ALIVE_INTERVAL`: Intervalo de envio de pacotes keep-alive.

---

## Como usar

1. **Clone este repositório**:

   ```bash
   git clone https://github.com/seu-usuario/nome-repositorio.git
   cd nome-repositorio
