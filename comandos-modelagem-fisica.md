# Comandos SQL

Comandos usados para a modelagem física.

## Criar banco de dados

```sql
CREATE DATABASE exemplo_camila CHARACTER SET utf8mb4;
```
## Entrar no banco de dados para usá-lo
```sql
USE DATABASE exemplo_camila;
```
## Criar a tabela de fabricantes
```sql
CREATE TABLE fabricantes(
    id TINYINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR (45) NOT NULL 
);
```
## Criar tabela produtos
```sql
CREATE TABLE produtos (
    id SMALLINT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR (45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id TINYINT
);
```
## Alterando a tabela produtos para criar um relacionamento a partir da coluna fabricante_id, com a coluna id da tabela fabricantes
```sql
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);
```