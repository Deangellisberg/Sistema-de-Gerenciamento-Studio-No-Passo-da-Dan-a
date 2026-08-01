# Sistema de Gerenciamento – Studio No Passo da Dança

## 📚 Descrição do Mini-Mundo

Este projeto foi desenvolvido para a disciplina de Banco de Dados e tem como objetivo modelar e implementar um sistema de gerenciamento para uma escola de ballet.

O sistema permite controlar informações sobre alunos, professores, modalidades, turmas e matrículas, facilitando a organização das atividades da escola.

## 🎯 Objetivo

O banco de dados foi criado para armazenar e gerenciar:

- Cadastro de alunos;
- Cadastro de professores;
- Cadastro de modalidades de dança;
- Cadastro de turmas;
- Controle das matrículas dos alunos nas turmas.

## 📋 Regras de Negócio

- Um professor pode ministrar várias turmas.
- Cada turma possui apenas um professor.
- Cada turma pertence a uma modalidade.
- Uma modalidade pode possuir várias turmas.
- Um aluno pode estar matriculado em várias turmas.
- Uma turma pode possuir vários alunos.
- A relação entre alunos e turmas é realizada por meio da tabela **matricula**.

## 🗄️ Estrutura do Banco

O banco de dados é composto pelas seguintes tabelas:

- **aluno**
- **professor**
- **modalidade**
- **turma**
- **matricula**

## 🔗 Relacionamentos

- Professor (1:N) Turma
- Modalidade (1:N) Turma
- Aluno (N:N) Turma, através da tabela **matricula**

## 📂 Estrutura do Projeto

```
desafio-bd-Deangellisberg/
├── README.md
├── modelo_er.png
├── 01_cria.sql
├── 02_insere.sql
├── 03_consultas.sql
└── 04_atualiza_remove.sql
```

## 🛠️ Tecnologias Utilizadas

- PostgreSQL
- DBeaver
- brModelo Web
- Git
- GitHub

## 👨‍💻 Autor

**Nome:** Deangellis Berg

**Disciplina:** Banco de Dados

**Professor:** Ricardo

**Instituição:** Cesar School

**Ano:** 2026