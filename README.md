# aula-2
sequencia e inserção em uma tabela usando dados de outra tabela 
```sql
CREATE SEQUENCE sequencia
INCREMENT 5
MINVALUE 100
MAXVALUE 999
START 100
CACHE 1;
```
```sql
--inserindo dados em uma tabela utilizando outra

INSERT INTO dept_inf(nome, num_empreg, somasalario)
SELECT D.nome COUNT(*), SUM(salario)
FROM empregado E, departamento D
WHERE E.num_dept=D.num_dept
GROUP BY D.nome
HAVING COUNT(*)>50;
```
```sql
--ATUALIZANDO TABELAS

UPDATE empregado SET salario = 2500 WHERE matricula=1;

UPDATE empregado SET salario = 2500 WHERE salario <=2000;

SELECT * FROM empregado ORDER BY matricula;

DELETE FROM empregado WHERE matricula = 1;

SELECT nome, salario FROM empregado WHERE num_depto = 1 ORDER BY nome;

SELECT nome, salario FROM empregado WHERE salario >= 3000 ORDER BY nome;

SELECT nome, salario FROM empregado WHERE num_depto = 1 AND salario >= 3000 ORDER BY nome;

SELECT nome, salario FROM empregado WHERE salario BETWEEN 2000 AND 3000; 

SELECT * FROM empregado WHERE nome LIKE 'vitor';

SELECT * FROM empregado WHERE nome LIKE '% duran';

SELECT AVG(salario) FROM empregado; 

SELECT E.nome, E.salario FROM empregado E WHERE E.salario>2500;
```
