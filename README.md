# thaiza.dev — Portfólio

Portfólio pessoal desenvolvido com HTML, CSS e JavaScript no frontend 
e FastAPI + Python no backend.

## Tecnologias
- HTML, CSS, JavaScript
- FastAPI
- smtplib (envio de e-mails)

## Funcionalidades
- Apresentação pessoal
- Listagem de projetos
- Formulário de contato com envio real de e-mail
- Validação de formulário em JavaScript

## Como rodar localmente

1. Clone o repositório
2. Crie um arquivo `.env` com sua senha de app do Gmail:
GMAIL_SENHA=sua_senha_aqui

3. Instale as dependências:
pip install fastapi uvicorn python-dotenv psycopg2-binary pydantic[email]

4. Crie o banco de dados no PostgreSQL:
CREATE DATABASE portfolio;

5. Configure o `.env`:
DATABASE_URL=postgresql://usuario:senha@localhost:5432/portfolio

MEU_EMAIL=seu_email@gmail.com
SENHA_EMAIL=sua_senha_de_app_gmail

6. Rode a API:
uvicorn main:app --reload

7. Abra o `sobre.html` no navegador

# thaiza.dev — Portfólio Pessoal

Portfólio pessoal desenvolvido com HTML, CSS e JavaScript no frontend e FastAPI + Python no backend. O projeto inclui um formulário de contato funcional que salva mensagens no banco de dados PostgreSQL e encaminha para o e-mail da desenvolvedora via Gmail.

## Sobre o projeto

Este portfólio foi desenvolvido como projeto acadêmico e também como vitrine profissional. O site apresenta informações pessoais, formação, projetos e um canal de contato direto. O backend foi construído seguindo boas práticas de desenvolvimento com separação de responsabilidades em camadas (routes, models, schemas, dependencies).

## Tecnologias utilizadas

Frontend:
- HTML5 e CSS3
- JavaScript (validação de formulário e integração com a API)
- Fonte JetBrains Mono (Google Fonts)
- Animações CSS (bolhas no fundo, transições e hover)

Backend:
- Python 3
- FastAPI
- SQLAlchemy (ORM)
- PostgreSQL
- Pydantic com EmailStr
- smtplib (envio de e-mails via Gmail)
- python-dotenv (variáveis de ambiente)

## Estrutura do projeto

portfolio/
├── frontend/
│   ├── sobre.html
│   ├── formacao.html
│   ├── portfolio.html
│   ├── contato.html
│   ├── style.css
│   ├── script.js
│   └── minha-foto.png
└── backend/
    ├── main.py
    ├── database.py
    ├── models.py
    ├── schemas.py
    ├── dependencies.py
    ├── routes/
    │   └── contato.py
    └── .env

## Funcionalidades

Frontend:
- Apresentação pessoal
- Projetos com links
- Linha do tempo de formação
- Formulário de contato com validação JS
- Modal de confirmação
- Animações de fundo

Backend:
- POST /contato para salvar mensagens
- GET /contato para listar mensagens
- Persistência em PostgreSQL
- Envio de e-mail automático
- Validação com Pydantic

## Endpoints da API

POST /contato → salva mensagem e envia e-mail  
GET /contato → lista mensagens

Exemplo:
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "mensagem": "Olá!"
}

## Como rodar localmente

Pré-requisitos:
- Python 3.10+
- PostgreSQL local
- Gmail com senha de app

1. Clone o repositório:
git clone https://github.com/thaiza-d/NOME_DO_REPO.git
cd NOME_DO_REPO

2. Instale dependências:
pip install fastapi uvicorn sqlalchemy psycopg2-binary python-dotenv pydantic[email]

3. Crie banco:
CREATE DATABASE portfolio;

4. Crie .env:
DATABASE_URL=postgresql://usuario:senha@localhost:5432/portfolio
MEU_EMAIL=seu_email@gmail.com
SENHA_EMAIL=sua_senha_de_app_gmail

5. Rode API:
uvicorn main:app --reload

6. Abra o frontend no navegador

## Variáveis de ambiente

DATABASE_URL → banco PostgreSQL  
MEU_EMAIL → e-mail Gmail  
SENHA_EMAIL → senha de app Gmail

## Observações

- .env não deve ser enviado ao GitHub
- Em produção, DATABASE_URL aponta para PostgreSQL do Render
- Frontend deve apontar para URL real da API

## Autora

Thaiza Dantas
GitHub: https://github.com/thaiza-d
LinkedIn: https://www.linkedin.com/in/thaiza-dantas-b312101b2/