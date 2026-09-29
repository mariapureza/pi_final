# Pet Rescue

Projeto Integrador VI-A — Universidade Católica de Pelotas

Curso de Análise e Desenvolvimento de Sistemas

Disciplinas:
- Engenharia de Software III
- Programação Back-End

Professores:
- Morgana Macedo Azevedo da Rosa
- Rogério Albandes

Integrantes:
- João Vitor Milech dos Santos
- Maria Eduarda Duarte Pureza

Ano: 2026

---

## Sobre o projeto

O Pet Rescue é uma aplicação web desenvolvida com o objetivo de apoiar a adoção responsável e organizar a gestão básica de animais resgatados.

A plataforma possui dois módulos principais:

- uma área pública, voltada para visitantes interessados em conhecer os animais disponíveis e registrar interesse em adoção;
- uma área administrativa autenticada, destinada ao gerenciamento dos animais e das solicitações recebidas.

---

## Funcionalidades implementadas

### Área pública

- Catálogo de animais cadastrados no banco de dados.
- Pesquisa de animais.
- Visualização dos animais disponíveis e em processo de adoção.
- Página individual de detalhes do animal.
- Exibição de:
  - nome;
  - espécie;
  - raça;
  - idade;
  - porte;
  - status;
  - data de resgate;
  - descrição;
  - imagem.
- Formulário de interesse em adoção.
- Validação de campos obrigatórios.
- Registro da solicitação no banco de dados.
- Tela de confirmação após o envio.

### Área administrativa

- Login de administrador.
- Senha armazenada utilizando hash com bcrypt.
- Controle de acesso por sessão.
- Proteção das rotas administrativas.
- Painel administrativo.
- Listagem dos animais cadastrados.
- Cadastro de novos animais.
- Edição dos dados dos animais.
- Atualização do status do animal para:
  - disponível;
  - em processo;
  - adotado.
- Exclusão de animais sem solicitações vinculadas.
- Listagem das solicitações de adoção.
- Atualização do status das solicitações para:
  - pendente;
  - aprovada;
  - rejeitada.
- Logout administrativo.

---

## Tecnologias utilizadas

- Node.js
- Express
- JavaScript
- EJS
- HTML5
- CSS3
- MySQL
- mysql2
- bcrypt
- express-session
- dotenv

---

## Arquitetura

O projeto utiliza uma organização em camadas inspirada no padrão MVC, com separação entre interface, rotas, autenticação, regras da aplicação e persistência.

Estrutura principal:

```text
PetRescue/
│
├── app.js
├── package.json
├── package-lock.json
├── .env.example
├── .gitignore
│
├── database/
│   ├── schema.sql
│   └── dados_demo.sql
│
├── public/
│   ├── css/
│   ├── js/
│   └── img/
│
├── src/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── services/
│
└── views/
    ├── index.ejs
    ├── animal.ejs
    ├── interesse.ejs
    ├── sucesso.ejs
    ├── login.ejs
    └── admin/
        ├── dashboard.ejs
        ├── animais.ejs
        ├── animal-form.ejs
        └── solicitacoes.ejs
