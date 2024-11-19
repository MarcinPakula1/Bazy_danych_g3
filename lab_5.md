# Zadanie 1
## 1
```sql
create table kreatura select * from wikingowie.kreatura
create table zasob select * from wikingowie.zasob
create table ekwipunek select * from wikingowie.ekwipunek
```
## 2
```sql
select * from zasob
```
## 3
```sql
select * from zasob where rodzaj = 'jedzenie'
```
## 4
```sql
select zasob.idZasobu, zasob.ilosc from ekwipunek, zasob where idKreatury like '1'  or '3' or '5'
```

# Zadnie 2
## 1
```sql
select * from kreatura where rodzaj != 'wiedzma' and udzwig >= 50
```
## 2
```sql
select * from zasob where waga >= 2 and waga <= 5
```
## 3
```sql
select * from kreatura where nazwa like '%or%' and udzwig > 30 and udzwig < 70
```

# Zadanie 3
## 1
```sql
select * from zasob where dataPozyskania like '____-07-__' or '____-08-__'
```
## 2
```sql
select * from zasob order by waga asc
```
## 3
```sql
select * from kreatura order by dataUr desc limit 5
```

# Zadanie 4
## 1
```sql
select distinct rodzaj from zasob 
```
## 2
```sql
select concat(nazwa,'-',rodzaj) as 'nazwa-rodzaj' from kreatura where rodzaj like 'wi%' 
```
## 3
```sql
select nazwa, concat(ilosc*waga) as 'całkowita waga' from zasob where year(dataPozyskania) >= 2000 and year(dataPozyskania) <= 2007
```

# Zadanie 5
## 1
```sql
select nazwa, concat((ilosc*waga)*0.7) as 'jedzenie wlasciwe', concat((ilosc*waga)*0.3) as 'odpady z jedzenia' from zasob 
```
## 2
```sql
select * from zasob where rodzaj is null
```
## 3
```sql
select distinct rodzaj from zasob where rodzaj like 'Ba%' or rodzaj like '%os' order by rodzaj
```
