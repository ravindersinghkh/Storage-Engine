
#### Activitat 2. REALITZA I/O RESPON ELS SEGÜENTS APARTATS

1. Desactiva l’opció que ve per defecte de innodb_file_per_table
    - Desactivem per la sessió actual amb aquesta comanda, en cas de voler fer-ho permanent, haurem de configurar el fitxer my.cnf i posar sota [mysqld] `innodb_file_per_table=0`
    
     ![image](https://user-images.githubusercontent.com/79662843/158659481-91b6d186-d20c-4e58-a9c5-1765c2d599e6.png)

2. Importa la BD Sakila com a taules InnoDB. 
   
   ![image](https://user-images.githubusercontent.com/79662843/158660122-d1dfee85-e893-4ecf-8d06-7ae99f22336e.png)

    
3.	Quin/quins són els fitxers de dades? A on es troben i quin és la seva mida?
    - Amb innodb_file_per_table desactivat, tots aquests tipus d'informació d'InnoDB es guarden a ibdata1. Es troben a `/var/lib/mysql`
    
    ![image](https://user-images.githubusercontent.com/79662843/158663009-8907daa9-db1e-4734-9dd3-6287bd8e9424.png)

    
4.	Canvia la configuració del MySQL per:
    - Canviar la localització dels fitxers del tablespace de sistema per defecte a /discs-mysql/
    - Tinguem dos fitxers corresponents al tablespace de sistema.
    - Tots dos han de tenir la mateixa mida inicial (10MB) 
  	- El tablespace ha de créixer de 5MB en 5MB.
    - Situa aquests fitxers (de manera relativa a la localització per defecte) en una nova localització simulant el següent:
    - /discs-mysql/disk1/primer fitxer de dades → simularà un disc dur
    - /discs-mysql/disk2/segon fitxer de dades → simularà un segon disc dur.
    <pre>
     Creem els directoris:
         - sudo mkdir /discs-mysql/disk1
         - sudo mkdir /discs-mysql/disk2
         - sudo chown -R mysql:mysql /discs-mysql/disk1
         - sudo chown -R mysql:mysql /discs-mysql/disk2
         - sudo chmod 751 /discs-mysql/disk1
         - sudo chmod 751 /discs-mysql/disk2
    </pre>
     ![image](https://user-images.githubusercontent.com/79662843/161110509-543f13e2-3165-4bc9-ba31-e462ba2ddd98.png)

    > Editem el fitxer my.cnf amb la següent configuració:
    
    ![image](https://user-images.githubusercontent.com/79662843/158665807-9208b16f-469f-4560-b75d-18241e0e1d19.png)

    
