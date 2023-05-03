# Exercícios SQL

<p align="justify">
    Teste solicitado pela empresa Xyz;
    Sql server;


## Desafio 01:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS EXISTENTES NO BD, EXIBINDO A PLACA, MODELO E FABRICANTE DE CADA UM.
</p>

```sql
    select v.PLACA, m.NOME_MODELO, f.NOME_DO_FABRICANTE
	from VEICULO as v
	inner join MODELO as m on (v.CODIGO_MODELO = m.CODIGO_MODELO)
	inner join FABRICANTE as f 
	on (m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE);
```



## Desafio 02:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE A QUANTIDADE DE REGISTROS EXISTENTES NA TABELA VEICULO CUJO ANO DE FABRICAÇÃO É DIFERENTE DO ANO DO MODELO.'
</p>

```sql
    select count(*) as "Quantidade" from VEICULO where ANO_FABRICACAO <> ANO_MODELO;
```

## Desafio 03:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE A QUANTIDADE DE VEÍCULOS EXISTENTES POR ANO DE FABRICAÇÃO, CONSIDERANDO APENAS OS ANOS DE FABRICAÇÃO EXISTENTES NA TABELA VEICULO.
</p>

```sql
    select ANO_FABRICACAO, count(*) as "Quantidade" FROM VEICULO group by ANO_FABRICACAO; 
```

## Desafio 04:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS NOMES DE MODELO DOS FABRICANTES “FORD”, “FIAT” E “HONDA”.'
</p>

```sql
    select m.NOME_MODELO as "Modelo", F.NOME_DO_FABRICANTE as "Fabricante" from MODELO as m
	inner join FABRICANTE as f on(m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE)
	where NOME_DO_FABRICANTE like 'FORD' or NOME_DO_FABRICANTE like 'FIAT' 
	or NOME_DO_FABRICANTE like 'HONDA';
```

## Desafio 05:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS QUE TEM A PLACA TERMINANDO EM “123”.'
</p>

```sql
    select * from VEICULO where PLACA  like'%123';
```

## Desafio 06:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS FABRICADOS NOS ANOS DE 2001, 2002, 2003, 2004, 2006, 2007 E 2008.'
</p>

```sql
    select * from VEICULO where ANO_FABRICACAO >= 2001 and  ANO_FABRICACAO  <=2008;
```

## Desafio 07:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS COM ANO DO MODELO ENTRE 1999 E 2016;'
</p>

```sql
    select * from VEICULO v  where ANO_MODELO >=1999 and ANO_MODELO <= 2016;
```

## Desafio 08:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS DO MODELO “GOL”, DO FABRICANTE “VOLKSWAGEN”.'
</p>

```sql
    select v.PLACA, m.NOME_MODELO, f.NOME_DO_FABRICANTE  from VEICULO as v
	inner join MODELO as m on ( v.CODIGO_MODELO = m.CODIGO_MODELO)
	inner join FABRICANTE as f on (m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE)
	where  m.NOME_MODELO like 'GOL' and f.NOME_DO_FABRICANTE like 'VOLKSWAGEN';
```

## Desafio 09:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS DO MODELO “GOL”, DO FABRICANTE “VOLKSWAGEN”, QUE FORAM FABRICADOS EM 2010 OU TÊM PLACA INICIANDO COM “X”.'
</p>

```sql
    select v.PLACA, v.ANO_FABRICACAO, m.NOME_MODELO, f.NOME_DO_FABRICANTE  from VEICULO as v
	inner join MODELO as m on (v.CODIGO_MODELO = m.CODIGO_MODELO)
	inner join FABRICANTE as f on (m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE)
	where m.NOME_MODELO like 'GOL' and (v.ANO_FABRICACAO =2010 or PLACA like 'X%');
```

## Desafio 10:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS DO FABRICANTE “RENAULT” QUE NÃO SEJAM DOS MODELOS “CLIO” NEM “SANDERO”, E QUE FORAM FABRICADOS ANTES DE 2015.'
</p>

```sql
    select * from VEICULO as v
	inner join MODELO as m on (v.CODIGO_MODELO = m.CODIGO_MODELO)
	inner join FABRICANTE as f on (m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE)
	where f.NOME_DO_FABRICANTE ='RENAULT'
	and m.NOME_MODELO not in ('CLIO','SANDERO')
	and v.ANO_FABRICACAO < 2015; 
```

## Desafio 11:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE A LISTA DE MODELOS EXISTENTES NA TABELA MODELO QUE NÃO POSSUEM VEÍCULOS ASSOCIADOS NA TABELA VEICULO.'
</p>

```sql
    select m.NOME_MODELO from MODELO as m
	left join VEICULO as v on (m.CODIGO_MODELO = v.CODIGO_MODELO)
	where v.CODIGO_MODELO is null;
```

## Desafio 12:
<p align="justify">Descrição:</p>
<p align="justify"> CRIE UM COMANDO PARA ALTERAR PARA 2016 O ANO DE FABRICAÇÃO DE TODOS OS VEÍCULOS DO MODELO “PALIO”, DO FABRICANTE “FIAT”, QUE ESTÃO REGISTRADOS COM ANO DE FABRICAÇÃO EM 1996.'
</p>

```sql
    update VEICULO  set ANO_FABRICACAO = 2016
	where  ANO_FABRICACAO = 1996  
	and CODIGO_MODELO = (select CODIGO_MODELO from MODELO where NOME_MODELO ='PALIO'
						and CODIGO_FABRICANTE = (select CODIGO_DO_FABRICANTE from FABRICANTE
											where NOME_DO_FABRICANTE = 'FIAT'));
```

```sql
    select v.ANO_FABRICACAO, m.NOME_MODELO, f.NOME_DO_FABRICANTE
	from VEICULO as v
	inner join MODELO as m on (v.CODIGO_MODELO = m.CODIGO_MODELO)
	inner join FABRICANTE as f on (m.CODIGO_FABRICANTE = f.CODIGO_DO_FABRICANTE)
	where m.NOME_MODELO = 'PALIO';
```
