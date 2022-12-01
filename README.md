# Redmine Dockerized

Redmine é uma aplicação web, de código-aberto, desenvolvido com a linguagem de programação Ruby e o framework Rails, com a finalidade de auxiliar no gerenciamento de projetos. Ele permite que usuários gerenciem múltiplos projetos e subprojetos associados. Como é uma aplicação web, é possível configurar o Redmine para ser executado tanto localmente, quanto em rede, auxiliando assim no desenvolvimento colaborativo, onde vários desenvolvidores e stakeholders podem colaborar e acompanhar/supervionar os projetos.

Ele possui recursos para auxiliar no gerenciamento e monitoramento de tarefas, como gráficos de Grantt, calendários e também páginas wikis e fórums (por projeto) que auxiliar na criação de bases de conhecimento. Ele também se integra com vários sistemas de controle de versões, incluindo repository browser e diff viewrs.

## Configurações

### Clonando o repositório.

| **Observação:** Você precisa ter o git instalados em sua máquina.

Execute:

```
git clone git@github.com:JoshuaWebDev/redmine-dockerized.git
```
### Variáveis de Ambiente

Dentro do arquivo ```docker-compose``` é possível definir algumas variáveis de ambiente, como senhas de usuários, banco de dados, etc. Exemplo:

```
...
REDMINE_DB_MYSQL: db
REDMINE_DB_PASSWORD: ${DB_PASSWORD}
REDMINE_SECRET_KEY_BASE: ${DB_PASSWORD}
...
```

No exemplo acima é usada uma base de dados MySQL, se quiser usar outro, como Postgres ou SQL Server, por exemplo, use as respectivas variáveis a seguir, conforme o tipo de SGBD desejado.

```
REDMINE_DB_POSTGRES: db
```

ou

```
REDMINE_DB_SQLSERVER: db
```

É possível definir o usuário que acessa a base de dados por meio da variável de ambiente a seguir:

```
REDMINE_DB_USERNAME: ${DB_USERNAME}
```

| Se esta variável não estiver definida, serão usados os usários padrão: ```root``` no MySQL, ```postgres``` no PostgreSQL ou ```redmine``` no SQLite.

Para evitar que dados sensíveis sejam visualizados por outras pessoas é recomendado usar um arquivo ```.env``` para armazenar os valores das variáveis de ambiente. Neste repositório há um arquivo ```.env.example``` que pode ser usado como template. Copie este arquivo, renomeando-o para ```.env``` e altere os valores das variáveis conforme queira.

### Montando as Imagens e Containers no Docker

Acesse a pasta do projeto e execute

| **Observação:** Você precisa ter o git, o docker e o docker-compose instalados em sua máquina.

```
docker-compose up -d
```

Acesse o endereço http://localhost:8030/ em seu navegador web.

O Redmine possui um usuário e senha padrão ```admin```. Ao acessar o Redmine a primeira vez e entrar com o usuário e senha ```admin``` o sistema pedirá para alterar a senha.

## Migração de Dados

[Em construção]

## Links Úteis

- [Gerenciando Projetos](https://www.redmine.org/projects/redmine/wiki/PtBRRedmineProjects)
- [Gerenciando Usuário](https://www.redmine.org/projects/redmine/wiki/PtBRRedmineUsers)
- [Gerenciando Grupos](https://www.redmine.org/projects/redmine/wiki/PtBRRedmineGroups)
- [Papés e Permissões](https://www.redmine.org/projects/redmine/wiki/PtBRRedmineRoles)
- [Tarefas](https://www.redmine.org/projects/redmine/wiki/PtBRRedmineIssueTrackingSetup)
- [Formatação de Textos](https://www.redmine.org/projects/redmine/wiki/RedmineTextFormattingTextile)
- [Documentação Oficial](https://www.redmine.org/projects/redmine/wiki/Guide)