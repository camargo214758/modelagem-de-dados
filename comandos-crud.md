# Comandos CRUD SQL

## Rsumo da sigla
- C-> CREAT ( INSERT, inserir dados)
- R-> READ (SELECT, leitura de dados)
- U-> UPDATE (UPDATE, atualizar dados)
- D-> DELETE (DELETE, excluir dados)

## INSERT
INSERT INTO fabricantes(nome) Values('Asus');
INSERT INTO fabricantes(nome) Values('Dell');
INSERT INTO fabricantes(nome) Values('Apple');
INSERT INTO fabricantes(nome) Values('LG');

INSERT INTO fabricantes(nome)
VALUES('Sansung'),('Microsoft'),('Brastemp');

### Produtos

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricantes_id)
VALUES('TV Led', 2000, 5, 'TV de ultima geração', 6);


INSERT INTO produtos(nome, preco, quantidade, descricao, fabricantes_id)
VALUES('iphone XYZ', 5500.79, 8, 'Smartphone caro pra caeramba', 3);

INSERT INTO produtos(nome, preco, quantidade, descricao, fabricantes_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso Ã  Internet das Coisas e bla bla bla',
    8 -- Brastemp
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memÃ³ria interna de 64GB, acesso ao iCloud.',
    4 -- Apple
),
(
    'Xbox',
    2500,
    6,
    'Console de Ãºltima geraÃ§Ã£o com acesso aos melhores jogos e bla bla',
    7 -- Microsoft
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vÃ­deo RTX',
    2 -- Asus
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    7 -- Microsoft
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versÃ£o 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    6 -- Samsung
);

## SELECT 
SELECT nome, preco FROM produtos;
SELECT preco, nome FROM produtos;

SELECT nome, preco FROM produtos WHERE preco < 3000;

SELECT nome, preco FROM produtos
WHERE preco < 3000 And preco > 2000;


SELECT nome, preco FROM produtos
WHERE fabricantes_id = 3 or fabricantes_id = 1;

select nome, fabricantes_id from produtos

select preco, descricao from produtos
order by preco;


select 
    produtos.nome,
    fabricantes.nome,
    produtos.preco,
    produtos.quantidade 
FROM produtos inner join fabricantes
ON produtos.fabricantes_id = fabricantes.id;

--INNER JOIN: comando que permite juntar duas ou mais tabelas
-- ON: comando para indicar a meneira como as tabelas sao juntas
-- AS comando qua permite dar um apeliido para as colunas

## update
update fabricantes set nome = 'LG do Brasil'
WHERE id = 4; --SEMPRE USE WHERE, SEMPRE DÊ UMA CONDIÇÃO

## DELETE
delete from produtos 
where id = 2; -- SEMPRE USE WHERE, SEMPRE DÊ UMA CONDIÇÃO



