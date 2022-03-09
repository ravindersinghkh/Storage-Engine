
#### Activitat 1. REALITZA I/O RESPON ELS SEGÜENTS APARTATS

1. Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra al comanda utilitzada i el resultat d’aquesta.
Utilitzem la comanda `SHOW ENGINES;` Podem observar el motor per defecte actiu i els que podem utilitzar.
![image](https://user-images.githubusercontent.com/79662843/157502753-1e9b2877-cbe5-4847-bb81-381273e0a45c.png)

2. Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor MyISAM?
Per saber el motor per defecte podem utilitzar la comanda anterior `SHOW ENGINES;` amb la qual ens indica el motor per defecte.
![image](https://user-images.githubusercontent.com/79662843/157504977-5f76646b-7d4b-40c9-ba52-bc581a287222.png)
Per canviar-ho, utilitzarem la comanda `SET default_storage_engine=MyISAM;`
![image](https://user-images.githubusercontent.com/79662843/157505230-7fb7af81-798f-4ffa-bef1-fa3923a76d97.png)

3. Com podem saber quin és el motor d'emmagatzematge per defecte?
4. Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor). Aquest tipus d’emmagatzematge està optimitzat per ser molt eficient en les escriptures amb lectures acceptables.


5. Importa la BD Sakila com a taules MyISAM. Fes els canvis necessaris per importar la BD Sakila perquè totes les taules siguin de tipus MyISAM. 
Mira quins són els fitxers físics que ha creat, quan ocupen i quines són les seves extensions. Mostra'n una captura de pantalla i indica què conté cada fitxer.
Un cop fet això torna a deixar el motor InnoDB per defecte.
6. A partir de MySQL apareixen els schemas de metadades i informació guardats amb InnoDB. Busca informació d'aquests schemas. Indica quin és l'objectiu de cadascun d'ells i posa'n un exemple d'ús.
7. Posa un exemple que produeix un DEADLOCK i mostra-ho al professor.
