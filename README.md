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
- Exibição de nome, espécie, raça, idade, porte, status, data de resgate, descrição e imagem.
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
- Atualização do status do animal para disponível, em processo ou adotado.
- Exclusão de animais sem solicitações vinculadas.
- Listagem das solicitações de adoção.
- Atualização do status das solicitações para pendente, aprovada ou rejeitada.
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

PetRescue/
├── app.js
├── package.json
├── package-lock.json
├── .env.example
├── .gitignore
├── database/
│   ├── schema.sql
│   └── dados_demo.sql
├── public/
│   ├── css/
│   ├── js/
│   └── img/
├── src/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── services/
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

---

## Banco de dados

O sistema utiliza MySQL e possui três entidades principais:

### Administrador

Responsável pelo acesso à área administrativa.

Principais campos:
- id_administrador
- nome
- email
- senha_hash

### Animal

Representa os animais divulgados pela plataforma.

Principais campos:
- id_animal
- nome
- especie
- raca
- idade
- porte
- status
- data_resgate
- descricao
- foto_url

### Solicitação de adoção

Armazena as manifestações de interesse enviadas pelos visitantes.

Principais campos:
- id_solicitacao
- id_animal
- nome_interessado
- email_interessado
- telefone
- mensagem
- data_solicitacao
- status_solicitacao

---

## Como executar o projeto

### 1. Requisitos

É necessário possuir:
- Node.js
- npm
- MySQL

### 2. Instalar as dependências

Dentro da pasta do projeto, execute:

npm install

### 3. Criar o banco de dados

Execute o arquivo:

database/schema.sql

Depois execute:

database/dados_demo.sql

Os scripts criam a estrutura necessária e adicionam dados de demonstração para uso acadêmico.

### 4. Configurar o ambiente

Crie um arquivo chamado:

.env

na raiz do projeto.

Use o arquivo .env.example como referência.

Exemplo:

PORT=3000

DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=sua_senha_do_mysql
DB_NAME=pet_rescue

SESSION_SECRET=sua_chave_de_sessao

O arquivo .env não deve ser enviado para repositórios públicos.

### 5. Iniciar a aplicação

Execute:

npm start

A aplicação ficará disponível em:

http://localhost:3000

---

## Área administrativa

A página de login está disponível em:

http://localhost:3000/login

Credenciais de demonstração:

E-mail: admin@petrescue.com

Senha: Admin123

Essas credenciais são utilizadas apenas para fins acadêmicos e de demonstração.

---

## Fluxo público

1. O visitante acessa o catálogo.
2. Consulta os animais cadastrados.
3. Utiliza a pesquisa, se desejar.
4. Abre a página de detalhes de um animal.
5. Registra uma manifestação de interesse em adoção.
6. O sistema valida os dados.
7. A solicitação é armazenada no banco.
8. O sistema apresenta uma confirmação.

---

## Fluxo administrativo

1. O administrador realiza login.
2. Acessa o painel administrativo.
3. Gerencia os animais cadastrados.
4. Pode cadastrar novos animais.
5. Pode editar dados existentes.
6. Pode alterar o status do animal.
7. Pode excluir animais quando permitido pelas regras de integridade.
8. Consulta as solicitações recebidas.
9. Atualiza o status das solicitações.
10. Realiza logout ao finalizar.

---

## Validações e segurança

Foram implementadas medidas básicas de segurança e validação, como:

- autenticação do administrador;
- senha armazenada com hash utilizando bcrypt;
- proteção das rotas administrativas;
- uso de sessão;
- validação de campos obrigatórios;
- consultas parametrizadas ao banco de dados;
- controle dos valores permitidos para os status;
- proteção contra exclusão de animais que possuam solicitações vinculadas;
- uso de variáveis de ambiente para dados sensíveis.

---

## Testes realizados

Foram realizados testes manuais dos principais fluxos da aplicação:

- carregamento da página inicial;
- consulta dos animais cadastrados;
- pesquisa de animais;
- acesso aos detalhes do animal;
- envio de solicitação de adoção;
- persistência da solicitação no MySQL;
- login com credenciais válidas;
- bloqueio da área administrativa sem autenticação;
- cadastro de animal;
- edição de animal;
- alteração do status do animal;
- exclusão de animal;
- visualização das solicitações;
- atualização do status das solicitações;
- logout do administrador.

---

## Vídeo de apresentação

Demonstração das principais funcionalidades da aplicação Pet Rescue:

https://youtu.be/6KizoerqVQw

O vídeo apresenta:

- página inicial e catálogo público;
- pesquisa;
- perfil do animal;
- formulário de interesse em adoção;
- confirmação da solicitação;
- login administrativo;
- gerenciamento de animais;
- cadastro;
- edição;
- alteração de status;
- exclusão;
- gerenciamento das solicitações;
- controle de acesso administrativo.

---

## Arquivo da entrega final

O código-fonte completo da aplicação também está disponibilizado no arquivo zipado.

---

## Privacidade

O projeto utiliza dados fictícios ou conteúdos autorizados para fins acadêmicos e de demonstração.

Os dados coletados no formulário são limitados às informações necessárias para o registro da manifestação de interesse em adoção.

---

## Observação

Projeto desenvolvido exclusivamente para fins acadêmicos.
