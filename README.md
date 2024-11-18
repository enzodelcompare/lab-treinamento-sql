<a href="https://www.linkedin.com/in/enzodelcompare">
  <img src="https://img.shields.io/badge/linkedin-enzo_delcompare-blue">
</a>

<a href="https://www.linkedin.com/in/enzodelcompare">
  <img src="https://img.shields.io/badge/contatos-enzo_delcompare-green">
</a>

<img src="https://github.com/enzodelcompare/treinamento-sql-olist/blob/main/imagens/olist.png">

# Treinamento SQL - Data Voyagers

## Descrição do Projeto

O treinamento tem como objetivo ensinar desde os conceitos básicos até os mais avançados de **SQL**, com ênfase no **MySQL**. Durante o treinamento, os participantes aprenderão a modelar e manipular dados a partir de um banco de dados real, proveniente do conjunto de dados da **OLIST** (_disponível no **Kaggle**_), aplicando técnicas de **DDL** (_Data Definition Language_), **DML** (_Data Manipulation Language_) e **DQL** (_Data Query Language_).

O projeto inclui:

- **Modelagem de Dados:** Utilizando o **SQL Power Architect** para criar o modelo de dados **DER** (_Diagrama de Entidade e Relacionamento_).
- **Criação de Banco de Dados e Tabelas:** Usando os comandos **DDL** para a definição de estruturas de banco de dados.
- **Manipulação de Dados:** Realizando inserções, atualizações e exclusões usando comandos **DML**.
- **Consultas e Análises:** Consultando e analisando os dados com comandos **DQL** para extrair informações úteis.

<br>

## Fonte de Dados

A fonte de dados utilizada no treinamento é proveniente do conjunto de dados da **OLIST** disponível no **Kaggle**: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

<br>

## Estrutura do Projeto

Este repositório contém as seguintes estruturas de pastas:

### Estrutura de Diretórios

`arquivos/`: Contém os arquivos de dados comprimidos da fonte **Olist**.

`der/`: Contém o modelo de dados no formato `ER` (**Entidade-Relacionamento*) para o banco `olist_db`, criado usando **SQL Power Architect**.

`imagens/`: Imagens utilizadas no prodjeto.

`scripts/`: Contém os scripts **SQL** para criação do banco de dados, inserção de dados e consultas.

<br>

## Comandos SQL Abordados no Treinamento

**1. Comandos DDL (Data Definition Language)**

`scripts/create_alter_drop.sql`: Esses scripts são responsáveis pela criação, alteração e exclusão das tabelas no banco de dados. Os alunos aprenderão como criar um banco de dados e tabelas, além de adicionar restrições e chaves estrangeiras para garantir a integridade referencial.

**2. Comandos DML (Data Manipulation Language)**

`scripts/exemplos-insert_update_delete.sql`: Esses scripts são responsáveis pela inserção, atualização e exclusão de dados nas tabelas. Os alunos aprenderão como popular as tabelas com dados reais extraídos do conjunto de dados da **Olist**, além de atualizar e excluir informações.

**3. Comandos DQL (Data Query Language)**

`scripts/select.sql`: Esses scripts são usados para consultar os dados no banco de dados, utilizando os comandos `SELECT` para realizar pesquisas complexas com filtros, joins, agregações e ordenações.

<br>

## Diagrama Entidade-Relacionamento (DER)

O modelo de dados foi criado utilizando o **SQL Power Architect** e está disponível na pasta `der/der_olist/`. O diagrama representa as tabelas, suas relações e chaves estrangeiras.

<br>

## Objetivos do Treinamento

- **Introdução ao SQL:** Explicar a sintaxe básica do **SQL**, tipos de dados e operações básicas.
- **Comandos DDL:** Como criar bancos de dados e tabelas, adicionar chaves primárias e estrangeiras.
- **Comandos DML:** Como inserir, atualizar e excluir dados no banco.
- **Consultas Avançadas (DQL):** Como usar joins, subconsultas, agregações e funções para obter insights a partir dos dados.
- **Modelagem de Dados:** Como usar o **SQL Power Architect** para criar e entender o modelo de dados de um banco de dados relacional.

<br>

## Como Rodar o Projeto?

### Requisitos

Para rodar este projeto, você precisará de:

- **MySQL:** Para criar e gerenciar o banco de dados.
- **SQL Power Architect:** Para visualizar e criar o modelo de dados.
- **Kaggle API** ou **Download Manual:** Para obter os arquivos de dados da Olist.

<br>

## Exercícios Práticos

Durante o treinamento, você realizará os seguintes exercícios:

- **Criação de Tabelas:** Criar tabelas adicionais baseadas no modelo **Olist**.
- **Inserção de Dados:** Inserir novos dados de clientes, produtos e pedidos no banco.
- **Consultas Avançadas:** Escrever consultas complexas para analisar as vendas, os produtos mais vendidos, etc.
- **Modelagem de Dados:** Criar ou modificar o modelo **ER** utilizando o **SQL Power Architect**.

<br>

## Contribuições

Contribuições são bem-vindas! Se você quiser melhorar este repositório, abra um `pull request` com suas melhorias ou correções. Caso identifique algum erro ou problema, crie uma issue para que possamos discutir a solução.
