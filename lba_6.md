# Zadanie 1
## 1
```sql
select avg(waga) from kreatura where rodzaj = 'wiking'
```
## 2
```sql
select avg(waga), count(idKreatury), distinct(rodzaj) from kreatura group by rodzaj
```
## 3
```sql
select distinct(rodzaj), avg(concat(2024-year(dataUr))) from kreatura group by rodzaj
```
# Zadanie 2
## 1
```sql
select distinct(rodzaj), sum(waga) from zasob group by rodzaj
```
## 2
```sql
select distinct(nazwa), avg(waga) from zasob where ilosc >= 4 group by nazwa having avg(waga) > 10
```
## 3
```sql
select distinct(rodzaj), count(nazwa) from zasob where ilosc > 1 group by rodzaj
```
# Zadnanie 3
## 1
```sql
select distinct(kreatura.nazwa), sum(ekwipunek.ilosc) from ekwipunek inner join
kreatura on kreatura.idKreatury = ekwipunek.idZasobu group by kreatura.nazwa
```
## 2
```sql
select distinct(kreatura.nazwa), group_concat(zasob.nazwa) from ekwipunek inner join
kreatura on ekwipunek.idKreatury = kreatura.idKreatury inner join zasob on 
ekwipunek.idZasobu = zasob.idZasobu group by kreatura.nazwa
```
## 3
```sql
select kreatura.nazwa from kreatura left join ekwipunek on 
ekwipunek.idKreatury = kreatura.idKreatury where ekwipunek.idKreatury is null
```
# Zadanie 4
## 1
```sql
select distinct(kreatura.nazwa), group_concat(zasob.nazwa) from ekwipunek inner join
kreatura on ekwipunek.idKreatury = kreatura.idKreatury inner join zasob on 
ekwipunek.idZasobu = zasob.idZasobu where dataUr like '167_-__-__' and 
kreatura.rodzaj like 'wiking' group by kreatura.nazwa
```
## 2
```sql
select kreatura.nazwa from kreatura inner join ekwipunek on 
ekwipunek.idKreatury = kreatura.idKreatury inner join zasob on
zasob.idZasobu = ekwipunek.idZasobu where zasob.rodzaj like 'jedzenie'
order by kreatura.dataUr asc limit 5
```
## 3
```sql
select k1.idkreatury, k1.nazwa as nazwa_kreatury_1, k2.idKreatury, k2.nazwa as 
nazwa_kreatury_2 from kreatura k1 join kreatura k2 on k1.idKreatury + 5 = k2.idKreatury
```
# Zadanie 5
## 1
```sql

```
