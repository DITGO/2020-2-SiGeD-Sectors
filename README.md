# API de Setores
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL3-blue.svg)](https://opensource.org/licenses/gpl-3.0.html)
[![codecov](https://codecov.io/gh/fga-eps-mds/2020-2-SiGeD-Sectors/branch/master/graph/badge.svg?token=KQw64ih7YW)](https://codecov.io/gh/fga-eps-mds/2020-2-SiGeD-Sectors)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=fga-eps-mds_2020-2-G4-Sectors&metric=alert_status)](https://sonarcloud.io/dashboard?id=fga-eps-mds_2020-2-G4-Sectors)
[![Maintainability](https://api.codeclimate.com/v1/badges/0e583ef4f237a7020f8b/maintainability)](https://codeclimate.com/github/fga-eps-mds/2020-2-SiGeD-Sectors/maintainability)

Essa API faz parte da arquitetura de microsserviços do projeto [`SiGeD`](https://github.com/fga-eps-mds/2020-2-SiGeD), sua funcionalidade é possibilitar o controle dos dados dos setores. 

## Como contribuir?

Gostaria de contribuir com nosso projeto? Acesse o nosso [guia de contribuição](https://fga-eps-mds.github.io/2020-2-SiGeD/CONTRIBUTING/) onde são explicados todos os passos.
Caso reste duvidas você também pode entrar em contato conosco criando uma issue.

## Documentação

A documentação do projeto pode ser acessada pelo nosso site em https://fga-eps-mds.github.io/2020-2-SiGeD/ ou você pode acessar pela [SiGeD Documentação](https://fga-eps-mds.github.io/2020-2-SiGeD/home/)

## Testes

Todas as funções adicionadas nessa API devem ser testadas, o repositŕorio aceita até 10% do total de lihas não testadas. Para rodar os testes nesse repositŕio deve ser executado o comando:

```bash
docker-compose run backend_sector bash -c  "yarn && yarn jest --coverage --forceExit"
```

## Como rodar?

Para rodar a API é preciso usar os seguintes comandos usando o docker:

Crie uma network para os containers da API, caso não exista:

```bash
docker network create siged_backend
```

Suba o container com o comando:

```bash
docker-compose up
```
A API estará rodando na [porta 3004](http://localhost:3004).

## Rotas

**GET: `/sector/`**

Para receber os dados dos setores.

**GET: `/sector/:id`**

Para receber os dados de um setor específico utilizando o `id`.

**GET: `/sector/newest-four`**

Para receber os dados dos últimos quatro setores adicionados.

**POST: `/sector/create`**

Para criar um novo setor, envie os dados nesse formato:

```json
{
    "name": "Nome do Setor",
    "description": "Descrição do Setor",
}
```

**PUT: `/sector/update/:id`**

Para atualizar os dados do setor, envie os dados atualizados seguindo o padrão:

```json
{
   "name": "Nome do Setor",
    "description": "Descrição do Setor Atualizada",
}
```

**DELETE: `/sector/delete/:id`**

Para deletar um setor pelo `id`.
