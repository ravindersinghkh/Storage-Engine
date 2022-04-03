#### REDOLOG. REALITZA ELS SEGÜENTS APARTATS
-	Com podem comprovar (Innodb Log Checkpointing):
> Amb la comanda ``SHOW ENGINE INNODB STATUS ;`` 

![image](https://user-images.githubusercontent.com/79662843/161442525-bb01c7d9-a7f0-417f-a859-4ece054a2d57.png)

-	LSN (Log Sequence Number) , L'últim LSN actualitzat a disc , Quin és l'últim LSN que se li ha fet Checkpoint

![image](https://user-images.githubusercontent.com/79662843/161442793-6a220299-4e6b-475c-9464-0241ebab5b4a.png)

-	Proposa un exemple a on es vegi l'ús del redolog
1. Redo log garanteix la durabilitat de les transaccions i evita que les pàgines brutes s'escriguin al disc en el moment de la fallada. Aquest es generat després de l'inici d'una transacció però no s'escriu quan es confirma la transacció, sinó durant l'execució de la transacció. Aleshores, en cas de nosaltres iniciar una transacció per inserir dades en una taula i per algun error, la base de dades ens dóna un error mentre fem aquesta transacció, la taula tornaria al seu estat anterior de quan vam començar a fer la transacció.

- Com podem mirar el número de pàgines modificades (dirty pages)? I el número total de pàgines?

1. Ho podem comprovar amb la comanda que hem utilitzat anteriorment a l'apartat `Buffer Pool and Memory`

![image](https://user-images.githubusercontent.com/79662843/161443025-d7a8997a-9147-49dc-a48b-2092a6e96b97.png)

2. També podem optar per una query:

![image](https://user-images.githubusercontent.com/79662843/161443087-7f30c4ce-f8c9-4c0b-adcc-e8854739df4c.png)


