# Zadanie 1
## 1
```sql
insert into kreatura select * from wikingowie.kreatura

create table uczestnicy select * from wikingowie.uczestnicy;
create table etapy_wyprawy select * from wikingowie.etapy_wyprawy;
create table sektor select * from wikingowie.sektor;
create table wyprawa select * from wikingowie.wyprawa;
```
## 2
```sql
select kreatura.nazwa from kreatura inner join wyprawa on 
wyprawa.id_wyprawy = kreatura.idKreatury 
where data_rozpoczecia is null
```
## 3 
```sql
select distinct(wyprawa.nazwa), sum(ilosc) from wyprawa
inner join uczestnicy on uczestnicy.id_wyprawy = wyprawa.id_wyprawy
inner join kreatura on kreatura.idKreatury = uczestnicy.id_uczestnika
inner join ekwipunek on ekwipunek.idKreatury = kreatura.idKreatury
group by wyprawa.nazwa
```
