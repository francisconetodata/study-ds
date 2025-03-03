# Manual Completo de Git e GitHub

## Introdução ao Controlo de Versões

### O que é Controlo de Versões?

Controlo de versões, também conhecido como controlo de código fonte ou gestão de revisões, é um sistema que regista as alterações num ficheiro ou conjunto de ficheiros ao longo do tempo, de modo a que possa recuperar versões específicas mais tarde. Imagine que está a escrever um livro; com o controlo de versões, pode voltar a uma versão anterior do livro caso cometa um erro ou queira reverter para uma versão anterior.

### Por que usar Controlo de Versões?

O controlo de versões oferece inúmeras vantagens, especialmente em projetos de desenvolvimento de software:

  * **Histórico de Alterações:** Permite rastrear todas as alterações feitas ao código, quem as fez e quando.
  * **Reversão:** Facilita a reversão para versões anteriores do código em caso de erros ou problemas.
  * **Colaboração:** Permite que várias pessoas trabalhem no mesmo projeto simultaneamente, gerindo conflitos e integrando alterações de forma eficiente.
  * **Branches (Ramificações):** Permite desenvolver novas funcionalidades ou corrigir bugs em isolamento, sem afetar a versão principal do projeto.
  * **Backup e Restauro:** Serve como um sistema de backup do seu projeto, permitindo restaurar o projeto para qualquer ponto no tempo.

### Tipos de Sistemas de Controlo de Versões

Existem diferentes tipos de sistemas de controlo de versões, sendo os principais:

  * **Sistemas de Controlo de Versões Centralizados (CVCS):** Como o SVN (Subversion) ou CVS. Nestes sistemas, existe um servidor central que armazena todas as versões dos ficheiros, e os utilizadores fazem o checkout da versão mais recente para trabalhar.

  * **Sistemas de Controlo de Versões Distribuídos (DVCS):** Como o Git e Mercurial. Em sistemas distribuídos, cada utilizador tem uma cópia completa do repositório e do seu histórico. Isto permite trabalhar offline e oferece maior flexibilidade e resiliência.

### Introdução ao Git

Git é um sistema de controlo de versões distribuído, amplamente utilizado no desenvolvimento de software moderno. Criado por Linus Torvalds (também criador do Linux), o Git é conhecido pela sua velocidade, eficiência e flexibilidade. É a ferramenta de controlo de versões mais popular e a base para plataformas como o GitHub, GitLab e Bitbucket.

## Instalação e Configuração do Git

### Instalar o Git

A instalação do Git varia dependendo do seu sistema operativo.

  * **Windows:**

    1.  Descarregue o instalador do Git para Windows em [https://git-scm.com/download/win](https://www.google.com/url?sa=E&source=gmail&q=https://git-scm.com/download/win).
    2.  Execute o instalador e siga as instruções. Geralmente, as opções padrão são suficientes.

  * **macOS:**

      * Se tiver o Homebrew instalado, pode usar o terminal:
        ```bash
        brew install git
        ```
      * Ou descarregue o instalador do Git para macOS em [https://git-scm.com/download/mac](https://www.google.com/url?sa=E&source=gmail&q=https://git-scm.com/download/mac).

  * **Linux (Debian/Ubuntu):**

    ```bash
    sudo apt-get update
    sudo apt-get install git
    ```

  * **Linux (Fedora/CentOS):**

    ```bash
    sudo yum install git
    ```

Após a instalação, pode verificar se o Git foi instalado corretamente abrindo o terminal ou linha de comandos e digitando:

```bash
git --version
```

Deverá ver a versão do Git instalada.

### Configuração Básica do Git

Após instalar o Git, é importante configurar o seu nome de utilizador e email. Estas informações serão associadas aos seus commits (registos de alterações).

1.  **Configurar o nome de utilizador:**

    ```bash
    git config --global user.name "Seu Nome Completo"
    ```

    Substitua `"Seu Nome Completo"` pelo seu nome.

2.  **Configurar o email:**

    ```bash
    git config --global user.email "seuemail@example.com"
    ```

    Substitua `"seuemail@example.com"` pelo seu endereço de email.

3.  **Verificar a configuração:**
    Para verificar as configurações, pode usar:

    ```bash
    git config --list
    ```

    Isto irá mostrar uma lista de todas as configurações do Git.

## Comandos Básicos do Git

### `git init`: Inicializar um Repositório

Para começar a usar o Git num projeto existente ou num novo projeto, precisa de inicializar um repositório Git. Navegue até à pasta raiz do seu projeto no terminal e execute:

```bash
git init
```

Este comando cria um subdiretório `.git` na pasta do projeto. Este diretório contém todos os metadados e histórico do repositório Git.

### `git clone`: Clonar um Repositório Existente

Para obter uma cópia de um repositório Git já existente (por exemplo, de um repositório remoto no GitHub), use o comando `git clone`.

```bash
git clone <URL_do_repositorio>
```

Substitua `<URL_do_repositorio>` pelo URL do repositório que deseja clonar. Por exemplo:

```bash
git clone [https://github.com/usuário/repositorio.git](https://www.google.com/search?q=https://github.com/usu%C3%A1rio/repositorio.git)
```

Isto irá criar uma pasta com o nome do repositório e descarregar todos os ficheiros e histórico do repositório para essa pasta.

### `git config`: Configurar o Git

Já vimos como configurar o nome de utilizador e email. O comando `git config` é usado para configurar várias opções do Git. Usamos `--global` para aplicar a configuração a todos os repositórios no seu sistema. Se quiser configurar opções específicas para um repositório local, pode executar `git config` sem `--global` dentro da pasta do repositório.

### `git status`: Verificar o Estado do Repositório

O comando `git status` mostra o estado do seu repositório de trabalho. Indica quais ficheiros foram modificados, quais estão em staging (preparados para commit) e quais ficheiros o Git não está a rastrear.

```bash
git status
```

### `git add`: Adicionar Alterações ao Staging

Quando modifica ficheiros no seu repositório de trabalho, o Git regista estas alterações, mas elas ainda não estão prontas para serem guardadas no histórico. Primeiro, precisa de adicionar as alterações ao "staging area" (área de preparação) usando `git add`.

  * **Adicionar um ficheiro específico:**
    ```bash
    git add <nome_do_ficheiro>
    ```
  * **Adicionar todos os ficheiros modificados e novos:**
    ```bash
    git add .
    ```

### `git commit`: Guardar Alterações no Histórico

Após adicionar as alterações ao staging, use `git commit` para guardar um snapshot das alterações no histórico do repositório. Cada commit deve ter uma mensagem descritiva que explique as alterações feitas.

```bash
git commit -m "Mensagem descritiva do commit"
```

Substitua `"Mensagem descritiva do commit"` por uma mensagem clara e concisa.

### `git log`: Ver o Histórico de Commits

Para ver o histórico de commits do seu repositório, use o comando `git log`.

```bash
git log
```

Isto mostra uma lista de commits, com informações como o autor, data e mensagem de cada commit. Pode usar várias opções com `git log` para formatar e filtrar o histórico.

  * **Ver o histórico de commits numa linha:**
    ```bash
    git log --oneline
    ```
  * **Ver o histórico de commits com o diff das alterações:**
    ```bash
    git log -p
    ```

### `git diff`: Ver Diferenças

O comando `git diff` é usado para ver as diferenças entre diferentes estados do seu repositório:

  * **Ver as alterações não staged (entre a área de trabalho e staging):**
    ```bash
    git diff
    ```
  * **Ver as alterações staged (entre staging e o último commit):**
    ```bash
    git diff --staged
    ```
  * **Ver as diferenças entre dois commits:**
    ```bash
    git diff <commit1> <commit2>
    ```

## Branching e Merging (Ramificações e Junção)

### O que são Branches?

Branches (ramificações) são uma funcionalidade poderosa do Git que permite criar linhas de desenvolvimento paralelas. Uma branch é essencialmente um ponteiro móvel para um commit. A branch `main` (ou `master` em repositórios mais antigos) é a branch principal.

### Por que usar Branches?

  * **Desenvolvimento de funcionalidades:** Permite desenvolver novas funcionalidades em branches separadas, sem instabilizar a branch principal.
  * **Correção de bugs:** Permite corrigir bugs em branches dedicadas, isolando as alterações.
  * **Experiências:** Permite experimentar novas ideias sem risco para o código principal.

### `git branch`: Gerir Branches

  * **Listar branches:**

    ```bash
    git branch
    ```

    Isto lista todas as branches locais. A branch atual é marcada com um `*`.

  * **Criar uma nova branch:**

    ```bash
    git branch <nome_da_branch>
    ```

    Substitua `<nome_da_branch>` pelo nome que deseja dar à nova branch.

  * **Eliminar uma branch local:**

    ```bash
    git branch -d <nome_da_branch>
    ```

    Use `-D` em vez de `-d` para forçar a eliminação, mesmo que a branch não tenha sido merged.

### `git checkout`: Mudar de Branch

Para mudar para uma branch diferente e começar a trabalhar nela, use `git checkout`.

```bash
git checkout <nome_da_branch>
```

Substitua `<nome_da_branch>` pela branch para a qual deseja mudar.

Para criar e mudar para uma nova branch num só comando, pode usar:

```bash
git checkout -b <nome_da_nova_branch>
```

### `git merge`: Juntar Branches

Após desenvolver numa branch separada, eventualmente vai querer juntar as alterações de volta à branch principal (ou outra branch). Use `git merge` para fazer isso.

1.  **Mude para a branch onde quer juntar as alterações (ex: `main`):**

    ```bash
    git checkout main
    ```

2.  **Execute o merge da branch que quer juntar:**

    ```bash
    git merge <nome_da_branch_a_juntar>
    ```

### Conflitos de Merge

Conflitos de merge ocorrem quando o Git não consegue juntar automaticamente as alterações de duas branches, geralmente porque o mesmo ficheiro foi alterado em ambas as branches de formas incompatíveis. Quando ocorre um conflito, o Git marca os ficheiros com conflitos, e precisa de os resolver manualmente:

1.  **Abra o ficheiro com conflito:** O ficheiro terá marcadores de conflito como `<<<<<<<`, `=======`, e `>>>>>>>`.
2.  **Edite o ficheiro:** Escolha quais alterações quer manter (da branch atual ou da branch que está a ser merged) e remova os marcadores de conflito.
3.  **Adicione o ficheiro resolvido ao staging:**
    ```bash
    git add <ficheiro_resolvido>
    ```
4.  **Finalize o merge:**
    ```bash
    git commit -m "Resolver conflitos de merge"
    ```

## Repositórios Remotos

### O que são Repositórios Remotos?

Repositórios remotos são versões do seu repositório que estão hospedadas noutro lugar, geralmente num servidor na internet ou numa rede. Os repositórios remotos são essenciais para colaboração, permitindo que várias pessoas trabalhem no mesmo projeto, partilhando e sincronizando as suas alterações. Plataformas como o GitHub, GitLab e Bitbucket fornecem serviços de hospedagem de repositórios Git remotos.

### Adicionar um Repositório Remoto

Quando clona um repositório, um remoto chamado `origin` é automaticamente configurado para apontar para o repositório de onde clonou. Para adicionar um novo remoto (por exemplo, um repositório remoto que criou no GitHub), use `git remote add`.

```bash
git remote add <nome_do_remoto> <URL_do_repositorio_remoto>
```

  * `<nome_do_remoto>`: Um nome curto para o remoto, geralmente `origin`.
  * `<URL_do_repositorio_remoto>`: O URL do repositório remoto (ex: do GitHub).

Exemplo:

```bash
git remote add origin [https://github.com/seu_usuario/seu_repositorio.git](https://www.google.com/search?q=https://github.com/seu_usuario/seu_repositorio.git)
```

### `git remote`: Gerir Repositórios Remotos

  * **Listar remotos:**

    ```bash
    git remote -v
    ```

    `-v` (verbose) mostra os URLs dos remotos.

  * **Remover um remoto:**

    ```bash
    git remote remove <nome_do_remoto>
    ```

  * **Renomear um remoto:**

    ```bash
    git remote rename <nome_antigo> <nome_novo>
    ```

### `git push`: Enviar Commits para o Remoto

Para enviar os seus commits locais para um repositório remoto, use `git push`.

```bash
git push <nome_do_remoto> <nome_da_branch_local>:<nome_da_branch_remota>
```

  * `<nome_do_remoto>`: O nome do remoto (ex: `origin`).
  * `<nome_da_branch_local>`: A branch local que quer enviar (ex: `main`).
  * `<nome_da_branch_remota>`: A branch remota para onde quer enviar (geralmente igual à local, ex: `main`).

Para a primeira vez que envia uma branch local para um remoto, pode usar uma forma mais simples:

```bash
git push -u origin <nome_da_branch_local>
```

`-u` configura a branch local para rastrear a branch remota, o que simplifica pushes e pulls futuros.

### `git pull`: Receber Alterações do Remoto

Para receber alterações de um repositório remoto e juntá-las à sua branch local atual, use `git pull`.

```bash
git pull <nome_do_remoto> <nome_da_branch_remota>
```

Se a sua branch local estiver configurada para rastrear uma branch remota (com `-u` no `push`), pode simplesmente usar:

```bash
git pull
```

### `git fetch`: Buscar Alterações do Remoto

`git fetch` busca as alterações do remoto, mas não as junta automaticamente à sua branch local. As alterações buscadas ficam disponíveis como uma branch remota (ex: `origin/main`). Pode então verificar as alterações e decidir como e quando juntá-las (com `git merge` ou `git rebase`).

```bash
git fetch <nome_do_remoto>
```

## Desfazer Alterações

### `git revert`: Reverter um Commit

`git revert` cria um novo commit que desfaz as alterações introduzidas por um commit específico. É uma forma segura de desfazer alterações, pois mantém o histórico completo.

```bash
git revert <hash_do_commit>
```

Substitua `<hash_do_commit>` pelo hash do commit que deseja reverter.

### `git reset`: Resetar para um Estado Anterior

`git reset` move a branch atual para um commit anterior. Pode ser perigoso se usado incorretamente, pois pode perder commits. Existem três modos de `git reset`:

  * **`--soft`:** Mantém as alterações no staging e na área de trabalho.
    ```bash
    git reset --soft <hash_do_commit>
    ```
  * **`--mixed` (padrão):** Mantém as alterações na área de trabalho, mas remove-as do staging.
    ```bash
    git reset --mixed <hash_do_commit>
    ```
  * **`--hard`:** Remove todas as alterações da área de trabalho, staging e histórico após o commit especificado. **Use com muita cautela, pois pode perder trabalho não commited.**
    ```bash
    git reset --hard <hash_do_commit>
    ```

### `git checkout -- <ficheiro>`: Descartar Alterações Num Ficheiro

Para descartar alterações não commited num ficheiro específico e restaurá-lo à versão do último commit, use:

```bash
git checkout -- <nome_do_ficheiro>
```

## Ignorar Ficheiros

### Ficheiro `.gitignore`

Para evitar que certos ficheiros (ex: ficheiros temporários, ficheiros de configuração local, pastas de dependências) sejam rastreados pelo Git, pode criar um ficheiro `.gitignore` na raiz do seu repositório. O Git ignora ficheiros e padrões especificados neste ficheiro.

  * **Criar o ficheiro `.gitignore`:** Na raiz do seu repositório, crie um ficheiro de texto com o nome `.gitignore`.
  * **Adicionar padrões ao `.gitignore`:** Cada linha no `.gitignore` especifica um padrão para ficheiros ou pastas a serem ignorados.

Exemplos de padrões no `.gitignore`:

```gitignore
# Ignorar ficheiros .log
*.log

# Ignorar pasta node_modules
node_modules/

# Ignorar ficheiros temporários iniciados com temp_
temp_*

# Ignorar o ficheiro específico config.local.json na raiz
config.local.json
```

## Introdução ao GitHub

### O que é GitHub?

GitHub é uma plataforma de hospedagem de repositórios Git baseada na web, que oferece funcionalidades adicionais para colaboração, gestão de projetos e desenvolvimento de software. É a maior e mais popular plataforma de repositórios Git remotos.

### Por que usar GitHub?

  * **Hospedagem de Repositórios:** Permite hospedar os seus repositórios Git remotamente, facilitando o backup e o acesso de qualquer lugar.
  * **Colaboração:** Oferece ferramentas para colaboração em equipa, como Pull Requests, Issues e Project Boards.
  * **Comunidade:** É uma vasta comunidade de desenvolvedores, ideal para descobrir projetos open source, contribuir e construir um portfólio.
  * **Funcionalidades Adicionais:** Oferece funcionalidades como GitHub Pages (para hospedar websites estáticos), GitHub Actions (para automação e CI/CD), e GitHub Projects (para gestão de projetos).

### GitHub vs Git

  * **Git:** É o sistema de controlo de versões em si, a ferramenta de linha de comandos para gerir o histórico e as alterações do código.
  * **GitHub:** É uma plataforma online que utiliza o Git como sistema de controlo de versões e adiciona funcionalidades para hospedagem, colaboração e gestão de projetos.

Em resumo, Git é a ferramenta, e GitHub é um serviço que usa essa ferramenta e a expande com funcionalidades web.

### Criar uma Conta no GitHub

1.  Aceda ao site do GitHub: [https://github.com/](https://www.google.com/url?sa=E&source=gmail&q=https://github.com/).
2.  Clique em "Sign up" ou "Registar".
3.  Siga as instruções para criar uma conta, escolhendo um nome de utilizador, email e password.

## Criar um Repositório no GitHub

### Criar um Novo Repositório

1.  Após iniciar sessão no GitHub, clique no botão "+" no canto superior direito e selecione "New repository" ("Novo repositório").
2.  Na página "Create a new repository" ("Criar um novo repositório"):
      * **Repository name** ("Nome do repositório"): Dê um nome ao seu repositório.
      * **Description** ("Descrição") (opcional): Adicione uma descrição para o seu repositório.
      * **Public ou Private** ("Público ou Privado"): Escolha se o repositório será público (visível para todos) ou privado (visível apenas para si e colaboradores que convidar).
      * **Initialize this repository with:** (Inicializar este repositório com):
          * **Add a README file** ("Adicionar um ficheiro README"): Recomendado para incluir uma descrição do projeto.
          * **Add .gitignore** ("Adicionar .gitignore"): Pode escolher um template para a sua linguagem de programação.
          * **Choose a license** ("Escolher uma licença"): Escolha uma licença open source se for relevante.
3.  Clique em "Create repository" ("Criar repositório").

### Trabalhar com Repositórios Remotos no GitHub

### Clonar um Repositório do GitHub

Já vimos o comando `git clone`. Para clonar um repositório do GitHub, copie o URL do repositório no GitHub (botão "Code" -\> "HTTPS" ou "SSH") e use:

```bash
git clone <URL_do_repositorio_GitHub>
```

### Enviar um Repositório Local para o GitHub

Se já tem um repositório Git local e quer enviá-lo para o GitHub:

1.  **Crie um repositório vazio no GitHub** (sem inicializar com README, .gitignore, etc.).
2.  **Adicione o repositório remoto como `origin` no seu repositório local:**
    ```bash
    git remote add origin <URL_do_repositorio_GitHub_criado>
    ```
3.  **Envie a branch local para o remoto:**
    ```bash
    git push -u origin main
    ```

### Receber Alterações do GitHub

Use `git pull` para sincronizar o seu repositório local com as alterações no repositório remoto do GitHub, como já foi explicado.

## Colaborar no GitHub

### Forking (Bifurcação) de um Repositório

Forking é criar uma cópia pessoal de um repositório de outro utilizador no seu próprio perfil do GitHub. É comum usar fork para:

  * **Contribuir para projetos open source:** Fazer um fork do repositório, fazer as suas alterações na sua cópia, e depois criar um Pull Request para propor as suas alterações ao repositório original.
  * **Experimentar e aprender:** Usar o fork como um espaço seguro para experimentar código sem afetar o repositório original.

Para fazer fork de um repositório no GitHub, vá para a página do repositório e clique no botão "Fork" no canto superior direito.

### Pull Requests (Pedidos de Pull)

Pull Requests (PRs) são uma forma de propor as suas alterações (numa branch) para serem merged numa outra branch (geralmente a branch principal) num repositório do GitHub. São a base da colaboração no GitHub.

1.  **Faça as suas alterações numa branch** (no seu fork ou numa branch do repositório original se tiver permissões).
2.  **Envie a sua branch para o repositório remoto** (`git push`).
3.  **No GitHub, vá para o seu repositório** e deverá ver um botão para "Compare & pull request" ou "Contribute". Clique nele.
4.  **Revise as alterações e crie o Pull Request:**
      * Escolha a branch base (onde quer juntar as suas alterações) e a branch compare (a sua branch com as alterações).
      * Adicione um título e descrição para o Pull Request, explicando as alterações propostas.
      * Clique em "Create pull request" ("Criar pull request").

### Issues (Problemas/Incidências)

Issues são usados para rastrear bugs, funcionalidades, tarefas e discussões num projeto do GitHub. São uma ferramenta de gestão de projetos integrada no GitHub.

  * **Criar uma Issue:** Na página do repositório, vá para a aba "Issues" e clique em "New issue" ("Nova issue").
  * **Discutir e resolver Issues:** As Issues podem ser comentadas, atribuídas a utilizadores, etiquetadas com labels (ex: "bug", "feature", "question") e fechadas quando resolvidas.

### Colaboradores e Permissões

Para projetos privados ou para dar permissões de escrita a outros utilizadores num repositório, pode adicionar colaboradores.

  * **Adicionar Colaboradores:** Na página do repositório, vá para "Settings" ("Definições") -\> "Collaborators" ("Colaboradores") -\> "Add people" ("Adicionar pessoas").
  * **Permissões:** Pode definir diferentes níveis de permissão para colaboradores (ex: read, write, admin).

## Funcionalidades do GitHub

### GitHub Pages

GitHub Pages permite hospedar websites estáticos diretamente do seu repositório GitHub. É ideal para websites pessoais, documentação de projetos ou portfólios.

1.  **Crie um repositório com o nome `<nome_utilizador>.github.io`** (para websites de utilizador) ou `<nome_repositorio>` (para websites de projeto).
2.  **Adicione ficheiros HTML, CSS, JavaScript** e outros ficheiros do website ao repositório.
3.  **Vá para "Settings" -\> "Pages"** do seu repositório no GitHub.
4.  **Escolha a branch e pasta de origem** (geralmente branch `main` e pasta raiz `/`).
5.  **O GitHub Pages irá publicar o seu website** em `https://<nome_utilizador>.github.io` ou `https://<nome_utilizador>.github.io/<nome_repositorio>`.

### GitHub Actions

GitHub Actions é uma plataforma de automação e CI/CD (Continuous Integration/Continuous Delivery) integrada no GitHub. Permite automatizar tarefas no seu workflow de desenvolvimento, como testes, builds, deploy, etc., diretamente nos seus repositórios GitHub.

  * **Workflows:** GitHub Actions são definidos em ficheiros YAML (`.github/workflows/`) no seu repositório.
  * **Ações:** Pode usar ações pré-definidas ou criar as suas próprias ações para automatizar tarefas.
  * **Triggers:** Workflows podem ser acionados por eventos do GitHub (ex: push, pull request, issues) ou agendados.

### GitHub Projects

GitHub Projects (antigamente Project Boards) são ferramentas de gestão de projetos integradas no GitHub. Permitem organizar e rastrear tarefas, issues e pull requests num projeto.

  * **Boards:** Crie boards (quadros) com colunas personalizadas (ex: "To do", "In progress", "Done").
  * **Cards:** Adicione issues, pull requests ou notas como cards aos boards.
  * **Automação:** Pode automatizar a movimentação de cards entre colunas com base em eventos do GitHub.

### GitHub Issues e Projects para Gestão de Projetos

Como mencionado, Issues e Projects são ferramentas poderosas para gestão de projetos no GitHub. Pode usar Issues para rastrear tarefas, bugs e funcionalidades, e Projects para organizar e planear o trabalho usando boards e cards. Combinando estas ferramentas, o GitHub torna-se uma plataforma completa para desenvolvimento colaborativo e gestão de projetos de software.

Este manual oferece uma visão geral completa do Git e GitHub, desde os comandos básicos do Git até às funcionalidades de colaboração e gestão de projetos do GitHub. Com este guia, deverá ser capaz de começar a usar o Git e GitHub nos seus projetos de desenvolvimento de software.
