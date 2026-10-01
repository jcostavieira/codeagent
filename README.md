# codeagent
Um agente programador de IA gratuito, local e de código aberto. Funciona como seu programador pessoal, capaz de analisar projetos, ler/criar/editar código, executar testes e trabalhar de forma autônoma com aprovação do usuário.

## Funcionalidades

- Conversar com o agente em linguagem natural
- Analisar projetos e repositórios
- Ler e entender arquivos
- Criar novos arquivos
- Editar arquivos existentes
- Executar testes
- Solicitar autorização antes de alterações
- Funcionar localmente com Ollama
- Não depender de APIs pagas

## Requisitos

- Python 3.11+
- Node.js 18+
- npm
- Git
- Ollama (opcional, mas recomendado para modelos locais)

## Estrutura do projeto

```text
codeagent/
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── agent/
│   │   ├── llm/
│   │   ├── tools/
│   │   ├── filesystem/
│   │   ├── security/
│   │   ├── models/
│   │   └── main.py
│   ├── tests/
│   └── requirements.txt
├── frontend/
│   ├── src/
│   ├── package.json
│   └── tsconfig.json
├── workspace/
├── docs/
├── .env.example
├── .gitignore
├── docker-compose.yml
├── LICENSE
├── README.md
└── .gitignore
```

## Instalação

### Backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### Frontend

```bash
cd frontend
npm install
```

## Configuração

Copie o arquivo `.env.example` para `.env` e ajuste conforme necessário.

```bash
cp .env.example .env
```

## Como iniciar

### Backend

```bash
cd backend
source .venv/bin/activate
uvicorn app.main:app --reload --host 127.0.0.1 --port 8000
```

### Frontend

```bash
cd frontend
npm run dev -- --host 0.0.0.0
```

## Como usar

1. Inicie backend e frontend.
2. Acesse a interface web.
3. Digite sua tarefa em linguagem natural.
4. O agente analisa o projeto, cria um plano e pede autorização antes de alterar arquivos.

## Segurança

- O agente trabalha dentro do diretório `/workspace`.
- Path traversal é bloqueado.
- Comandos perigosos exigem autorização explícita.
- Nenhuma chave, senha ou token deve ser gravada no código.
- Utilize `.env` e mantenha `.env` fora do controle de versionamento.

## Testes

```bash
cd backend
source .venv/bin/activate
pytest
```

## Contribuição

Contribuições são bem-vindas. Abra uma issue ou pull request com a sua proposta.

## Licença

Este projeto está sob a licença MIT.
