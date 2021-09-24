CREATE TABLE
Esse comando cria uma nova tabela.

CREATE TABLE nome_tabela;
SHOW TABLE
Mostra uma tabela e os seus registros armazenados.

SHOW nome_tabela;
USE
Seleciona um banco de dados no SGBD.

USE nome_do_banco;
DROP TABLE
Exclui uma tabela.

DROP nome_tabela;
ALTER TABLE
Altera a estrutura da tabela.

ALTER TABLE nome_tabela 
RENAME novo_nome;
CRUD
Em resumo, são os comandos básicos para inserir, ler, alterar e remover os registros do banco de dados.

Insert: insere novos dados.
INSERT INTO nome_tabela 
VALUES (valores);
Select: recupera os registros através de uma consulta.
SELECT * FROM nome_tabela;
Update: atualiza registros.
UPDATE nome_tabela 
SET nome_coluna 
WHERE condição;
Delete: remove os registros especificados.
DELETE FROM nome_tabela 
WHERE condição;
 

Aqui, você pode ler mais sobre eles.

 

Consultas SQL
O objetivo deste post é aprofundar o seu conhecimento na área de consultas SQL. Por isso, reuni os principais comandos que você vai utilizar em seu banco de dados. Acompanhe:

SELECT
Sabemos que o SELECT tem o propósito de recuperar e acessar informações no banco de dados. Portanto, para utilizá-lo, basta dizer quais tabelas serão consultadas e quais dados serão requisitados.

SELECT Cliente.nome, 
Funcionario.nome 
FROM Cliente, Funcionario;
WHERE
Esse comando filtra o que você precisa pesquisar através do SELECT de acordo com os parâmetros que você passou. Para selecionar os registros, o WHERE se utiliza dos seguintes operadores e funções:

Igual (=)
SELECT cliente.nome 
FROM cliente 
WHERE id = 04;
Diferente (<>)
SELECT cliente.nome 
FROM cliente 
WHERE id <> 98;
Menor ou igual que (<=)
SELECT cliente.nome 
FROM cliente 
WHERE id <= 24;
Maior ou igual que (>=)
SELECT cliente.nome 
FROM cliente 
WHERE id >= 56;
Menor (<)
SELECT cliente.nome 
FROM cliente 
WHERE id < 165;
Maior (>)
SELECT cliente.nome 
FROM cliente 
WHERE id > 78;
IS
SELECT * FROM vendas 
WHERE pagamento_cartao 
IS TRUE;
IS NOT
SELECT * FROM vendas 
WHERE pagamento_cartao 
IS NOT TRUE;
IS NULL
SELECT * FROM vendas 
WHERE pagamento IS NULL;
IS NOT NULL
SELECT * FROM vendas 
WHERE pagamento 
IS NOT NULL;
BETWEEN AND
SELECT * FROM vendas 
WHERE pagamento_valor 
BETWEEN 1500 AND 3000;
LIKE
SELECT * FROM cliente 
WHERE nome LIKE 'Almeida%';
NOT LIKE
SELECT * FROM cliente 
WHERE nome  
NOT LIKE 'Almeida%';
IN
SELECT * FROM cliente 
WHERE id IN (04, 56, 89, 208);
NOT IN
SELECT * FROM cliente 
WHERE id NOT IN (04, 56, 89, 208);

Nesse post você pode ver mais exemplos sobre esses comandos.

ORDER BY
O ORDER BY ordena os resultados da consulta de acordo com os parâmetros especificados. Pode ser em amostragem ascendente ou descendente:

ASC
Ordena os resultados de forma ascendente.

SELECT nome FROM Cliente 
ORDER BY nome ASC
DESC
Ordena os resultados de forma descendente.

SELECT nome FROM Cliente 
ORDER BY nome DESC
Funções de Agrupamento
Servem para manipular e fazer cálculos com os dados:

COUNT
Conta a incidência dos dados.

SELECT COUNT(*) 
FROM cliente;
AVG
Faz o cálculo da média.

SELECT 
AVG(pagamento_clientes) 
FROM vendas;
SUM
Soma os dados.

SELECT 
SUM(pagamento_clientes) 
FROM vendas;
MAX
Filtra o maior número.

SELECT 
MAX(pagamento_clientes) 
FROM vendas;
MIN
Filtra o menor número.

SELECT 
MIN(pagamento_clientes) 
FROM vendas;
GROUP BY
Esse comando agrupa os dados obtidos da consulta. Desse modo, pode-se contabilizar a quantidade de incidências.

SELECT 
pagamento_cartao_credito, 
COUNT(*) FROM vendas 
GROUP BY 
pagamento_cartao_credito;
DISTINCT
Se em uma consulta você precisar eliminar resultados duplicados para poder trabalhar, o DISTINCT é o comando certo.

SELECT DISTINCT(bairro) 
FROM cliente;
LIMIT
Como o próprio nome já diz, esse comando limita a quantidade de registros exibidos na consulta.

SELECT * FROM cliente LIMIT 50;
