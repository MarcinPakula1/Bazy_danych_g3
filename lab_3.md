# Zadania lab_3
## Zadanie 4
### 1
```sql
CREATE TABLE przetwory(
  id_przetworu INT,
  rok_produkcji INT(4) DEFAULT 1654,
  id_wykonawcy INT, 
  zawartosc VARCHAR(100),
  dodatek VARCHAR(100) default 'papryczka chili',
  id_konsumenta INT,
  PRIMARY KEY(id_przetworu),
  FOREIGN KEY(id_wykonawcy) REFERENCES postac(id_postaci),
  FOREIGN KEY(id_konsumenta) REFERENCES postac(id_postaci),
);
```
### 2
```sql
INSERT INTO przetwory VALUES(
	default, default, 1, 'bigos', default, default
);
```
## Zadanie 5
### 1
```sql
INSERT INTO postac VALUES
	(default, 'Wiking 1', 'Wiking', '1564-08-23', 100),
    (default, 'Wiking 2', 'Wiking', '1664-08-23', 40),
    (default, 'Wiking 3', 'Wiking', '1524-08-23', 120),
    (default, 'Wiking 4', 'Wiking', '1534-08-23', 104),
    (default, 'Wiking 5', 'Wiking', '1484-08-23', 215)
;
```
### 2
```sql
CREATE TABLE statek(
	  nazwa_statkU VARCHAR(150),
    rodzaj_statku ENUM('kuter', 'łajba', 'frachtowiec', 'kajak'),
    data_wodowania DATE,
    max_ladownosc INT unsigned
);
```
### 3
```sql
INSERT INTO statek VALUES
	('statek 1', 'kajak', '1543-09-11', 200),
  ('statek 2', 'łajba', '1498-03-24', 5400)
;
```
### 4
```sql
ALTER TABLE postac ADD
	funkcja VARCHAR(150)
;
```
### 5
```sql
UPDATE postac SET 
	funkcja = 'kapitan' WHERE id_postaci = 1
;
```
### 6
```sql
ALTER TABLE postac ADD(
	statek_nazwa VARCHAR(50)
);

ALTER TABLE postac ADD 
	FOREIGN KEY(statek_nazwa) REFERENCES statek(nazwa_statku)
;
```
### 7
```sql
UPDATE postac SET 
	statek_nazwa = 'statek 1' WHERE rodzaj = 'wiking' AND rodzaj= 'ptak'
;
```
### 8
```sql
DELETE FROM izba WHERE nazwa_izby = 'spiżarnia';
```
### 9
```sql
DROP TABLE izba;
```
