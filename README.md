# operador-BETWEEN-en-Oracle-SQL
#### Este operador relacional se utiliza para trabajar intervalo de valores.
```sql
 create table medicamentos(
  codigo number(6) not null,
  nombre varchar2(20),
  laboratorio varchar2(20),
  precio number(6,2),
  cantidad number(4),
  fechavencimiento date not null,
  primary key(codigo)
 );

 insert into medicamentos
  values(102,'Sertal','Roche',5.2,10,to_date('01/02/2020','dd/mm/yyyy'));
 insert into medicamentos 
  values(120,'Buscapina','Roche',4.10,200,to_date('01/12/2017','dd/mm/yyyy'));
 insert into medicamentos 
  values(230,'Amoxidal 500','Bayer',15.60,100,to_date('28/12/2017','dd/mm/yyyy'));
 insert into medicamentos
  values(250,'Paracetamol 500','Bago',1.90,20,to_date('01/02/2018','dd/mm/yyyy'));
 insert into medicamentos 
  values(350,'Bayaspirina','Bayer',2.10,150,to_date('01/12/2019','dd/mm/yyyy'));
 insert into medicamentos 
  values(456,'Amoxidal jarabe','Bayer',5.10,250,to_date('01/10/2020','dd/mm/yyyy'));
  ```
  
  >select * from medicamentos

 | codigo            | nombre           |   laboratorio   |  precio   |  cantidad   |  fechavencimiento  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:|
 | 102 | Sertal |  Roche   | 5.2   | 10 | 01/02/2020|
 | 120 | Buscapina |  Roche   | 4.10   | 200 | 01/12/2017|
 | 230 | Amoxidal 500 |  Bayer   | 15.60   | 100 | 28/12/2017|
 | 250 | Paracetamol 500 |  Bago   | 1.90   | 20 | 01/02/2018| 
 | 350 | Bayaspirina |  Bayer   | 2.10   | 150 | 01/12/2019| 
 | 456 | Amoxidal jarabe |  Bayer   | 5.10   | 250 | 01/10/2020| 
 
 
 
 ```sql
 SELECT *
FROM MEDICAMENTOS
WHERE PRECIO BETWEEN 5 AND 15;
```
 | codigo            | nombre           |   laboratorio   |  precio   |  cantidad   |  fechavencimiento  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:|
 | 102 | Sertal |  Roche   | 5.2   | 10 | 01/02/2020|
 | 456 | Amoxidal jarabe |  Bayer   | 5.10   | 250 | 01/10/2020| 
 
 
 ```sql
 select * from medicamentos where cantidad between 100 and 200 ;
 ```
 | codigo            | nombre           |   laboratorio   |  precio   |  cantidad   |  fechavencimiento  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:|
 | 120 | Buscapina |  Roche   | 4.10   | 200 | 01/12/2017|
 | 230 | Amoxidal 500 |  Bayer   | 15.60   | 100 | 28/12/2017|
 | 350 | Bayaspirina |  Bayer   | 2.10   | 150 | 01/12/2019| 
 
 
 ```sql
 --utilizando fechas
 select * from medicamentos where fechavencimiento between '01/12/17' and '01/02/18' ;
 ```
 | codigo            | nombre           |   laboratorio   |  precio   |  cantidad   |  fechavencimiento  |
 | ------------------|:----------------:|----------------:| ---------:| -----------:| ------------------:|
 | 120 | Buscapina |  Roche   | 4.10   | 200 | 01/12/2017|
 | 230 | Amoxidal 500 |  Bayer   | 15.60   | 100 | 28/12/2017|
 | 250 | Paracetamol 500 |  Bago   | 1.90   | 20 | 01/02/2018| 
 
 
