# comandos SQL para modelagem fisica

## Criar bando de dados
CREATE DATABASE vendas_claudio camargo CHARACTER SET utf8mb4;

## Entrar no banco de dados criado
USE DATABASE vendas_claudio;

## criar tabale fabricantes
CREATE TABLE fabricantes (
id int not null auto_increment primary key, 
nome varchar(45) not null

);

CREATE TABLE produtos(
    id int not null auto_increment primary key,
    nome varchar(45) not null,
    preco decimal(8,2) not null,
    quantidade smallint null,
    descricao text(1000) not null,
    fabricantes_id int not null
);

## Alterando a tabela para criar relacionamento por meio da chave estrangeira
ALTER TABLE produtos 
ADD constraint fk_produtos_fabricantes
Foreign key (fabricantes_id) References fabricantes(id); 