# 🚀 Finance Control

**Sistema de gerenciamento de finanças,** feito em TypeScript com deploy no google Cloud, integrado com o Gemini como um assistente financeiro.

## Funcionalidades

A API oferece os seguintes endpoints para interação:

Front-End -> 

### Cadastro de compras

* **`POST /checkout`**
* **`GET /purchases`**
* **`GET /purchases/id`**: **Esta rota requer autenticação.**

### Gerenciamento de transações

* **`GET /transactions`**
* **`POST /transactions`**
* **`GET /transactions/id`**

* ### Products -> Consumo de outra api

* **`GET /products`**

## 🛠️ Conteúdo e Tecnologias

O projeto foi estruturado com base nos seguintes conceitos e ferramentas, visando escalabilidade, manutenibilidade e segurança:

* **MongoDB - Como banco principal**
* * **Docker - Como banco de teste**
* **Cloud Run**
* **Clean Architecture**
* **TypeScript**
* **Express.js**
* **Google Cloud Platform**
* **Cors**
* **Testes com Jest**

---

## Acessando:

Siga estas instruções para ter uma cópia do projeto funcionando na sua máquina local para desenvolvimento e testes.

### Pré-requisitos

Certifique-se de ter as seguintes ferramentas instaladas:

* **Node.js** (versão LTS recomendada)
* **npm** ou **Yarn** (gerenciador de pacotes)
* **TypeScript** (geralmente instalado junto com o Node.js ou via npm)
* **MongoDB Instance**: Uma instância do MongoDB (local ou na nuvem, como MongoDB Atlas) configurada e acessível. Você precisará de uma URI de conexão.

### Instalação

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/feliixjuliana/pretalab-api.git
    ```
2.  **Navegue até o diretório do projeto:**
    ```bash
    cd Projeto2-Clean-Architecture-Aprofunda
    ```
3.  **Instale as dependências:**
    ```bash
    npm install
    ```
4.  **Configure as variáveis de ambiente:**
    Crie um arquivo `.env` na raiz do diretório `api-clean-architecture` e adicione a URI de conexão do seu MongoDB e uma chave secreta para o JWT:

    ```
    MONGO_URL = 
    PORT = 
    GEMINI_API_KEY = 
    NODE_ENV =
    ```

5.  **Execute o projeto:**
    ```bash
    npm run DEV
    ```
    O servidor deverá iniciar, geralmente em `http://localhost:3000`.

---

## 📸 Demonstração

### Cadastrando compra

* **Endpoint:**
* Local:`POST http://localhost:3000/checkout`
* **Body (JSON):**
    ```json
    {
      "total": 7850,
      "items": [
      {
        "productId": "1",
        "quantity": 1,
        "name": "Notebook Gamer Pro",
        "price": 7500,
        "_id": "68a4a5b91c6914647640b214"
      }
    ]
    }
    ```

### Interação com Gemini

* **Endpoint:**
* Local:`POST http://localhost:3000/chat`

* **Body (JSON):**
    ```json
    {
        "prompt": "Qual o meu total de gasto?"
    }
    ```

### Cadastrando transações

* **Endpoint:**
* Local:`POST http://localhost:3000/transactions`

* **Body (JSON):**
    ```json
    {
      "description": "Salário de Julho",
      "amount": 5000,
      "type": "income",
      "category": "Salário"
    }
    ```
