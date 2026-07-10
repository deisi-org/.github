<div align="center">

# DEISI — Aplicações Académicas Online

### Plataforma institucional para deploy de aplicações desenvolvidas no âmbito académico

**Universidade Lusófona · Departamento de Engenharia Informática e Sistemas de Informação**

</div>

---

## Sobre esta organização

A organização **deisi-org** reúne projetos académicos, aplicações e recursos associados ao Departamento de Engenharia Informática e Sistemas de Informação da Universidade Lusófona.

Esta organização suporta o deploy de aplicações desenvolvidas por alunos e equipas académicas, permitindo colocar os projetos online com um endereço institucional.

As aplicações disponibilizadas através desta plataforma podem ficar acessíveis em endereços do tipo:

```text
https://nome-da-app.apps.deisi.ulusofona.pt
```

---

## Objetivo da plataforma

A plataforma foi criada para simplificar o deploy de aplicações académicas, disponibilizando uma forma centralizada, consistente e segura de colocar projetos online.

Entre os principais objetivos encontram-se:

- facilitar o deploy de aplicações desenvolvidas no DEISI;
- permitir a utilização de um domínio institucional;
- uniformizar o processo de deploy dos diferentes projetos;
- reduzir a necessidade de acesso direto à infraestrutura;
- disponibilizar suporte para aplicações com diferentes tecnologias;
- garantir uma separação clara entre o código das aplicações e a infraestrutura central.

---

## A quem se destina

Esta plataforma destina-se principalmente a:

- alunos com projetos académicos que necessitem de ficar disponíveis online;
- equipas de Trabalhos Finais de Curso;
- docentes responsáveis pelo acompanhamento de projetos;
- aplicações institucionais ou demonstradores desenvolvidos no contexto do DEISI.

Cada equipa trabalha apenas no repositório da respetiva aplicação.

O acesso direto ao cluster, aos servidores, às bases de dados centrais e aos componentes internos da plataforma não é necessário para a utilização normal do serviço.

---

## Tecnologias suportadas

A plataforma foi concebida para ser genérica e pode suportar diferentes tipos de aplicações, incluindo:

- aplicações web;
- APIs;
- backends;
- frontends;
- sites estáticos;
- aplicações com base de dados;
- aplicações com armazenamento persistente.

Podem ser utilizadas tecnologias como Python, Django, Flask, FastAPI, Node.js, React, Java, Spring Boot, PHP, Laravel, entre outras, desde que a aplicação possa ser executada num container Docker.

---

## Funcionalidades disponíveis

A plataforma disponibiliza, consoante as necessidades de cada aplicação:

| Funcionalidade | Descrição |
|---|---|
| **Deploy automático** | Atualização da aplicação a partir do repositório GitHub. |
| **Domínio institucional** | Endereço público no domínio `apps.deisi.ulusofona.pt`. |
| **HTTPS** | Acesso seguro através de certificado válido. |
| **Variáveis de ambiente** | Configuração de chaves, tokens e outros valores sensíveis. |
| **PostgreSQL** | Base de dados dedicada a cada aplicação, quando necessária. |
| **Migrations** | Execução de comandos de atualização da estrutura da base de dados. |
| **Persistência de ficheiros** | Armazenamento persistente para uploads, imagens e documentos. |
| **Isolamento entre aplicações** | Cada aplicação possui configuração e credenciais próprias. |

---

## Documentação

A documentação de utilização da plataforma encontra-se disponível no guia seguinte:

### [Guia genérico para colocar uma aplicação online](./docs/guia-deploy-aplicacoes.pdf)

O guia contém as instruções necessárias para preparar e publicar uma aplicação, incluindo:

- organização do repositório;
- criação do Dockerfile;
- configuração do workflow;
- variáveis de ambiente e secrets;
- bases de dados PostgreSQL;
- migrations;
- persistência de ficheiros;
- acompanhamento do processo de publicação;
- resolução de problemas comuns.

---

## Organização e acesso

Os repositórios das aplicações podem ser públicos ou privados, de acordo com as regras definidas para cada projeto.

O acesso é atribuído apenas às pessoas ou equipas que necessitam de trabalhar em cada repositório.

Os componentes centrais da infraestrutura são geridos separadamente e não fazem parte do acesso normal dos utilizadores da plataforma.

---

## Segurança

A utilização da plataforma deve respeitar as seguintes regras:

- não guardar passwords, tokens ou chaves privadas no código;
- não publicar ficheiros `.env`;
- utilizar os mecanismos de secrets disponibilizados pelo GitHub;
- não partilhar credenciais de base de dados;
- não incluir informação sensível em issues, commits ou pedidos de suporte;
- limitar o acesso aos repositórios apenas aos membros necessários.

---

## Responsabilidade das equipas

Cada equipa é responsável por:

- manter o código da aplicação funcional;
- garantir que a aplicação pode ser executada em Docker;
- manter a documentação do próprio projeto;
- proteger credenciais e dados sensíveis;
- acompanhar o estado do deploy da sua aplicação;
- comunicar erros com informação suficiente para diagnóstico.

A plataforma central disponibiliza o mecanismo de deploy, mas não substitui a validação técnica da aplicação.

---

## Suporte

Em caso de problema, deve ser consultada primeiro a documentação e o histórico da execução no GitHub Actions.

Ao solicitar apoio, indicar:

- nome do repositório;
- tecnologia utilizada;
- descrição do problema;
- passo em que ocorreu a falha;
- mensagem de erro relevante.

Não devem ser enviados passwords, tokens, chaves privadas ou outros valores sensíveis.

---

<div align="center">

**DEISI — Universidade Lusófona**

Plataforma de deploy de aplicações académicas

</div>
