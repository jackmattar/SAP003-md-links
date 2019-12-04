# Markdown Links

## Índice

* [1. Prefácio](#1-prefácio)
* [2. Resumo do projeto](#2-resumo-do-projeto)
* [3. Instalação e Uso](#3-instalação-e-uso)
* [4. Considerações Finais](#4-considerações-finais)

***

## 1. Prefácio

[Markdown](https://pt.wikipedia.org/wiki/Markdown) é uma linguagem de marcação
muito popular entre os programadores. É usada em muitas plataformas que
manipulam texto (GitHub, fórum, blogs e etc), e é muito comum encontrar arquivos
com este formato em qualquer repositório (começando pelo tradicional
`README.md`).

Os arquivos `Markdown` normalmente contém _links_ que muitas vezes estão
quebrados, ou que já não são válidos e isso prejudica muito o valor da
informação que está ali.

Então criamos uma biblioteca capaz de encontrar e validar esses links.


## 2. Resumo do projeto

O projeto é uma biblioteca que pode ser executada por uma CLI (Command Line Interface - Interface de Linha de Comando)
que retorna um array de objetos dos links contidos em um arquivo Markdown(.md) e como opção pode validar os mesmos.

## 3. Instalação e Uso

### Como Instalar

Você pode instalar a biblioteca usando o seguinte comando no seu terminal:

`$ npm install -g jackmattar/SAP003-md-links`

Talvez você precise de autorização de administrador para instalar.
Caso ocorra um erro de permissão na instalação tente:

`$ sudo npm install -g jackmattar/SAP003-md-links`

### Como usar

#### Usando em um arquivo .js

Para usar a biblioteca em seus projetos JavaScript, faça um `require` no seu arquivo da seguinte forma:

```js
const mdLinks = require("md-links");

mdLinks(path, option)
  .then(links => {
    console.log(links)
  })
  .catch(console.error);
```
`path`: Rota absoluta ou relativa ao arquivo.

`option`: Um objeto com a propriedade validate, cujo valor é um booleano,
`{validate: true}` ou `{validate: false}`.

#### CLI (Command Line Interface - Interface de Linha de Comando)

Você também pode usar com uma CLI direto no seu terminal, da seguinte maneira:

`$ md-links caminho/do/arquivo.md`

#### Validando os links

Você pode validar os links pela CLI usando:
`$ md-links caminho/do/arquivo.md  --validate`

ou passando o objeto no lugar de option

```js
//option = {validate: true} ou {validate: false}
mdLinks('./exemplo.md', {validate: true})
  .then(links => {
    console.log(links)
  })
  .catch(console.error);
```

#### Retorno esperado

`
[
  {
    href: 'https://pt.wikipedia.org/wiki/Markdown',
    text: 'Markdown',
    status: 200
  }
  {
    href: 'https://google.com',
    text: Google,
    status: 200
  }
]

`

## 4. Considerações Finais

Esse projeto foi desenvolvido como parte do currículo do Bootcamp Laboratória Brasil, e as tecnologias 
usadas foram:

* JavaScript
* Node.js
* Eslint
* Jest
* node-fetch
* fs

Projeto desenvolvido por Jackeline Mattar.


