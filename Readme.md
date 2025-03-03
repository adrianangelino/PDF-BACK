
# PDF Extractor - Projeto CPF

## Descrição

Este projeto é composto por duas partes: o **Back-End** e o **Front-End**. 

### Back-End

API construída com **Node.js**, **Express**, **Firebase Admin** e **pdfjs-dist** para processar uploads de arquivos PDF, extrair CPFs e armazená-los no **Firebase Realtime Database**.

### Front-End

Aplicação **Vue.js** que permite ao usuário fazer upload de PDFs, visualizar os CPFs extraídos e gerenciar (editar/excluir) os CPFs armazenados.

## Índice

- [Pré-requisitos](#pré-requisitos)
- [Instalação](#instalação)
- [Configuração](#configuração)
- [Funcionalidades](#funcionalidades)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Uso](#uso)
- [Contribuição](#contribuição)

## Pré-requisitos

- **Node.js** (v12 ou superior)
- **NPM** ou **Yarn**
- Conta no **Firebase** (para configurar o Firebase Realtime Database)
- **Vue CLI** (para desenvolver e rodar o front-end)

## Instalação

### Back-End

1. Clone o repositório:

```bash
git clone <URL do repositório>
cd backend
```

2. Instale as dependências:

```bash
npm install # ou yarn install
```

3. **Configuração do Firebase**:

Coloque o arquivo `serviceAccountKey.json` (credenciais do Firebase) no diretório `src/config`.

Certifique-se de que a URL do Firebase esteja correta no arquivo `index.js`.

4. Iniciar o servidor:

```bash
npm start # ou yarn start
```

O back-end ficará disponível em: `http://localhost:5000`.

### Front-End

1. Navegue até o diretório do front-end:

```bash
cd frontend
```

2. Instale as dependências:

```bash
npm install # ou yarn install
```

3. Iniciar o servidor de desenvolvimento:

```bash
npm run serve # ou yarn serve
```

O front-end geralmente estará disponível em: `http://localhost:8080`.

## Configuração

### Configuração do Back-End

O back-end utiliza as seguintes tecnologias e pacotes:

- **Express**: Framework para criar uma API.
- **Multer**: Middleware para upload de arquivos.
- **pdfjs-dist**: Biblioteca para extrair texto dos arquivos PDF.
- **Firebase Admin**: Para integração com o Firebase Realtime Database.

**Principais endpoints**:

- `POST /api/pdf/upload`: Realiza o upload de um arquivo PDF, extrai os CPFs e os salva no Firebase.
- `GET /api/cpfs`: Retorna todos os CPFs salvos.
- `PUT /api/cpfs/:cpf`: Edita um CPF.
- `DELETE /api/cpfs/:cpf`: Exclui um CPF.

### Configuração do Front-End

O front-end foi desenvolvido com:

- **Vue.js**: Framework para construir a interface.
- **Axios**: Para fazer requisições HTTP à API.
- **Vue Router**: Para navegação entre as páginas.

**Componentes principais**:

- **HomePage.vue**: Página para upload de PDFs e visualização dos CPFs extraídos.
- **CpfList.vue**: Página para listagem, edição e exclusão de CPFs.

## Funcionalidades

- **Upload de PDF**: Permite enviar um arquivo PDF para o back-end para extração dos CPFs.
- **Extração de CPFs**: Utiliza o `pdfjs-dist` para extrair os números de CPF dos arquivos PDF.
- **Armazenamento no Firebase**: Os CPFs extraídos são salvos no Firebase Realtime Database.
- **Visualização dos CPFs**: A interface exibe os CPFs em um container centralizado, com scroll (caso a lista seja longa).
- **Edição e Exclusão**: Permite que o usuário edite ou exclua um CPF diretamente pela interface.

## Estrutura do Projeto

```bash
backend/
├── src/
│   ├── config/                # Configurações (ex.: serviceAccountKey.json para o Firebase)
│   ├── controller/            # Lógica para as rotas da API
│   ├── routes/                # Endpoints da API (ex.: upload PDF, listar/excluir CPFs)
│   ├── services/              # Manipulação de dados (ex.: extração de PDF e CPF)
│   └── (outros arquivos de suporte)
└── index.js                    # Arquivo principal que inicializa o servidor Express

frontend/
├── src/
│   ├── assets/                # Arquivos estáticos (imagens, fontes, etc.)
│   ├── components/            # Componentes Vue.js reutilizáveis
│   ├── views/                 # Páginas da aplicação
│   │   ├── HomePage.vue       # Página para upload de PDF e visualização de CPFs
│   │   └── CpfList.vue        # Página para listagem, edição e exclusão de CPFs
│   ├── router/                # Configuração do Vue Router para navegação entre páginas
│   └── App.vue                # Componente principal da aplicação
├── package.json               # Dependências do front-end
└── README.md                  # Documentação do front-end
```

## Uso

### Back-End

1. Inicie o servidor:

```bash
npm start # ou yarn start
```

O back-end ficará disponível em: `http://localhost:5000`.

### Front-End

1. Inicie o servidor de desenvolvimento:

```bash
npm run serve # ou yarn serve
```

O front-end estará disponível em: `http://localhost:8080`.

## Contribuição

1. Fork este repositório.
2. Crie uma branch para sua funcionalidade (`git checkout -b feature/nova-funcionalidade`).
3. Faça o commit das suas mudanças (`git commit -am 'Adiciona nova funcionalidade'`).
4. Envie a branch para o repositório remoto (`git push origin feature/nova-funcionalidade`).
5. Abra um pull request.
