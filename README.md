# React Native - Desafio 6 (Novo)

[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/osvaldokalvaitir/react-native-desafio6-novo/blob/master/LICENSE)
![](https://img.shields.io/github/package-json/v/osvaldokalvaitir/react-native-desafio6-novo.svg)
![](https://img.shields.io/github/last-commit/osvaldokalvaitir/react-native-desafio6-novo.svg?color=red)
![](https://img.shields.io/github/languages/top/osvaldokalvaitir/react-native-desafio6-novo.svg?color=yellow)
![](https://img.shields.io/github/languages/count/osvaldokalvaitir/react-native-desafio6-novo.svg?color=lightgrey)
![](https://img.shields.io/github/languages/code-size/osvaldokalvaitir/react-native-desafio6-novo.svg)
![](https://img.shields.io/github/repo-size/osvaldokalvaitir/react-native-desafio6-novo.svg?color=blueviolet)
[![made-for-VSCode](https://img.shields.io/badge/Made%20for-VSCode-1f425f.svg)](https://code.visualstudio.com/)
![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)

Aplicação usando React Native, ESLint, Prettier, EditorConfig, React Navigation, styled-components, React Native Vector Icons, Axios, React Native Async Storage, prop-types, React Native WebView e Reactotron.

## Desafio 06. Aplicação com React Native

Nesse desafio você adicionará novas funcionalidades na aplicação que desenvolvemos ao longo desse módulo.

### Funcionalidades

#### Loading de repositórios

Adicione um indicator de loading utilizando `<ActivityIndicator />` antes de carregar a lista de repositórios favoritados na tela de detalhes do Usuário.

#### Scroll infinito

Adicione uma funcionalidade de scroll infinito na lista de repositórios favoritados. Assim que o usuário chegar nos **20%** do final de lista, busque pelos items na próxima página e adicione na lista. Seu código ficará da seguinte forma:

```js
<Stars
  onEndReachedThreshold={0.2} // Carrega mais itens quando chegar em 20% do fim
  onEndReached={this.loadMore} // Função que carrega mais itens
  // Restante das props
>
```

Para requisitar uma nova página no Github utilize um parâmetro `page` no fim da URL:

```
https://api.github.com/users/diego3g/starred?page=2
```

#### Pull to Refresh

Adicione uma funcionalidade para quando o usuário arrastar a listagem de repositórios favoritados pra baixo atualize a lista resetando o estado, ou seja, volte o estado da paginação para a página 1 exibindo apenas os 30 primeiros itens.

A funcionalidade "Pull to Refresh" existe por padrão na FlatList e pode ser implementada através do seguinte código:

```js
<Stars
  onRefresh={this.refreshList} // Função dispara quando o usuário arrasta a lista pra baixo
  refreshing={this.state.refreshing} // Variável que armazena um estado true/false que representa se a lista está atualizando
  // Restante das props
>
```

#### WebView

Crie uma nova página na aplicação que vai ser acessada quando o usuário clicar em um repositório favoritado, essa página deve conter apenas o Header da aplicação. O conteúdo da página será uma WebView, ou seja, um browser integrado que exibe o atributo `html_url` presente no objeto do repositório que vem da API do Github.

Documentação de utilização da WebView: https://github.com/react-native-community/react-native-webview/blob/master/docs/Getting-Started.md

Exemplo de código:

```js
<WebView
  source={{ uri: repository.html_url }}
  style={{ flex: 1 }}
/>
```

Resultado:

![WebView](/.github/assets/exemplo-web-view.png)


## Índice

- [Capturas de Tela](#capturas-de-tela)

  - [Principal](#principal)

  - [Usuário](#usuário)

  - [Repositório](#repositório)

- [Desenvolvimento](#desenvolvimento)

  - [Configuração do Ambiente](#configuração-do-ambiente)

  - [Instalação do Projeto](#instalação-do-projeto)

  - [Execução do Projeto](#execução-do-projeto)

- [Utilizados no Projeto](#utilizados-no-projeto)

  - [Bibliotecas](#bibliotecas)

  - [APIs](#apis)

  - [Ferramentas](#ferramentas)

## Capturas de Tela

### Principal

![Main](/.github/assets/main.png)
Esta é a primeira tela, onde deve ser informado um usuário existente do GitHub, que ao ser adicionado, ele aparecerá numa lista abaixo.

### Usuário

![User](/.github/assets/user.png)
Nesta tela estão todos os repositórios do GitHub favoritados pelo usuário, podendo também voltar para a tela principal.

### Repositório

![Repository](/.github/assets/repository.png)
Ao clicar em um repositório, será redicionado para esta tela que é uma WebView que exibe seu conteúdo.

## Desenvolvimento

### Configuração do Ambiente

Clique [aqui](https://github.com/osvaldokalvaitir/projects-settings/blob/master/README.md) e siga `Configuração de Ambiente`.

### Instalação do Projeto

Clique [aqui](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/nodejs.md) e siga `Instalação de Projeto`.

### Execução do Projeto

Clique [aqui](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-cli.md) e siga `Execução de Projeto para Desenvolvimento`.

## Utilizados no Projeto

### Bibliotecas

- [Axios](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/axios.md)

- [babel-eslint](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/babel-eslint.md)

- [ESLint](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/eslint.md)

- [eslint-config-prettier](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/eslint-config-prettier.md)

- [eslint-plugin-prettier](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/eslint-plugin-prettier.md)

- [Prettier](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/prettier.md)

- [prop-types](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/prop-types.md)

- [React Native Async Storage](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/@react-native-community-async-storage.md)

- [React Native Gesture Handler](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-gesture-handler.md)

- [React Native Vector Icons](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-vector-icons.md)

- [React Native WebView](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-webview.md)

- [React Navigation](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-navigation.md)

- [React Navigation Stack](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-navigation-stack.md)

- [react-native-cli](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-cli.md)

- [react-native-reanimated](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/react-native-reanimated.md)

- [reactotron-react-native](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/reactotron-react-native.md)

- [styled-components](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/styled-components.md)

### APIs

- **[GitHub](https://api.github.com)**

  - **Rotas**

    - Usuários

      - Busca dados de repositórios pertencente a um usuário

### Ferramentas

- [Reactotron](https://github.com/osvaldokalvaitir/projects-settings/blob/master/inspector/reactotron.md)
