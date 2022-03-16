
#### Activitat 1. REALITZA I/O RESPON ELS SEGÜENTS APARTATS

1. Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra al comanda utilitzada i el resultat d’aquesta.

- Utilitzem la comanda `SHOW ENGINES;` Podem observar el motor per defecte actiu(InnoDB) i els que podem utilitzar.
  ![image](https://user-images.githubusercontent.com/79662843/157502753-1e9b2877-cbe5-4847-bb81-381273e0a45c.png)

2. Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?
- Per saber el motor per defecte podem utilitzar la comanda anterior `SHOW ENGINES;` amb la qual ens indica el motor per defecte.
![image](https://user-images.githubusercontent.com/79662843/157504977-5f76646b-7d4b-40c9-ba52-bc581a287222.png)
- Per canviar-ho, utilitzarem la comanda `SET default_storage_engine=MyISAM;` Aquesta comanda canviará per la sessió actual, si ho volem canviar de manera permanent, haurem de anar a configurar `/etc/my.cnf` i afegir la variable `default-storage-engine=MyISAM`.
![image](https://user-images.githubusercontent.com/79662843/157505230-7fb7af81-798f-4ffa-bef1-fa3923a76d97.png)

3. Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor). Aquest tipus d’emmagatzematge està optimitzat per ser molt eficient en les escriptures amb lectures acceptables.
Per la instal·lació, seguim els passos següents:
- Instal·lem el paquet `sudo yum install percona-server-rocksdb`
- Executem el script ps-admin un cop instal·lat el paquet `ps-admin --enable-rocksdb -u perepi -ppastanaga`
  ![image](https://user-images.githubusercontent.com/79662843/157507885-ee9f5204-c3f9-4712-acba-c4c3147dea85.png)
- Comprovem si s'ha instal·lat correctament amb `SHOW ENGINES;`
![image](https://user-images.githubusercontent.com/79662843/157508236-bb48c885-355d-4bf5-9a45-98c136c0807b.png)

4. Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM. 
Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.
Un cop fet això torna a deixar el motor InnoDB per defecte.
- Per poder importar la DB Sakila amb les taules MyISAM, modifiquem el `ENGINE` de cada taula. Repetim aquest procés amb totes les taules on el ENGINE sigui InnoDB.

![image](https://user-images.githubusercontent.com/79662843/157509345-f66c4981-b6e4-44f0-90e2-c5cd8f19255a.png)

![image](https://user-images.githubusercontent.com/79662843/157511743-0ad2be06-3dc0-4fb6-ae70-44265b4f163f.png)
- Podem observar que ha creat *3* fitxers per cada taula. Les extensions que utilitza son: `.sdi` Directori de la base de dades de la taula(metadades), `.MYD` El fitxer de dades i `.MYI` el fitxer dels índexs
![image](https://user-images.githubusercontent.com/79662843/157512297-ba069ae7-01ee-4e2e-9ac3-08dbfe7d2349.png)
- Tornem a possar el motor InnoDB:
![image](https://user-images.githubusercontent.com/79662843/157513359-3c1f207b-0297-4dd4-ba39-6633ba00e09d.png)

5. A partir de MySQL apareixen els schemas de metadades i informació guardats amb InnoDB. Busca informació d'aquests schemas. Indica quin és l'objectiu de cadascun d'ells i posa'n un exemple d'ús.
- `INFORMATION_SCHEMA` proporciona accés a les metadades de la base de dades, informació sobre el servidor MySQL, com ara el nom d'una base de dades o taula, el tipus de dades d'una columna o privilegis d'accés.
- `PERFORMANCE_SCHEMA` proporciona una manera d'inspeccionar l'execució interna del servidor en temps d'execució per supervisar el rendiment del nostre servidor
- `MYSQL SCHEMA` és l'esquema del sistema. Conté taules que emmagatzemen la informació requerida pel servidor MySQL mentre s'executa. També conté taules de diccionari de dades que emmagatzemen metadades d'objectes de base de dades i taules del sistema utilitzades per a altres propòsits operatius. 

6. Posa un exemple que produeix un DEADLOCK i mostra-ho al professor.
![image](https://user-images.githubusercontent.com/79662843/157514859-82f05c60-ea86-4ca0-930c-54dd6e6134f6.png)
- Amb un altre usuari, intenem el següent:
![image](https://user-images.githubusercontent.com/79662843/157519868-c7d29fb8-237d-40bf-9a23-e44a454aac1c.png)
- Com podem observar, ens dona un error ja que amb el primer usuari ja estem amb un lock a la taula i el segon usuari per eliminar-ho, necesita el permís que no pot tenir pel motiu esmentat anteriorment. És per mantenir la consistència de dades.
