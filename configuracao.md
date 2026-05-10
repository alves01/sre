# Lab SRE - Agente com Dynatrace MCP

## 📋 PRÉ-REQUISITOS

### 0. Estar em ambiente Ubuntu / Windows (WSL)

### 1. Instalar Node.js (v22+)

```bash
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

node --version
npm --version

### 2. Instalar Amazon Q CLI

curl --proto '=https' --tlsv1.2 -sSf https://desktop-release.q.us-east-1.amazonaws.com/latest/amazon-q.deb -o amazon-q.deb
sudo apt install -y ./amazon-q.deb

q --version

q login

### 3. Diretorios principais devem estar nessa hierarquia

mkdir -p ~/.aws/amazonq/prompts
mkdir -p ~/.aws/amazonq/cli-agents

### 4. no arquivo sre.json adicionar token de acesso

Gerar o token de plataforma no Dynatrace.
Se estiver usando o Playground não é necessário token.

"env": {
  "DT_ENVIRONMENT": "https://{tenant}.apps.dynatrace.com",
  "DT_PLATFORM_TOKEN": "{token}"
}

### Executar ###

Se tudo der certo agora é só subir o agente

q chat --agent sre
