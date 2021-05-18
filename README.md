# Flask Login API

## Setup
Para iniciar o projeto da API, utilize o seguinte comando na raiz da pasta:

```bash
pip3 install -r requirements.txt
```

## Executar
Para executar a aplicação, execute o comando abaixo no terminal, com Python 3 em seu bash:

```bash
python run.py
```

## Sobre a API

A API tem duas endpoints principais, `/register` e `/login`, com as seguintes respostas HTTP:

- 400 – Bad Request, quando algum parâmetro foi esquecido no objeto da requisição ou está inválido.
- 403 – Forbidden, quando não há permissão de acesso ao recurso.
- 201 – Created, quando a criação de um recurso foi feita com sucesso.
- 200 – OK, quando a operação foi concluída com sucesso.

### Requisição para a rota /register

Esta rosta recebe o seguinte objeto, com `Content-Type` – `application/json` no header, usando o método `POST`.

```JSON
{
    "email": "teste@mail.com",
    "name": "Teste Santos",
    "password": "a123vsd123",
    "username": "teste"
}
```

A API não aceita a criação de recursos com e-mail ou username duplicados.

### Requisição para a rota /login

Esta rosta recebe um dos seguintes objetos, com `Content-Type` – `application/json` no header, usando o método `POST`.

#### Email & Senha

```JSON
{
    "email": "teste@mail.com",
    "password": "a123vsd123",
}
```

#### Username & Senha

```JSON
{
    "username": "teste",
    "password": "a123vsd123",
}
```