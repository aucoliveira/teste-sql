# Exercícios SQL

<p align="justify">
    Teste em SQL     
</p>


## Desafio 01:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS EXISTENTES NO BD, EXIBINDO A PLACA, MODELO E FABRICANTE DE CADA UM
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

## Desafio 03:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE A QUANTIDADE DE VEÍCULOS EXISTENTES POR ANO DE FABRICAÇÃO, CONSIDERANDO APENAS OS ANOS DE FABRICAÇÃO EXISTENTES NA TABELA VEICULO.
</p>

## Desafio 04:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS NOMES DE MODELO DOS FABRICANTES “FORD”, “FIAT” E “HONDA”.'
</p>

## Desafio 05:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS QUE TEM A PLACA TERMINANDO EM “123”.'
</p>

## Desafio 06:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS FABRICADOS NOS ANOS DE 2001, 2002, 2003, 2004, 2006, 2007 E 2008.'
</p>

## Desafio 07:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS COM ANO DO MODELO ENTRE 1999 E 2016;'
</p>

## Desafio 08:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS DO MODELO “GOL”, DO FABRICANTE “VOLKSWAGEN”.'
</p>

## Desafio 09:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE OS VEÍCULOS DO MODELO “GOL”, DO FABRICANTE “VOLKSWAGEN”, QUE FORAM FABRICADOS EM 2010 OU TÊM PLACA INICIANDO COM “X”.'
</p>

## Desafio 10:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE TODOS OS VEÍCULOS DO FABRICANTE “RENAULT” QUE NÃO SEJAM DOS MODELOS “CLIO” NEM “SANDERO”, E QUE FORAM FABRICADOS ANTES DE 2015.'
</p>

## Desafio 11:
<p align="justify">Descrição:</p>
<p align="justify"> CONSULTE A LISTA DE MODELOS EXISTENTES NA TABELA MODELO QUE NÃO POSSUEM VEÍCULOS ASSOCIADOS NA TABELA VEICULO.'
</p>

## Desafio 12:
<p align="justify">Descrição:</p>
<p align="justify"> CRIE UM COMANDO PARA ALTERAR PARA 2016 O ANO DE FABRICAÇÃO DE TODOS OS VEÍCULOS DO MODELO “PALIO”, DO FABRICANTE “FIAT”, QUE ESTÃO REGISTRADOS COM ANO DE FABRICAÇÃO EM 1996.'
</p>

## Tecnologias usadas:

- [MariaDB](https://mariadb.org/download/?t=mariadb&p=mariadb&r=10.11.2&os=Linux&cpu=x86_64&pkg=tar_gz&i=systemd&m=fder): versão 10.11.2

- [DBeaver](https://dbeaver.io/): versão 23.0.0

- [Java](https://www.oracle.com/java/technologies/downloads/#java17): versão 17.0.6
- [Intellij IDEA](https://www.jetbrains.com/pt-br/idea/download/#section=linux): versão 2022.3.3