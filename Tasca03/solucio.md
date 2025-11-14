

* **Configuració Inicial**: Crear un grup de volums (VG) i un volum lògic (LV) utilitzant inicialment un mínim de dos discs durs (simulats) de 10 GB de capacitat. Aquest volum haurà estar formatat i muntat automàticament al sistema mitjançant l’edició de l’arxiu /etc/fstab.

Creem la màquina on li assignarem el nom corresponent  
![][image1]  
Assignem la quantitat de recursos que li donarem a la máquina  
![][image2]

Comencem a crear els discos on s'observa que se li assigna 10GB  
![][image3]  
En aquesta imatge podem observar com s'han creat els discos corresponents  
![][image4]  
Muntem els discos  
![][image5]

Els VG són com a particions així que perquè ens siguin útils haurem de formatar-los amb un sistema d'arxius  
![][image6]

Per a poder utilitzar el VG haurem d'utilitzar la comanda mount per a muntar el volum  
![][image7]  
Seguidament anirem a aquest fitxer per a modificar-lo de manera que el LV aquest muntat de manera permanent  
![][image8]  
Aquesta comanda serveix per a fer comprovacions  
![][image9]

* **Alta Disponibilitat**: Implementar la configuració d’un mirall (lvm\_mirror) que protegeixi la informació davant la fallada d'un disc.

Aquí fem pvs per a veure els discos muntats  
![][image10]

Creem el VG mirror amb els 2 discos  
![][image11]  
Creem un LV de 90Mb del mirror  
![][image12]  
Aquí comprovem que s'ha fet correctament  
![][image13]

* **Instantànies** (snapshots):  Crear i afegir dos discos de 10 GB al grup de volums. Crear un volum (lvm\_dades) amb el primer disc afegit, formatar-lo i muntar-lo. A continuació afegir arxius al volum (poden ser imatges d’Internet). Usar el segon disc afegit per crear un snapshot (lv\_snapshot) i documentar com es pot restaurar aquest snapshot, si per exemple, la informació del volum original es danyés.

Crearem un volum denominat lmv\_\*dades  
![][image14]  
Muntem la còpia per a veure el contingut	  
![][image15]  
Muntem el volum creat  
![][image16]  
Modifiquem l'arxiu de manera que sigui permanent el muntatge de l'arxiu  
![][image17]  
Creem un arxiu on el posarem en la carpeta de lvm\_\*dades  
![][image18]  
En aquesta imatge crearem un altre LV denominat lv\_\*snapshot, on se li crea una carpeta  
![][image19]  
Seguidament es prossegueix a muntar el LV  
![][image20]

En aquesta imatge ho muntem de manera permanent  
![][image21]  
Movem l'arxiu a la carpeta  
![][image22]  
Seguidament creem el següent LV  
![][image23]  
Aquí comprovem que s'han creat correctament  
![][image24]  
Aquí en la imatge es muntem els discos  
![][image25]

* **Escalabilitat**: Demostrar el procés d'ampliació*.* Usar l’espai que quedi lliure dins el grup de volums per ampliar el volum lv\_dades.

Fem el següent comando que ens permet estendre el volum del LV

![][image26]


























[Tornar a l'enunciat](README.md)[T03 proj 3.md](https://github.com/user-attachments/files/23551674/T03.proj.3.md)

