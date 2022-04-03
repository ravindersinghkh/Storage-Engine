#### INNODB part III. REALITZA ELS SEGÜENTS APARTATS

-	Crea un tablespace anomenat 'ts1' situat a /discs-mysql/disc1/ i col·loca les taules actor, address i category de la BD Sakila.
-	Crea un altre tablespace anomenat 'ts2' situat a /discs-mysql/disc2/ i col·loca-hi la resta de taules.
-	Comprova que pots realitzar operacions DML a les taules dels dos tablespaces.
-	Quines comandes i configuracions has realitzat per fer els dos apartats anteriors?

1. Creació ts1 amb les taules respectives:

![image](https://user-images.githubusercontent.com/79662843/161439758-793d8c20-47d4-4ea2-8f36-e6f1f2561c22.png)

![image](https://user-images.githubusercontent.com/79662843/161439764-7b5db454-8670-4b91-bd5c-363178fc4fb8.png)

-Comprovació de la creació del tablespace:
![image](https://user-images.githubusercontent.com/79662843/161439950-3f300e45-78aa-4e98-a74a-04157003b5cc.png)


2. Creació ts2 amb les taules respectives:

![image](https://user-images.githubusercontent.com/79662843/161440971-bc340216-cdc9-4f15-acdd-8a670afa58e2.png)

![image](https://user-images.githubusercontent.com/79662843/161440978-398bb562-e868-4c39-9921-405ecaa5b597.png)

-Comprovació de la creació del tablespace:
![image](https://user-images.githubusercontent.com/79662843/161441004-91686fca-19be-4ce0-8fe3-75a66b986f2f.png)


3. Finalment, comprovem les operacions DML:
  - ts1:

  ![image](https://user-images.githubusercontent.com/79662843/161441386-3616472d-0b1e-4628-8df1-8b13842f210c.png)

  - ts2:

  ![image](https://user-images.githubusercontent.com/79662843/161441464-2ed75042-e312-4ab6-8a76-d301dd0c0ac2.png)

