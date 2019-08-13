# Limpeza de Dados
### Questão: Acesse os dados da pesquisa da [BBC da última aula](https://docs.google.com/spreadsheets/d/18yUpkEmTbVja4KUi2_JN8Y7QyPGzzJ_yRE_FrjS-a-A/edit#gid=0). Considere que a coluna timestamp não possuialores anômalos.
### Realize a limpeza de dados. Submeta a url de um projeto contendo: 

#### - Código utilizado para sua solução (excel, python, java, ...);
#### - Arquivo final resultante da limpeza;


**Facilitando a Visualização**

```sql
/*CRIO UMA COLUNA COM O NOME ID, SENDO ELA AUTO INCREMENT*/
ALTER TABLE `table 1` ADD `id` INT NOT NULL AUTO_INCREMENT FIRST, ADD PRIMARY KEY (`id`);
```

**Limpeza dos Dados**

```sql
/*VALORES ACIMA DE 100 SÃO SUBSTITUIDOS POR 100*/
UPDATE `table 1` SET `COL 3`= 100 WHERE `COL 3`>100
```

```sql
/*VALORES ACIMA DE 100 SÃO SUBSTITUIDOS POR 100*/
UPDATE `table 1` SET `COL 4`= 100 WHERE `COL 4`>100

```

```sql
/*MÉDIA DA COLUNA 3*/
SELECT AVG(`COL 3`) FROM `table 1`
```

```sql
/*AOS VALORES VAZIOS, ADICIONA-SE A MÉDIA*/
UPDATE `table 1` SET `COL 3`=77 WHERE `COL 3`=''

```

```sql
/*MÉDIA DA COLUNA 4*/
SELECT AVG(`COL 4`) FROM `table 1`

```

```sql
/*AOS VALORES VAZIOS, ADICIONA-SE A MÉDIA*/
UPDATE `table 1` SET `COL 4`=77 WHERE `COL 4`=''
```

```sql
/*REMOVIDO O CARACTERE '%' da coluna 3*/
update `table 1` set `COL 3` = replace(`COL 3`, "%", "")

```
```sql
/*REMOVIDO O CARACTERE '%' da coluna 4*/
update `table 1` set `COL 4` = replace(`COL 4`, "%", "")

```

```sql
/*ALTERA OS VALORES TRUNCADOS*/
UPDATE `table 1` SET `COL 3`=77 WHERE `COL 3`= 'ee' 
UPDATE `table 1` SET `COL 4`=77 WHERE `COL 4`='ee'

```
```sql
/*SALVA OS DADOS EM UM .CSV*/
SELECT * FROM`table 1` INTO OUTFILE 'C:/dev/Limpesa-de-Dados/output/BBC_Results_Lesson 1_clean.csv' 
FIELDS TERMINATED BY ',' ENCLOSED BY '"' LINES TERMINATED BY '\n'

```
