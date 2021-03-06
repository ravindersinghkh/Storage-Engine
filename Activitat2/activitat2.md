
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
     Creem els directoris i els permisos respectius:
         - sudo mkdir /discs-mysql
         - sudo chown -R mysql:mysql /discs-mysql
         - sudo chmod 750 /discs-mysql/
         - sudo mkdir /discs-mysql/disk1
         - sudo mkdir /discs-mysql/disk2
         - sudo chown -R mysql:mysql /discs-mysql/disk1
         - sudo chown -R mysql:mysql /discs-mysql/disk2
         - sudo chmod 751 /discs-mysql/disk1
         - sudo chmod 751 /discs-mysql/disk2
    </pre>
    > Canviem el datadir del Mysql a /discs-mysql/
    1. Aturem servei:
        ![image](https://user-images.githubusercontent.com/79662843/161113968-49198a07-2e48-45ba-8a3b-bd0e2d6af357.png)
    2. Movem el directori actual al nou

        ![image](https://user-images.githubusercontent.com/79662843/161115648-104e0324-9d2d-4a90-a9ce-1f6a7d61fbe6.png)

    3. Configurem `my.cnf` , posem el nou path i aixequem el servei:
        ![image](https://user-images.githubusercontent.com/79662843/161114665-e0ad5d14-c093-40ab-92c4-228dac861c33.png)
        
        ![image](https://user-images.githubusercontent.com/79662843/161117133-e5bd92b6-3058-4fdf-8669-8043188e20f7.png)

        
        ![image](https://user-images.githubusercontent.com/79662843/161116907-54f6650a-6888-41a9-9fbf-9da7ed9e5d4b.png)
        
    > Per canviar els directoris del tablespace aturarem el servei mysql i eliminarem els fitxers ibdata1. Un cop eliminat aquests fitxers, configurarem el fitxer `my.cnf` de la següent manera:
    
    ![image](https://user-images.githubusercontent.com/79662843/161117738-05c3e30b-b571-4423-84fd-3050e22152ec.png)
    
    > Comprovació: 

    ![image](https://user-images.githubusercontent.com/79662843/161118446-9a217b38-f149-4970-a949-a8c59db002d7.png)



    
