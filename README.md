<img alt="Ignite" src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fad01ee79-762a-4775-bbb6-354f2f42879a%2Fcover-node.js.png?table=block&id=59ccb235-aecd-43a6-a06b-f09a24e7ede8&width=3840&userId=2851198d-6d7e-47d6-b66a-5928d7b96353&cache=v2" />

<h3 align="center">
  Desafio 01: Conceitos do Node.js
</h3>

<p align="center">
  🧠 Aplicação de gerenciamento de tarefas - (ToDo).
</p>

---

## 🚀 Sobre o desafio

Nesse desafio, foi criada uma aplicação backend para treinar o que aprendi até agora no Node.js!

É uma aplicação para gerenciar tarefas (em inglês _todos_). Será permitida a criação de um usuário com `name` e `username`, bem como fazer o CRUD de _todos_:

- Criar um novo _todo_;
- Listar todos os _todos_;
- Alterar o `title` e `deadline` de um _todo_ existente;
- Marcar um _todo_ como feito;
- Excluir um _todo_;

Tudo isso para cada usuário em específico (o `username` será passado pelo header).

---

### 💻 Instalação e Execução do Projeto

- Clone este repositório

```
$ git clone https://github.com/pedrofbaltar/ignite-challenge1
```

- Navegue até o diretório principal do projeto

```
$ cd ignite-challenge1
```

- Instale as dependências com o Yarn

```
$ yarn
```

- Rode a suite de testes

```
$ yarn test
```

- Execute o projeto

```
$ yarn dev
```

---

### Rotas da aplicação (Instruções)

Com o template já clonado e o arquivo `index.js` aberto, você deve completar onde não possui código com o código para atingir os objetivos de cada teste.

#### POST `/users`

A rota deve receber `name`, e `username` dentro do corpo da requisição. Ao cadastrar um novo usuário, ele deve ser armazenado dentro de um objeto no seguinte formato:

```jsx
{
	id: 'uuid', // precisa ser um uuid
	name: 'Pedro Baltar',
	username: 'pedro',
	todos: []
}
```

Certifique-se que o ID seja um UUID, e de sempre iniciar a lista `todos` como um array vazio.

#### GET `/todos`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e retornar uma lista com todas as tarefas desse usuário.

#### POST `/todos`

A rota deve receber `title` e `deadline` dentro do corpo da requisição e, uma propriedade `username` contendo o username do usuário dentro do header da requisição. Ao criar um novo _todo_, ele deve ser armazenada dentro da lista `todos` do usuário que está criando essa tarefa. Cada tarefa deverá estar no seguinte formato: . Certifique-se que o ID seja um UUID.

```jsx
{
	id: 'uuid', // precisa ser um uuid
	title: 'Nome da tarefa',
	done: false,
	deadline: '2021-02-27T00:00:00.000Z',
	created_at: '2021-02-22T00:00:00.000Z'
}
```

**Observação**: Lembre-se de iniciar a propriedade `done` sempre como `false` ao criar um _todo_.

**Dica**: Ao fazer a requisição com o Insomnia ou Postman, preencha a data de `deadline` com o formato `ANO-MÊS-DIA` e ao salvar a tarefa pela rota, faça da seguinte forma:

```jsx
{
	id: 'uuid', // precisa ser um uuid
	title: 'Nome da tarefa',
	done: false,
	deadline: new Date(deadline),
	created_at: new Date()
}
```

Usar `new Date(deadline)` irá realizar a transformação da string "ANO-MÊS-DIA" (por exemplo "2021-02-25") para uma data válida do JavaScript.

#### PUT `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e receber as propriedades `title` e `deadline` dentro do corpo. É preciso alterar **apenas** o `title` e o `deadline` da tarefa que possua o `id` igual ao `id` presente nos parâmetros da rota.

#### PATCH `/todos/:id/done`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e alterar a propriedade `done` para `true` no _todo_ que possuir um `id` igual ao `id` presente nos parâmetros da rota.

#### DELETE `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e excluir o _todo_ que possuir um `id` igual ao `id` presente nos parâmetros da rota.

---

### 🤨 Observações

Você pode ter acesso à documentação no Notion sobre as rotas e testes clicando [aqui](https://www.notion.so/Desafio-01-Conceitos-do-Node-js-59ccb235aecd43a6a06bf09a24e7ede8).

---

### 📜 LIcença

Esse projeto está sob a licença do MIT. Veja o arquivo [LICENSE](./LICENSE).

Feito com 💜 por <a href="https://www.linkedin.com/in/pedro-felipe-baltar-2a26a31ab/">Pedro Felipe Baltar</a>
