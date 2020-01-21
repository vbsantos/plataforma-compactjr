# Git

## O que é o Git e GitHub

O **Git** é um sistema open-source de controle de versão utilizado pela grande maioria dos desenvolvedores atualmente. Com ele podemos criar todo histórico de alterações no código do nosso projeto e facilmente voltar para qualquer ponto para saber como o código estava naquela data.

Já o **Github**, que será usado nos exemplos, é um site que permite que você hospede seus repositórios (projetos) usando o Git lá. Outras pessoas podem ver seus projetos, baixa-los, olhar o seu código. E você também pode ver o código dos outros, participar de projetos e _seguir_ outros desenvolvedores.

## Instalando Git

### No Linux

Se você deseja instalar o Git no Linux através de um instalador binário, você pode geralmente fazê-lo através da ferramenta básica de gerenciamento de pacotes que vem com sua distribuição. Para sistemas baseados em Debian:

```shell
sudo apt-get install git-all
```

Para mais opções de instruções de como instalar o Git em outros vários sistemas Unix, veja [aqui](http://git-scm.com/download/linux).

### No Windows

Pra instalar o Git no Windows é só baixar o executável [aqui](https://git-scm.com/download/win) e fazer aquele processo que já conhecemos: **next**, **next** e **finish**. As opções padrão são o que você precisa para começar.

### No MacOS

Um instalador OSX Git é mantido e disponível para download [aqui](http://git-scm.com/download/mac).

### Ajuda após a instalação

```shell
git help   # Modo de uso e principais comandos

git help -a   # Mostra todos os comandos disponíveis
git help add  # explica o comando add
git help commit  # explica o comando commit

git help -g   # Mostra alguns guias do próprio Git
git help tutorial # Abre "A tutorial introduction to Git"
git help everyday # Abre "A useful minimum set of commands for Eveyday Git"
```

## Iniciando ou Retomando um projeto

### Criando um novo repositório

Crie uma nova pasta, abra-a e execute o comando abaixo para criar um novo repositório.

```shell
git init
```

### Clonando um repositório já existente

Crie uma cópia de trabalho em um repositório local executando o comando:

```shell
git clone /caminho/para/o/repositório
```

Quando usar um servidor remoto, seu comando será:

```shell
git clone usuário@servidor:/caminho/para/o/repositório
```

### Conectando repositório à um servidor remoto

Se você não clonou um repositório existente e quer conectar seu repositório a um servidor remoto, você deve adicioná-lo com:

```shell
git remote add origin <servidor>
```

Agora você é capaz de enviar suas alterações para o servidor remoto selecionado.

### Status do repositório

```shell
git status
```

---

### Exemplo

Para clonar o projeto [projeto-trainee](https://github.com/wedersonf/projeto-trainee) do [repositório do Wederson](https://github.com/wedersonf) no GitHub:

```shell
git clone https://github.com/wedersonf/projeto-trainee
```

---

## Fluxo de trabalho

Seus repositórios locais consistem em três "árvores" mantidas pelo git.

1. **Working Directory** que contém todas as pastas e arquivos do projeto com as últimas alterações.
2. **Index/Staging Area** que funciona como uma área temporária.
3. **HEAD/Local** que aponta para o último _commit_ que você fez.

![](/home/armitage/Temporarios/Shared/DRIVE/CompAct Jr./Manual Git/git(3).png)

### Add & Commit

Você pode propor mudanças (adicioná-las ao **Index**) usando:

```shell
git add .
```

Este é o primeiro passo no fluxo de trabalho básico do git. Para realmente confirmar estas mudanças (isto é, fazer um _commit_), use:

```shell
git commit -m "comentários das alterações"
```

Agora o arquivo é enviado para o **HEAD** (repositório local), mas ainda não para o repositório remoto.

### Push

Suas alterações agora estão no **HEAD** da sua cópia de trabalho local. Para enviar estas alterações ao seu repositório remoto, execute:

```shell
git push origin master
```

Altere _master_ para qualquer ramo (_branch_) desejado, enviando suas alterações para ele.

---

### Exemplo

Após modificar o CSS do projeto pra deixar o site responsivo:

```shell
# Manda todos os arquivos de dentro da pasta css pro INDEX
git add css/*
# Manda pro repositório local (INDEX -> HEAD)
git commit -m "Site 100% responsivo"
# Manda do repositório local para o remoto (HEAD -> GitHub)
git push origin master
```

---

## Ramificando

### Branch

O **Branch** seria uma linha de desenvolvimento interna do projeto, ou seja, que apenas colaboradores podem criar e modificar. A ideia é que depois essa linha seja integrada com a linha principal do projeto. Resumindo: seria uma linha temporária de desenvolvimento.

```shell
git branch nome-do-branch  # cria branch
git checkout nome-do-branch  # muda pra branch
```

```shell
git checkout -b nome-do-branch # cria e muda pro branch
```

O **branch _master_** é o branch "padrão" quando você cria um repositório. Use outros branches para desenvolver e mescle-os (**_merge_**) ao branch master após a conclusão.

![Exemplo de ramificação](/home/armitage/Temporarios/Shared/DRIVE/CompAct Jr./Manual Git/git(19).png)

---

### Exemplo

```shell
# Crie e troque para um branch chamado "hotfix-bug53"
git checkout -b hotfix-bug53
# Envie o novo branch para o github
git push origin hotfix-bug53
# Conserte o bug
git add javascript/main.js
git commit -m "bug na função da animação corrigido [bug53]"
# Volta pro ramo/branch principal
git checkout master
# E faz o merge pra corrigir o bug
git merge hotfix-bug53
# Agora que a correção foi feita o branch pode ser deletado
git branch -d hotfix-bug53
# E a versão corrigida pode ser enviada para o github
git push origin master
```

---

### Fork

O **Fork** seria uma linha que partiu de um projeto base por alguém que não era colaborador do projeto original. A ideia é que depois essa linha seja integrada ou não ao projeto principal, inclusive essa linha pode se tornar um projeto independente que tem apenas um core/base em comum com o projeto original.

![](/home/armitage/Temporarios/Shared/DRIVE/CompAct Jr./Manual Git/git(16).png)

## Atualizar e Unir branchs

O **fetch** puxa as atualizações mais recentes do seu repositório, porém ele não faz o merge com o seu repositório local. É como se o git soubesse que você está atrasado, mas te dá a escolha de você mesmo fazer as atualizações.

Já o **pull** é um **fetch** seguido de um **merge**. Ele puxa todas as atualizações e já adiciona elas no seu repositório local. Nesse caso se acontecer algum conflito o git vai te avisar para você corrigir manualmente.

O **pull** é o mais comum de ser utilizado. é uma boa prática sempre antes de começar a trabalhar (Caso esteja trabalhando em uma branch compartilhada com outras pessoas) de dar um git pull no início do trabalho.

![](/home/armitage/Temporarios/Shared/DRIVE/CompAct Jr./Manual Git/git(23).png)

### Atualizar repositório

Para atualizar seu repositório local com a mais nova versão (do repositório remoto), execute **git pull** na sua pasta de trabalho para _obter_ a versão mais nova e _fazer merge_ (mesclar) com as alterações locais.

```shell
git pull
```

### Unir branchs

Para _juntar_ um outro branch ao seu branch ativo/atual, use:

```shell
git merge <nome_do_branch>
```

Em ambos os casos (**pull** e **merge**) o git tenta fazer o merge das alterações automaticamente.

Entretanto, o **merge** nem sempre é possível e resulta em conflitos. Você é responsável por fazer o **merge** destes conflitos manualmente editando os arquivos exibidos pelo git.

## Sobrescrever alterações locais

No caso de você ter feito algo errado no seu projeto, você pode sobrescrever as alterações locais usando o comando:

```shell
git checkout -- <nome_do_arquivo>
```

O qual substitui as alterações no seu **Working Directory** com o conteúdo mais recente do **HEAD**. Alterações já adicionadas ao index, bem como novos arquivos serão mantidos.

Se ao invés disso você deseja remover todas as alterações e _commits_ locais, recupere o histórico mais recente do servidor e aponte para seu branch master local desta forma

```shell
git fetch origin
git reset --hard origin/master
```

## Referências

- Instaladores:
  - Linux: <http://git-scm.com/download/linux>
  - Windows: <https://git-scm.com/download/windows>
  - MacOS: <https://git-scm.com/download/mac>
- <https://git-scm.com/docs/user-manual.html>
- <https://rogerdudler.github.io/git-guide/index.pt_BR.html>
- <https://help.github.com/pt>
- Ramificação
  - <https://git-scm.com/book/pt-br/v1/Ramifica%C3%A7%C3%A3o-Branching-no-Git-B%C3%A1sico-de-Branch-e-Merge>
- visual guide: http://marklodato.github.io/visual-git-guide/index-en.html
