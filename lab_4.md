# Zadanie 1
## 1
```sql
DELETE FROM postac WHERE nazwa != 'Bjorn' and rodzaj = 'wiking' ORDER BY wiek LIMIT 2;
```
## 2
```sql
ALTER TABLE walizka DROP FOREIGN KEY walizka_ibfk_1;
ALTER TABLE przetwory DROP FOREIGN KEY przetwory_ibfk_1;
ALTER TABLE przetwory DROP FOREIGN KEY przetwory_ibfk_2;
ALTER TABLE postac CHANGE id_postaci id_postaci INT;
ALTER TABLE postac DROP PRIMARY KEY;
```
# Zadanie 2
## 1
```sql
ALTER TABLE postac ADD pesel INT(11) first;
ALTER TABLE postac MODIFY pesel char(11);
UPDATE postac SET pesel = '12345678901' WHERE nazwa = 'Bjorn';
ALTER TABLE postac ADD PRIMARY KEY(pesel);
```
## 2
```sql
ALTER TABLE postac MODIFY rodzaj ENUM('wiking', 'ptak', 'kobieta', 'syrena');
```
## 3
```sql
INSERT INTO postac VALUES( '12746872149', 10, 'Gertruda Nieszczera', 'syrena', '1950-11-11', 74, NULL, NULL);
```
# Zadanie 3
## 1
```sql

```
# Zadanie 4
## 1
```sql
INSERT INTO postac VALUES('24623159821', 11, 'Loco', 'waz', '1999-10-12', 25, NULL, NULL);
```
## 2
```sql
CREATE TABLE marynarz LIKE postac;
INSERT INTO marynarz SELECT * FROM postac WHERE statek_nazwa IS NOT NULL; #albo CREATE TABLE AS SELECT ...

```
