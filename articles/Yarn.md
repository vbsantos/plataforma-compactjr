![yarn-kitten-full](https://raw.githubusercontent.com/diegoeis/tableless-static-images/master/2016/10/yarn-kitten-full.png)

# Yarn

O **NPM** é o **Gerenciador de Pacotes do Node** (*Node Package Manager*) que vem junto com ele e que é muito útil no desenvolvimento Node.

O **Yarn** é o **Gerenciador de Pacotes do Node** feito pelo **Facebook**, que vem com a proposta de ser mais rápido, seguro e confiável que o NPM. O Yarn é open source, e nasceu com a colaboração, também, das empresas **Exponent**, **Google**, e **Tilde**.

## Comandos

### Instalação

```
npm install -g yarn
```

### Inicialização

```
yarn init
```

Este comando irá gerar um arquivo **package.json**:

```json
{
	"name": "Yarn",
	"version": "1.0.0",
	"main": "index.js",
	"license": "MIT"
}
```

### Adicionando uma dependência ao projeto

```
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

#### Parâmetros importantes

- Usar `--dev` ou `-D` instalará um ou mais pacotes nas suas [`devDependencies`](https://yarnpkg.com/pt-BR/docs/dependency-types#toc-dev-dependencies) (dependências de desenvolvimento).
- Usar `--peer` ou `-P` instalará um ou mais pacotes nas suas [`peerDependencies`](https://yarnpkg.com/pt-BR/docs/dependency-types#toc-peer-dependencies) (dependências “parceiras”).
- Usar `--optional` ou `-O` instalará um ou mais pacotes nas suas [`optionalDependencies`](https://yarnpkg.com/pt-BR/docs/dependency-types#toc-optional-dependencies) (dependências opcionais).
- Usar `--exact` ou `-E` instala os pacote nas suas versões exatas. O padrão é usar o lançamento mais recente com a mesma versão “maior”. Por exemplo, `yarn add foo@1.2.3` aceitaria a versão `1.9.1`, porém `yarn add foo@1.2.3 --exact` só aceitaria a versão `1.2.3`.
- Usar `--tilde` ou `-T` instala o lançamento mais recente dos pacotes que tenha a mesma versão “menor”. O padrão é usar o lançamento mais recente com a mesma versão “maior”. Por exemplo, `yarn add foo@1.2.3 --tilde` aceitaria `1.2.9` mas não `1.3.0`.

### Fazendo update

```
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

### Desfazendo as coisas

```
yarn remove [package]
```

### Instalando as dependências

Em um diretório que exista o **package.json** cria e popula a pasta **node_modules**

```
yarn
```

ou

```
yarn install
```

### Global

É um prefixo usado para vários comandos como `add`, `bin`, `list` e `remove`. Eles têm o mesmo comportamento que suas versões normais, exceto que **usam um diretório global** para salvar os pacotes.

```
yarn global add
```

O comando `global` torna arquivos executáveis disponíveis para uso pelo seu sistema operacional.

```
$ yarn global add create-react-app --prefix /usr/local
# o comando`create-react-app` agora está disponível globalmente:
$ which create-react-app
$ /usr/local/bin/create-react-app
$ create-react-app
```

### Create

Este comando é uma abreviação que ajuda você a fazer duas coisas ao mesmo tempo:

- Instalar o `create-` globalmente, ou atualizar o pacote para a versão mais recente, caso já exista
- Roda o executável localizado no campo `bin` do `package.json` do starter kit, encaminhando quaisquer argumentos para ele

Por exemplo:

```
$ yarn create react-app my-app
```

é equivalente a:

```
$ yarn global add create-react-app
$ create-react-app my-app
```

### Outras funcionalidades

#### Lock file

Além do package.json, o Yarn cria, na pasta raíz do projeto, um arquivo yarn.lock, que trata de listar as bibliotecas “originais” do projeto, um sistema bem semelhante ao do composer.

#### Fazendo uma limpeza

Outro recurso interessante é o mecanismo de limpeza de dependências, ao executar o comando:

```
yarn clean
```

O Yarn vasculha as dependências e verifica tudo aquilo que não está sendo utilizado e exporta para um arquivo **.yarnclean**. Caso você tenha este arquivo em sua pasta raíz, quando executar o **yarn install**, ele vai instalar as dependências de forma mais limpa.

#### Self-update

Para atualizar o Yarn, basta digitar no console:

```
yarn self-update
```

ou, caso queira especificar a versão:

```
yarn self-update 0.1.2
```

