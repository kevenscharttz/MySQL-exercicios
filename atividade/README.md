### Atividade 1 - selecionar todos os nomes da tabela de gafanhotos que sejam do sexo feminino.
```sql
SELECT nome FROM gafanhotos
WHERE sexo = 'F';
```

### Atividade 2 - Uma lista com todos os dados daqueles que nasceram entre 01/01/2000 e 31/12/2015.
```sql
SELECT * FROM gafanhotos WHERE nascimento BETWEEN '2000-01-01' AND '2015-12-31'
ORDER BY nascimento;
```

### Atividade 3 - Uma lista com os nomes de todos os homens que trabalham como Programador.
```sql
SELECT nome FROM gafanhotos
WHERE profissao = 'Programador' AND sexo = 'M';
```

### Atividade 4 - Uma lista com os dados de todas as mulheres que nasceram no Brasil, com nomes que começam com J
```sql
SELECT * FROM gafanhotos 
WHERE sexo = 'F' AND nacionalidade = 'Brasil'
AND nome LIKE 'J%';
```

### Atividade 5 - Uma lista com os nomes e nacionalidades de todos os homens com menos de 100kg
```sql
SELECT nome, nacionalidade FROM gafanhotos
WHERE nome LIKE '%_silva' AND peso < '100';
```

### Atividade 6 - A maior altura dos homens que nasceram no Brasil;
```sql
SELECT AVG(peso) FROM gafanhotos;
```
SELECT MAX(altura) FROM gafanhotos
WHERE sexo = 'M' AND nacionalidade = 'Brasil';

### Atividade 7 - A média de peso dos gafanhotos;
```sql
SELECT AVG(peso) FROM gafanhotos;
```

### Atividade 8 - Qual o menor pedo entre as gafanhotas mulheres que nasceram fora do Brasil e entre 01-01-1990 e 21-10-2000
```sql
SELECT MIN(peso) FROM gafanhotos 
WHERE sexo = 'F' AND nacionalidade = 'Brasil'
AND nascimento BETWEEN '1990-01-01' AND '2000-12-31';
```

### Atividade 9 - Quantos gafanhotos mulheres têm mais de 1.90m de altura?
```sql
SELECT COUNT(sexo = 'F') FROM gafanhotos
WHERE altura > '1.90'; 
```

### Atividade 10 - Uma lista com as profissões dos gafanhotos e seus respectivos quantitativos
```sql
SELECT profissao, count(*) FROM gafanhotos
GROUP BY profissao;
```

### Atividade 11 - Quantos gafanhotos homens e mulheres nasceram após 01/01/2005

```sql
SELECT sexo, COUNT(*) FROM gafanhotos
WHERE nascimento > 2005-01-01
GROUP BY sexo;
```


### Atividade 12 - Uma lista com os gafanhotos que nasceram fora do Brasil, mostrando o país de origem e o total de pessoas nascidas lá. Só nos interessam os países que tiverem mais de 3 gafanhotos com essa nacionalidade

```sql
SELECT nacionalidade, count(*) FROM gafanhotos 
WHERE nacionalidade != 'Brasil' 
GROUP BY nacionalidade  
HAVING count(nacionalidade) > 3;
```



