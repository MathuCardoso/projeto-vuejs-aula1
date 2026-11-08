# Pizza Vue 🍕

Projeto de exemplo desenvolvido para o mini curso da disciplina de **Projeto de Extensão** do 4º período do curso de **Análise e Desenvolvimento de Sistemas**.

A aplicação simula o formulário de pedido de uma pizzaria: o usuário informa o nome, escolhe o tamanho, os sabores e a quantidade de pizzas, e acompanha o resumo do pedido com o valor total atualizado em tempo real.

## Funcionalidades

- Campo para informar o nome do cliente
- Seleção do tamanho da pizza (Pequeno, Médio e Grande)
- Seleção de múltiplos sabores
- Controle de quantidade (de 1 a 10 pizzas)
- Resumo do pedido com cálculo automático do total
- Layout responsivo para telas menores

## Tecnologias utilizadas

- [Vue.js 3](https://vuejs.org/) (Composition API com `<script setup>`)
- [Vite](https://vite.dev/)
- JavaScript, HTML e CSS

## Requisitos

Antes de executar o projeto, é necessário ter instalado:

- **Node.js** na versão `22.18.0` ou superior (ou `24.12.0` ou superior)
- **npm** (instalado junto com o Node.js)
- Um navegador moderno (Chrome, Edge, Firefox ou Brave)
- Um editor de código, de preferência o [VS Code](https://code.visualstudio.com/) com a extensão [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar)

Para verificar se o Node.js e o npm estão instalados, execute no terminal:

```sh
node --version
npm --version
```

## Como executar o projeto

1. Clone ou baixe este repositório e abra a pasta do projeto no terminal.

2. Instale as dependências:

```sh
npm install
```

3. Inicie o servidor de desenvolvimento:

```sh
npm run dev
```

4. Acesse o endereço exibido no terminal (normalmente `http://localhost:5173`).

O servidor possui *hot reload*: as alterações no código são refletidas automaticamente no navegador.

### Outros comandos

| Comando | Descrição |
| --- | --- |
| `npm run dev` | Inicia o servidor de desenvolvimento |
| `npm run build` | Gera a versão de produção na pasta `dist` |
| `npm run preview` | Visualiza localmente a versão de produção gerada |

## Estrutura do projeto

```text
aula-dia1/
├── public/          # Arquivos estáticos (favicon)
├── src/
│   ├── App.vue      # Componente principal com o formulário e o resumo do pedido
│   ├── main.js      # Ponto de entrada da aplicação Vue
│   └── style.css    # Estilos da aplicação
├── index.html       # Página HTML base
├── package.json     # Dependências e scripts do projeto
└── vite.config.js   # Configuração do Vite
```

## Licença

Projeto de uso educacional, desenvolvido para fins de ensino.
