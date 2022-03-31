#### Activitat 8.Storage Engine MyRocks

-	Documenta i posa exemple de com utilitzar ENGINE MyRocks. Crea una Base de dades amb 2 o 3 taules i inserta-hi contingut.
-	Cal documentar els passos que has hagut de realitzar per preparar l'exemple: configuracions, instruccions DML, DDL, etc....
1. Creem la base de dades, les taules & insertem els registres
```mysql
# Creació base de dades
CREATE DATABASE prova_rocksdb;
USE prova_rocksdb;
# Creació taula amb engine RocksDB
CREATE TABLE test1 (
i INT NOT NULL, 
c CHAR(15) NOT NULL
)ENGINE = RocksDB;
CREATE TABLE test2 (
x INT NOT NULL, 
z CHAR(15) NOT NULL
)ENGINE = RocksDB;
# Insert de dades a la taula
INSERT INTO test1 VALUES(1,'registre 1'),(2,'registre 2');
INSERT INTO test2 VALUES(1,'registre 1'),(2,'registre 2');
# Select de les taules creades
SELECT * from test1;
SELECT * from test2;
```
![image](https://user-images.githubusercontent.com/79662843/161082889-c160f978-8449-4580-8b78-14efe51f6678.png)

-	A quin directori es guarden els fitxers de dades? Fes un llistat de a on són els fitxers i què ocupen.
![image](https://user-images.githubusercontent.com/79662843/161087320-29645b05-dcd7-42dc-b9a4-fbcf82437185.png)
- Quina és la compressió per defecte que utilitza per les taules? Com ho faries per canviar-lo. Per exemple utilitza Zlib o ZSTD o sense compressió.
1. La compressió per defecte ho podem comprovar amb les següents sentències:
![image](https://user-images.githubusercontent.com/79662843/161087949-e70e97ad-c935-4b37-ba47-14d275141dc3.png)
![image](https://user-images.githubusercontent.com/79662843/161088016-09881f19-445c-4b00-9d69-589c43476edf.png)

 >Podem observar que utilitza _**KLZ4**_ per defecte

2. Per canviar-ho, haurem de configurar el fitxer ``my.cnf`` i posar les següents línies




