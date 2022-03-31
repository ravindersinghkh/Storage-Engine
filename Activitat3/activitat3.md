#### Activitat 3. INNODB part II. REALITZA ELS SEGÜENTS APARTATS
-	Partint de l'esquema anterior configura el Percona Server perquè cada taula generi el seu propi tablespace en una carpeta anomenada tspaces (aquesta pot estar situada a on vulgueu).
-	Indica quins són els canvis de configuració que has realitzat.

1. Activem `innodb_file_per_table=ON` al `my.cnf` per generar tablespace per cada taula.

![image](https://user-images.githubusercontent.com/79662843/161119595-bdb51ddf-779c-434a-9c9b-c094566fd37f.png)

![image](https://user-images.githubusercontent.com/79662843/161119722-0d2512ea-3b79-4e28-bcff-a0e481bdc0a3.png)


2.
