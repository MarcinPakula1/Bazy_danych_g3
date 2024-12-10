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
# Zadanie 2
## 1
```sql
select wyprawa.nazwa, count(uczestnicy.id_uczestnika), group_concat(distinct(kreatura.nazwa))
from wyprawa inner join uczestnicy on uczestnicy.id_wyprawy = wyprawa.id_wyprawy inner join
kreatura on uczestnicy.id_uczestnika = kreatura.idKreatury group by wyprawa.nazwa
```
## 2
```sql
select distinct(wyprawa.nazwa, wyprawa.data_rozpoczecia, etapy_wyprawy.kolejnoscs, sektor.nazwa
kreatura.nazwa) from etapy_wyprawy inner join sektor on etapy_wyprawy.sektor = sektor.id_sektora
inner join wyprawa on etapy_wyprawy.idWyprawy = wyprawa.id_wyprawy inner join kreatura on
kreatura.idKreatury = wyprawa.kierownik order by wyprawa.data_rozpoczecia, etapy_wyprawy.kolejnosc
```
# Zadanie 3
## 1
```sql
select sektor.nazwa, count(etapy_wyprawy.sektor) from sektor left join etapy_wyprawy on
sektor.id_sektora = etapy_wyprawy.sektor group by sektor.nazwa
```
## 2
```sql
select kreatura.nazwa, if(count(uczestnicy.uczestnicy_id) > 0, 'bral udzial w wyprawie', 'nie bral udzialu w wyprawie')
from uczestnicy right join kreatura on kreatura.idKreatury = uczestnicy.id_uczestnika group by kreatura.nazwa
```
# Zadanie 4
## 1
```sql
select wyprawa.nazwa, sum(lenght(etapy-wyprawy.dziennik)) from wyprawa inner join eatpy_wyprawy on
wypraw.id_wyprawy = etapy_wyprawy.idWyprawy group by wyprawa.nazwa having sum(lenght(etapy_wyprawy.dziennik)) < 400
```
## 2
```sql
select wyprawa.nazwa, sum(zasob.waga * zasob.ilosc)/count(uczestnicy.id_uczestnika) from wyprawa
right join uczdestnicy on uczestnicy.id_wyprawy = wyprawa.id_wyprawy inner join kreatura on
kreatura.idKreatury = uczestnik.id_uczestnika inner join ekwipunek on ekwipunek.idKreatury =
kreatura.idKreatury left join zasob on zasob.idZasobu = ekwipunek.idZasobu group by wyprawa.nazwa
```
# Zadanie 5
## 1
```sql
select distinct(kreatura.nazwa), datediff(wyprawa.data_rozpoczecia, kreatura.dataUr) from kreatura
inner join uczestnicy on uczestnicy.id_uczestnika = kreatura.idKreatury inner join wyprawa on
wyprawa.id_wyprawy = uczestnicy.id_wyprawy inner join eatpay_wyprawy on etapy_wyprayw.idWyprawy =
wyprawa.idWyprawy inner join sektor on sektor.id_sektora = etapy_wyprawy_sektor where sektor.nazwa =
'Chatka dziadka'
```
