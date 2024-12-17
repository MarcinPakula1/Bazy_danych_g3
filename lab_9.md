# Zadanie 1
## 1
```sql
-- select nazwisko from pracownik order by nazwisko

-- select imie,nazwisko,pensja from pracownik where year(data_urodzenia) > 1979

-- select * from pracownik where pensja > 3500 and pensja < 5000

-- select towar from stan_magazynowy where ilosc > 10

-- select nazwa_towaru from towar where nazwa_towaru like 'A%' 
-- or nazwa_towaru like 'B%' or nazwa_towaru like 'C%'

-- select * from klient where czy_firma != 1

-- select * from zamowienie order by data_zamowienia desc limit 10 

-- select imie, nazwisko, pensja from pracownik order by pensja limit 5

-- select * from towar where nazwa_towaru not like '%a%' order by cena_zakupu desc limit 10

-- select * from towar inner join stan_magazynowy on stan_magazynowy.towar = towar.id_towaru
-- inner join jednostka_miary on jednostka_miary.id_jednostki = stan_magazynowy.jm
-- where jednostka_miary.nazwa like 'szt' order by towar.nazwa_towaru, towar.cena_zakupu desc

-- use infs_pakulam

-- create table towar_powyzej_100(select * from __firma_zti.towar where cena_zakupu >= 100)

-- create table pracownik_50_plus(select * from __firma_zti.pracownik where year(data_urodzenia) <= '1974')
```
## 2
```sql
-- select imie, nazwisko, dzial.nazwa from pracownik inner join dzial on dzial.id_dzialu = pracownik.dzial

-- select towar.nazwa_towaru, kategoria.nazwa_kategori, stan_magazynowy.ilosc from towar 
-- inner join kategoria on kategoria.id_kategori = towar.kategoria inner join stan_magazynowy on 
-- stan_magazynowy.towar = towar.id_towaru order by ilosc desc

-- select * from zamowienie inner join status_zamowienia on 
-- status_zamowienia.id_statusu_zamowienia = zamowienie.status_zamowienia 
-- where nazwa_statusu_zamowienia = 'anulowane'
```
