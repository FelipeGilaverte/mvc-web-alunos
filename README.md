# MVC Web - Cadastro de Alunos

Projeto simples de cadastro de alunos usando Java, Spring Boot, Maven e Thymeleaf.

A aplicacao mostra, de forma pratica, a divisao da arquitetura MVC:

- Model: representa os dados e as regras principais.
- Controller: recebe as requisicoes do navegador e escolhe qual tela sera exibida.
- View: exibe o formulario e a lista de alunos.

## Tecnologias

- Java 21
- Spring Boot
- Spring Web MVC
- Thymeleaf
- Maven

## Estrutura do projeto

```text
mvc-web-alunos/
|-- src/main/java/com/exemplo/mvc/
|   |-- MvcWebAlunosApplication.java
|   |-- model/
|   |   `-- Aluno.java
|   `-- controller/
|       `-- AlunoController.java
|-- src/main/resources/
|   |-- templates/
|   |   |-- alunos-form.html
|   |   `-- alunos-lista.html
|   |-- static/css/
|   |   `-- styles.css
|   `-- application.properties
|-- pom.xml
|-- mvnw
`-- mvnw.cmd
```

## Explicacao dos arquivos

### `Aluno.java`

Fica na camada Model. Essa classe representa um aluno com dois dados:

- `nome`
- `matricula`

Ela tambem possui uma validacao simples para nao permitir nome vazio.

### `AlunoController.java`

Fica na camada Controller. Essa classe controla o fluxo da aplicacao:

- `GET /alunos`: abre o formulario de cadastro.
- `POST /alunos`: recebe os dados do formulario, cria um aluno e envia a lista para a tela.

Os alunos ficam guardados em uma lista em memoria, ou seja, os dados existem enquanto a aplicacao estiver rodando.

### `alunos-form.html`

Fica na camada View. Essa tela mostra o formulario com os campos:

- Nome
- Matricula

Quando o usuario clica em `Cadastrar`, os dados sao enviados para o controller.

### `alunos-lista.html`

Tambem fica na camada View. Essa tela mostra uma tabela com os alunos cadastrados.

### `styles.css`

Define apenas a aparencia das paginas, como cores, espacamento, formulario, botao e tabela. A logica da aplicacao continua no controller e no model.

## Como executar

No terminal, dentro da pasta do projeto, execute:

```powershell
.\mvnw.cmd spring-boot:run
```

Depois acesse no navegador:

```text
http://localhost:8080/alunos
```

## Como testar o funcionamento

1. Abra `http://localhost:8080/alunos`.
2. Digite o nome do aluno.
3. Digite a matricula.
4. Clique em `Cadastrar`.
5. Confira se o aluno aparece na tabela.

## Fluxo MVC

```text
Navegador -> Controller -> Model -> Controller -> View -> Navegador
```

No projeto, esse fluxo acontece assim:

1. O navegador acessa `/alunos`.
2. O `AlunoController` retorna a tela `alunos-form.html`.
3. O usuario envia nome e matricula pelo formulario.
4. O `AlunoController` cria um objeto `Aluno`.
5. A lista de alunos e enviada para `alunos-lista.html`.
6. O navegador mostra a tabela com os dados cadastrados.

## Comandos Git

O repositorio local ja pode ser publicado no GitHub. Depois de criar o repositorio remoto, use:

```bash
git remote add origin https://github.com/SEU_USUARIO/mvc-web-alunos.git
git branch -M main
git push -u origin main
```
