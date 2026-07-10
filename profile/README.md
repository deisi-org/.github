<div align="center">

# DEISI — Plataforma de Deploy

### Aplicações académicas online no domínio institucional da Universidade Lusófona

**Docker · GitHub Actions · Kubernetes · PostgreSQL · HTTPS**

```text
https://nome-da-app.apps.deisi.ulusofona.pt
```

</div>

---

## Sobre a plataforma

A **Plataforma de Deploy DEISI** permite colocar online aplicações desenvolvidas por alunos, docentes e equipas académicas através de um processo centralizado e automatizado.

Cada aplicação é mantida num repositório próprio da organização e pode ser disponibilizada num endereço institucional, sem que a respetiva equipa necessite de acesso direto à máquina virtual, ao cluster Kubernetes, às bases de dados centrais ou aos componentes internos da infraestrutura.

A plataforma foi criada para substituir processos manuais e configurações isoladas por um modelo comum, reutilizável e alinhado com práticas modernas de DevOps.

---

## A quem se destina

Esta plataforma destina-se a:

- alunos que pretendam colocar projetos académicos online;
- equipas de Trabalhos Finais de Curso;
- docentes responsáveis por aplicações ou demonstradores;
- projetos desenvolvidos no contexto do DEISI;
- aplicações institucionais que necessitem de um ambiente de execução comum.

> [!IMPORTANT]
> Cada utilizador trabalha apenas no repositório da sua aplicação.  
> Não é necessário conhecer ou administrar a infraestrutura interna da plataforma.

---

## O que a plataforma oferece

| Funcionalidade | Descrição |
|---|---|
| **Deploy automatizado** | A aplicação é construída e atualizada através do GitHub Actions. |
| **Domínio institucional** | Cada aplicação pode ser disponibilizada em `nome-da-app.apps.deisi.ulusofona.pt`. |
| **HTTPS** | O acesso público é disponibilizado através de ligação segura. |
| **Suporte a várias tecnologias** | Podem ser utilizadas diferentes linguagens e frameworks, desde que a aplicação execute em Docker. |
| **Variáveis de ambiente seguras** | Chaves, tokens e configurações privadas são tratados através de secrets. |
| **PostgreSQL opcional** | Cada aplicação pode receber uma base de dados, utilizador e credenciais próprias. |
| **Migrations automáticas** | A atualização da estrutura da base de dados pode fazer parte do processo de deploy. |
| **Persistência de ficheiros** | Pode ser associado armazenamento persistente para uploads, imagens ou documentos. |
| **Rolling updates** | As novas versões são aplicadas de forma controlada. |
| **Recuperação automática** | A infraestrutura tenta repor aplicações quando ocorre uma falha no respetivo processo de execução. |
| **Backups da base de dados** | O PostgreSQL central dispõe de backups automáticos guardados fora do cluster. |

---

## Tecnologias suportadas

A plataforma é independente da linguagem ou framework utilizada.

Pode suportar, entre outros:

- Django, Flask e FastAPI;
- Node.js, Express e NestJS;
- React, Vite e aplicações frontend;
- Java e Spring Boot;
- PHP e Laravel;
- APIs, backends e sites estáticos.

O requisito principal é que a aplicação possa ser executada num container Docker.

---

## Experiência do utilizador

Do ponto de vista de um aluno ou docente, a utilização da plataforma está limitada ao repositório da aplicação.

A infraestrutura central trata das operações comuns necessárias para colocar a aplicação online, incluindo:

```text
Código da aplicação
        ↓
Construção da imagem
        ↓
Deploy no cluster
        ↓
Configuração do acesso HTTPS
        ↓
Aplicação disponível no domínio institucional
```

Quando solicitado pela aplicação, a plataforma pode também preparar:

- variáveis de ambiente;
- base de dados PostgreSQL;
- migrations;
- armazenamento persistente;
- credenciais próprias para ligação à base de dados.

Toda a complexidade associada ao cluster, à rede interna e aos componentes administrativos permanece separada da utilização normal da plataforma.

---

## Documentação de deploy

As instruções completas para preparar e colocar uma aplicação online encontram-se no guia seguinte:

<div align="center">

### [Abrir o Guia Genérico de Deploy](./docs/guia-deploy-aplicacoes.pdf)

</div>

O guia inclui informação sobre:

- requisitos da aplicação;
- preparação do repositório;
- criação do Dockerfile;
- configuração do workflow;
- escolha da porta interna;
- variáveis de ambiente e secrets;
- base de dados PostgreSQL;
- migrations;
- persistência de ficheiros;
- acompanhamento do deploy;
- resolução de problemas comuns.

---

## Acesso e organização dos repositórios

Cada aplicação possui o seu próprio repositório e o acesso é atribuído apenas aos membros autorizados.

Os utilizadores da plataforma:

- têm acesso ao repositório da respetiva aplicação;
- podem acompanhar o deploy através do GitHub Actions;
- não necessitam de acesso à VM;
- não necessitam de acesso ao Kubernetes;
- não necessitam de acesso direto ao PostgreSQL;
- não necessitam de acesso aos repositórios internos da infraestrutura.

Esta separação reduz a exposição de componentes técnicos e permite que cada equipa se concentre no desenvolvimento da sua aplicação.

---

## Responsabilidades

### Equipa da aplicação

A equipa responsável por cada projeto deve:

- manter o código da aplicação funcional;
- garantir que a aplicação pode ser executada através de Docker;
- proteger passwords, tokens e chaves privadas;
- configurar corretamente as variáveis necessárias;
- manter a documentação específica do projeto;
- acompanhar o resultado do deploy no GitHub Actions.

### Plataforma DEISI

A plataforma disponibiliza:

- construção e disponibilização da aplicação;
- integração com o domínio institucional;
- gestão dos recursos necessários no ambiente de execução;
- suporte opcional a PostgreSQL, migrations e persistência;
- isolamento lógico entre aplicações;
- backups automáticos da base de dados central.

A plataforma não corrige automaticamente erros existentes no código, no Dockerfile, nas dependências ou nas migrations de uma aplicação.

---

## Segurança

Para garantir uma utilização segura:

- passwords, tokens e chaves privadas não devem ser guardados no código;
- ficheiros `.env` não devem ser enviados para o repositório;
- devem ser utilizados GitHub Secrets para valores sensíveis;
- credenciais de base de dados não devem ser partilhadas;
- informação sensível não deve ser incluída em commits, issues ou pedidos de suporte;
- o acesso aos repositórios deve ser limitado aos membros necessários.

A infraestrutura administrativa, os recursos internos do cluster e a base de dados central não são expostos aos utilizadores comuns da plataforma.

---

## Suporte

Em caso de problema, deve ser consultado primeiro:

1. o guia de deploy;
2. a execução mais recente em **GitHub Actions**;
3. o primeiro passo da pipeline que tenha apresentado erro.

Ao solicitar apoio, deve ser indicada informação suficiente para diagnóstico:

- nome do repositório;
- tecnologia utilizada;
- descrição do problema;
- passo da pipeline que falhou;
- mensagem de erro relevante;
- indicação sobre utilização de base de dados, migrations ou persistência.

Nunca devem ser enviados passwords, tokens, chaves privadas ou o conteúdo de secrets.

---

## Origem do projeto

A plataforma foi desenvolvida no âmbito do Trabalho Final de Curso:

**Integração de Aplicações DEISI numa Plataforma Unificada**

Desenvolvido por **Afonso Sá** e **Lucas Martins**, com orientação do **Professor Lúcio Studer Ferreira** e coorientação do **Professor Martim Mourão**.

O projeto teve como objetivo modernizar e normalizar o deploy das aplicações do DEISI através de uma infraestrutura comum, automatizada e documentada.

---

<div align="center">

**DEISI — Universidade Lusófona**

Plataforma unificada para deploy de aplicações académicas

</div>