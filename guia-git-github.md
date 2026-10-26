# Guia Prático de Git e GitHub

Este documento apresenta o ciclo de vida de um projeto
no GitHub, desde sua criação até suas atualizações.

# Guia Prático de Git e GitHub

## Introdução

O Git e o GitHub são ferramentas importantes no desenvolvimento de software, pois permitem organizar projetos, controlar as alterações realizadas no código e armazenar os arquivos de forma segura.

O Git é responsável pelo controle de versões, registrando as mudanças feitas durante o desenvolvimento. Já o GitHub é uma plataforma online que permite armazenar repositórios e compartilhar projetos com outras pessoas.

Neste documento, vou explicar como criar um repositório, enviar arquivos, utilizar o README.md e realizar atualizações utilizando diferentes ferramentas.

---

## 1. O Passo a Passo da Criação e Envio

### 1.1 Criando um repositório no GitHub

O primeiro passo para disponibilizar um projeto no GitHub é criar um repositório, que será o local onde os arquivos e o histórico de alterações ficarão armazenados.

Para criar um repositório, sigo os seguintes passos:

1. Acesso o site [GitHub](https://github.com) e faço login na minha conta.
2. Clico na opção **New repository** para criar um novo repositório.
3. Defino um nome para o projeto, por exemplo, `atividade-git-github`.
4. Adiciono uma descrição para explicar brevemente o objetivo do repositório.
5. Escolho se o repositório será **Public**, permitindo que outras pessoas visualizem o projeto, ou **Private**, restringindo o acesso.
6. Para começar com um repositório vazio, deixo desmarcadas as opções de adicionar README, `.gitignore` e licença.
7. Finalizo clicando em **Create repository**.

Depois desses passos, o GitHub cria um repositório remoto que poderá receber os arquivos do meu computador.

### 1.2 Conectando o projeto local ao GitHub

Após criar o repositório, preciso conectar a pasta do meu computador ao repositório remoto.

Para isso, abro a pasta do projeto no VS Code e utilizo o terminal integrado.

Primeiro, inicializo o Git:

```bash
git init
```

Esse comando transforma a pasta do projeto em um repositório Git local, permitindo que as alterações nos arquivos sejam acompanhadas.

Em seguida, defino o nome da branch principal:

```bash
git branch -M main
```

A branch `main` será utilizada como a principal linha de desenvolvimento do projeto.

Depois, conecto o repositório local ao GitHub:

```bash
git remote add origin https://github.com/SEU-USUARIO/atividade-git-github.git
```

O comando `git remote add origin` cadastra o endereço do repositório remoto. Dessa maneira, o Git sabe para onde deverá enviar as atualizações.

É necessário substituir `SEU-USUARIO` pelo nome de usuário da conta do GitHub.

### 1.3 Realizando o primeiro envio

Com a conexão configurada, posso enviar os arquivos do meu computador para o GitHub.

Primeiro, adiciono os arquivos à área de preparação:

```bash
git add .
```

Esse comando prepara todos os arquivos novos e modificados da pasta, respeitando as regras do `.gitignore`, para serem incluídos no próximo commit.

Depois, crio um commit:

```bash
git commit -m "Primeiro commit do projeto"
```

O commit registra uma versão do projeto no histórico local. A mensagem permite identificar o que foi realizado naquela atualização.

Por último, envio os commits para o GitHub:

```bash
git push -u origin main
```

O comando `git push` envia os commits locais para o repositório remoto. A opção `-u` estabelece a associação entre a branch local e a branch remota, facilitando os próximos envios.

Após executar os comandos e realizar a autenticação, caso seja solicitada, posso acessar a página do repositório no GitHub e visualizar os arquivos enviados.

**Resumo dos comandos utilizados:**

| Comando                     | Função                                                         |
| --------------------------- | -------------------------------------------------------------- |
| `git init`                  | Inicializa um repositório Git local.                           |
| `git branch -M main`        | Define ou renomeia a branch atual para main.                   |
| `git remote add origin URL` | Conecta o repositório local ao remoto.                         |
| `git add .`                 | Prepara os arquivos para o commit.                             |
| `git commit -m "mensagem"`  | Registra uma alteração no histórico local.                     |
| `git push -u origin main`   | Envia os commits ao GitHub e configura a associação da branch. |

Também é importante utilizar o `.gitignore` para evitar o envio de arquivos desnecessários e verificar se não existem informações sensíveis, como senhas e chaves de acesso, dentro do projeto.

---

## 2. A Anatomia do README Perfeito

### 2.1 O que é o README.md?

O `README.md` é um arquivo de documentação que normalmente fica na pasta principal de um projeto.

Ele funciona como uma apresentação do repositório, ajudando outras pessoas a entenderem o objetivo da aplicação, quais tecnologias foram utilizadas e como executar o projeto.

O público-alvo do README pode incluir desenvolvedores, recrutadores, professores e qualquer pessoa interessada em conhecer o código.

Considero esse arquivo importante porque um projeto pode possuir um código bem desenvolvido, mas, sem documentação, outras pessoas podem encontrar dificuldades para entender como ele funciona.

Além disso, o GitHub apresenta automaticamente o conteúdo do README na página principal do repositório, facilitando o acesso às informações.

### 2.2 Informações essenciais de um README profissional

Um README bem organizado deve apresentar informações que ajudem o leitor a compreender e utilizar o projeto.

**1. Título do projeto**

É o nome da aplicação ou do repositório. Deve aparecer de forma destacada para que o visitante identifique rapidamente o projeto.

**2. Descrição do projeto**

Explica qual é o objetivo da aplicação, o problema que ela busca resolver e suas principais características.

**3. Tecnologias utilizadas**

Apresenta as linguagens, frameworks, bancos de dados e ferramentas utilizadas no desenvolvimento.

Por exemplo:

- Java
- Spring Boot
- PostgreSQL
- Git e GitHub

**4. Como instalar e executar**

Contém orientações para que outra pessoa consiga configurar e executar o projeto no próprio computador.

Pode incluir os requisitos necessários, comandos de instalação, configurações e instruções de execução.

**5. Funcionalidades**

Apresenta as principais operações disponíveis na aplicação, como cadastro de usuários, autenticação, consultas e gerenciamento de informações.

**6. Status do desenvolvimento**

Informa se o projeto está em planejamento, desenvolvimento, manutenção ou concluído.

Essa informação ajuda o visitante a compreender o estado atual da aplicação.

**7. Licença**

Informa quais são as condições de uso, distribuição e modificação do projeto. Quando existe uma licença, é importante indicar seu nome e disponibilizar o arquivo correspondente.

Essas informações tornam a documentação mais completa e ajudam tanto os usuários quanto outros desenvolvedores.

### 2.3 Por que utilizamos Markdown?

O Markdown é uma linguagem de marcação simples, utilizada para formatar documentos de texto.

O arquivo `README.md` utiliza a extensão `.md`, que representa um documento Markdown.

Uma das principais vantagens é a facilidade de escrita. Não é necessário utilizar HTML para criar títulos, listas, links ou destacar palavras.

Por exemplo:

```markdown
# Meu Projeto

## Descrição

Aplicação desenvolvida para gerenciar tarefas.

## Tecnologias

- Java
- Spring Boot
- PostgreSQL

## Status

**Em desenvolvimento**

## Repositório

[GitHub](https://github.com)
```

Nesse exemplo:

- `#` cria um título principal.
- `##` cria subtítulos.
- `-` permite organizar informações em listas.
- `**texto**` destaca palavras em negrito.
- `[texto](URL)` cria links.

O GitHub interpreta esses elementos e apresenta o documento com uma formatação visual organizada.

Dessa maneira, o Markdown facilita a leitura, a manutenção e a organização da documentação.

---

## 3. O Mapa das Atualizações: Commits e Pushes

Durante o desenvolvimento de um projeto, é comum realizar alterações, corrigir erros e implementar novas funcionalidades.

Para manter o repositório atualizado, posso utilizar diferentes ferramentas, dependendo do tipo de alteração e da minha preferência.

### 3.1 Atualizando diretamente pelo GitHub

O próprio site do GitHub permite editar arquivos sem precisar utilizar ferramentas instaladas no computador.

Para realizar uma alteração, posso seguir estes passos:

1. Acesso o repositório pelo navegador.
2. Abro o arquivo que desejo modificar.
3. Clico no ícone de lápis, que permite editar o arquivo.
4. Realizo as alterações necessárias.
5. Seleciono a opção de registrar as mudanças.
6. Escrevo uma mensagem explicando o que foi modificado.
7. Confirmo o commit, diretamente na branch ou por meio de uma nova branch, conforme o caso.

Essa opção é interessante para alterações pequenas, como corrigir um erro de digitação ou atualizar informações no README.

Entretanto, possui limitações para modificações maiores, principalmente quando o projeto possui muitos arquivos ou precisa ser executado e testado localmente.

### 3.2 Atualizando pelo terminal

O terminal é uma das maneiras mais tradicionais de utilizar o Git, pois permite executar os comandos diretamente e controlar cada etapa do versionamento.

Para atualizar um projeto, começo verificando quais arquivos foram modificados:

```bash
git status
```

Depois, adiciono as alterações:

```bash
git add .
```

Crio um commit com uma mensagem que descreve o que foi realizado:

```bash
git commit -m "Adiciona nova funcionalidade"
```

E envio os commits para o repositório remoto:

```bash
git push
```

Quando outras pessoas também trabalham no repositório, posso utilizar:

```bash
git pull
```

Esse comando busca e integra as atualizações da branch remota acompanhada pela minha branch local. É importante verificar possíveis conflitos antes de continuar o desenvolvimento.

A principal vantagem do terminal é oferecer mais controle e permitir a utilização de diferentes comandos do Git.

Também é uma forma muito utilizada profissionalmente e pode ser integrada a processos de automação.

### 3.3 Atualizando pelo VS Code

O VS Code possui integração com o Git, permitindo acompanhar e enviar alterações sem precisar digitar todos os comandos manualmente.

Na aba **Source Control**, consigo visualizar os arquivos que foram modificados durante o desenvolvimento.

Para registrar uma atualização, posso:

1. Abrir a aba Source Control.
2. Verificar quais arquivos foram alterados.
3. Selecionar os arquivos que desejo incluir no commit.
4. Escrever uma mensagem descrevendo as alterações.
5. Clicar na opção **Commit**.
6. Utilizar **Push** ou **Sync Changes** para enviar os commits ao GitHub.

A principal vantagem é conseguir visualizar as diferenças entre versões diretamente no editor.

Essa integração facilita o desenvolvimento porque posso modificar o código e acompanhar o versionamento dentro da mesma ferramenta.

### 3.4 Atualizando pelo GitHub Desktop

O GitHub Desktop é uma aplicação com interface gráfica desenvolvida para facilitar o uso do Git e a integração com o GitHub.

Com ele, posso abrir um repositório local e visualizar os arquivos modificados, além das diferenças entre a versão anterior e a atual.

Para enviar alterações, o processo consiste em:

1. Abrir o repositório no GitHub Desktop.
2. Verificar a lista de arquivos modificados.
3. Selecionar as alterações que farão parte do commit.
4. Escrever uma mensagem explicando a atualização.
5. Clicar em **Commit to main**, caso esteja trabalhando na branch principal.
6. Clicar em **Push origin** para enviar os commits ao GitHub.

O GitHub Desktop também permite trabalhar com branches, consultar o histórico de commits e buscar atualizações remotas.

Sua principal vantagem é oferecer uma interface visual, facilitando a utilização para quem não está acostumado com comandos de terminal.

Por outro lado, o terminal continua oferecendo acesso mais direto e completo aos recursos avançados do Git.

### 3.5 Por que devemos atualizar o repositório frequentemente?

Durante o desenvolvimento, considero importante realizar commits pequenos e frequentes, em vez de deixar todas as alterações acumuladas para enviar somente no final do mês.

Quando registro as mudanças aos poucos, consigo organizar melhor o histórico e identificar qual funcionalidade foi implementada em cada etapa.

Por exemplo, durante o desenvolvimento de uma API Java, posso organizar os commits da seguinte maneira:

```text
Commit 1 - Cria estrutura inicial do projeto
Commit 2 - Implementa entidade User
Commit 3 - Adiciona repositório de usuários
Commit 4 - Implementa regras de negócio
Commit 5 - Cria endpoints da API
Commit 6 - Adiciona validações
```

Essa organização facilita a identificação de problemas, a revisão do código e a recuperação de versões anteriores.

Também é importante entender que **commit e push são operações diferentes**.

O commit registra uma versão no repositório local, enquanto o push envia os commits para o repositório remoto no GitHub.

Por esse motivo, não basta apenas criar commits no computador. É necessário realizar o push regularmente para manter a versão remota atualizada.

Além disso, atualizar o repositório frequentemente facilita o trabalho em equipe, reduz o acúmulo de alterações e ajuda a evitar conflitos difíceis de resolver.

---

## Conclusão

Com esta atividade, pude compreender melhor o ciclo de vida de um projeto utilizando Git e GitHub.

Desde a criação do repositório até o envio dos arquivos, cada comando possui uma função importante para organizar e controlar o desenvolvimento.

Também entendi que a documentação por meio do README.md é essencial para apresentar um projeto e facilitar sua utilização por outras pessoas.

Por fim, percebi que existem diferentes maneiras de atualizar um repositório, seja pelo navegador, terminal, VS Code ou GitHub Desktop.

O mais importante é manter um histórico de alterações organizado, utilizar mensagens claras nos commits e atualizar o repositório com frequência.

Dessa forma, o Git e o GitHub deixam de ser apenas ferramentas para armazenar código e passam a fazer parte da organização e do acompanhamento de todo o desenvolvimento de software.
