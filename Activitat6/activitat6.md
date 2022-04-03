#### Activitat 6. Implementar BD Distribuïdes
Com s'ha vist a classe MySQL proporciona el motor d'emmagatzemament FEDERATED que té com a funció permetre l'accés remot a bases de dades MySQL en un servidor local sense utilitzar tècniques de replicació ni clustering.

-	Prepara un Servidor Percona Server amb la BD de Sakila
-	Prepara un segon servidor Percona Server a on hi hauran un conjunt de taules FEDERADES del primer servidor.
-	Per realitzar aquest link entre les dues BD podem fer-ho de dues maneres:
-	Opció1: especificar TOTA la cadena de connexió a CONNECTION 
-	Opció2: especifficar una connexió a un server a CONNECTION que prèviament s'ha creat mitjançant CREATE SERVER
-	Posa un exemple de 2 taules de cada opció. 
Tingues en compte els permisos a nivell de BD i de SO així com temes de seguretat com firewalls, etc...
-	Detalla quines són els passos i comandes que has hagut de realitzar en cada màquina.

> Utilitzaré un clon de la mateixa màquina percona server amb usuaris ja prèviament creats amb els permisos respectius.

![image](https://user-images.githubusercontent.com/79662843/161446980-e77f89f3-6855-4e1c-83bd-3233b7e5d34b.png)

![image](https://user-images.githubusercontent.com/79662843/161450199-f9a68ada-ca46-4f88-82ef-e7d4dc13de89.png)


> Per defecte, el engine FEDERATED està desactivat, configurarem `my.cnf` i afegirem "federated" sota [mysqld]. Reiniciem servei i comprovem.

![image](https://user-images.githubusercontent.com/79662843/161448002-bfdc6f7f-844e-429a-b04e-954c14bdda71.png)
![image](https://user-images.githubusercontent.com/79662843/161448059-4d56318c-e129-4148-a37d-983ac1fe0313.png)
![image](https://user-images.githubusercontent.com/79662843/161448086-b70d3696-0ab8-4fc0-b3a4-53ffe78f58f8.png)


> Creem una base de dades al segon servidor i les 4 taules (2 per cada opció) dins d'aquesta base de dades que utilitzarem com a exemple. 

![image](https://user-images.githubusercontent.com/79662843/161447575-925d4397-5df4-4461-94c3-7040508bebd5.png)
![image](https://user-images.githubusercontent.com/79662843/161450342-ba767904-34c5-4835-a5b4-ed24a6d51b1a.png)


**1. Opció 1: CONNECTION**

- Creem o modifiquem les taules de la següent manera amb el engine federated:
![image](https://user-images.githubusercontent.com/79662843/161449955-850de11b-030d-4ef2-9619-d13a44aa5bb6.png)

- Inserim des del primer servidor i comprovem amb un select als dos servidors
![image](https://user-images.githubusercontent.com/79662843/161449995-905e2f12-4256-4706-ac6f-7171adf7bbc3.png)
![image](https://user-images.githubusercontent.com/79662843/161450057-b837dfaa-0cc8-459b-ad9d-85df8c75710a.png)


**2. Opció 2: CREATE SERVER**
- Amb aquesta opció ens permet simplificar el fet de crear taules amb el engine federated.
![image](https://user-images.githubusercontent.com/79662843/161451086-2a574149-6ec3-4fdf-8efb-2124eb7cc8e7.png)
![image](https://user-images.githubusercontent.com/79662843/161451102-c0e9c55b-51e1-4770-8787-17ef66724963.png)
- Un cop hem creat el servidor, modifiquem les taules o creem les taules de la següent manera:
![image](https://user-images.githubusercontent.com/79662843/161450814-9017a75b-30a6-4607-9c85-b5ed888ad35b.png)

- Inserim des del primer servidor i comprovem amb un select als dos servidors

![image](https://user-images.githubusercontent.com/79662843/161451122-14f93899-6086-4487-9f2c-fd169ca150ad.png)
![image](https://user-images.githubusercontent.com/79662843/161451124-d0ba9b01-29a8-4484-8868-874c6e052b5f.png)
