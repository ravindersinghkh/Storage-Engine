#### Activitat 3. INNODB part II. REALITZA ELS SEGÜENTS APARTATS
-	Partint de l'esquema anterior configura el Percona Server perquè cada taula generi el seu propi tablespace en una carpeta anomenada tspaces (aquesta pot estar situada a on vulgueu).
-	Indica quins són els canvis de configuració que has realitzat.

1. Activem `innodb_file_per_table=ON` al `my.cnf` per generar tablespace per cada taula.

![image](https://user-images.githubusercontent.com/79662843/161119595-bdb51ddf-779c-434a-9c9b-c094566fd37f.png)

![image](https://user-images.githubusercontent.com/79662843/161119722-0d2512ea-3b79-4e28-bcff-a0e481bdc0a3.png)


2. Un cop hem activar `innodb_file_per_table`, canviem la ruta del datadir com ho hem fet a l'exercici anterior
![image](https://user-images.githubusercontent.com/79662843/161438385-38986581-6aaa-47e9-a11a-669a3554263b.png)
![image](https://user-images.githubusercontent.com/79662843/161438477-342ab1a6-70ff-47fd-a07e-2707ff06c7d2.png)
3. Configurem `my.cnf`:

![image](https://user-images.githubusercontent.com/79662843/161439022-d44ec591-1981-46ab-8195-70a360465a11.png)

4. Comprovem:

![image](https://user-images.githubusercontent.com/79662843/161439006-a245588b-c603-48ff-bfef-9a115d141d3d.png)


