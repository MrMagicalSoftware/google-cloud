# 6-creating internal and external static ip addresses


controllare che sia presente vpc default 

![Screenshot 2024-11-17 alle 17 38 13](https://github.com/user-attachments/assets/903b32a0-c224-49dd-a9fc-57500106d8c4)

**controllare che sia presente default vpc**

![Screenshot 2024-11-17 alle 17 38 42](https://github.com/user-attachments/assets/3a7e2f56-b7b3-4323-b27c-bfa3c22e9b14)

per fare una demo mi serve una istanza VM
vado nel menù Compute Engine

![Screenshot 2024-11-17 alle 17 40 32](https://github.com/user-attachments/assets/55d29a20-c15d-44fb-b4e5-e310b164b1ac)

quindi creo una nuova istanza :


![Screenshot 2024-11-17 alle 17 41 14](https://github.com/user-attachments/assets/da73993e-9e39-426a-9c27-caf861b18ccf)


in machine type seleziono e2-micro ( 2vCpu , 1gb memory )


![Screenshot 2024-11-17 alle 17 42 35](https://github.com/user-attachments/assets/ef4d48dc-c703-46a8-8fcf-ef197dd89601)


seleziono la voce di networking

![Screenshot 2024-11-17 alle 17 44 17](https://github.com/user-attachments/assets/dbf8652f-274b-4d15-82aa-9894a619bf14)


Seleziono **reserve static internal ip address**


![Screenshot 2024-11-17 alle 17 45 23](https://github.com/user-attachments/assets/5431e5b2-4cc2-410f-89f7-9538c2de6e48)

![Screenshot 2024-11-17 alle 17 46 11](https://github.com/user-attachments/assets/9bf5051f-aade-48df-907d-926a7883434f)



Una volta che la vm sarà creata si presenterà in questo modo :

![Screenshot 2024-11-17 alle 17 46 52](https://github.com/user-attachments/assets/bd00f048-5143-4b95-ae48-d07244369ad5)


![Screenshot 2024-11-17 alle 17 48 05](https://github.com/user-attachments/assets/79453c71-4638-4d3f-8b49-6938521c9c65)


**static ip address persist eaven the resourses has been deleted**
per dimostrare questo , cancello l'istanza che ho creato

![Screenshot 2024-11-17 alle 17 50 01](https://github.com/user-attachments/assets/dc5a36f5-7986-45ed-a0a4-629c3a7e40bc)


uso nuovamente il comando :

```
gcloud compute addresses list

```
NOTO CHE L'INDIRIZZO IP è ANCORA DISPONIBILE!


°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°

mostriamo ora come avviene la promozione EPHEMERAL(Automatic)
Creo nuovamente la VM con queste caratteristiche :



![Screenshot 2024-11-17 alle 17 56 32](https://github.com/user-attachments/assets/f3caaf4f-e09d-4614-86eb-a582e6874bd4)



Seleziono ora l'istanza :

![Screenshot 2024-11-17 alle 19 00 08](https://github.com/user-attachments/assets/c29ec92a-16d6-4418-8b3c-1da4704dab93)


![Screenshot 2024-11-17 alle 19 47 40](https://github.com/user-attachments/assets/3231d982-a43f-4a38-87fd-94d5e1435761)




![Screenshot 2024-11-17 alle 19 48 39](https://github.com/user-attachments/assets/38dd280b-0d63-4635-9def-e0b9395eeeeb)


![Screenshot 2024-11-17 alle 19 51 05](https://github.com/user-attachments/assets/e39b6c34-8f15-4b5e-a64e-47011b862176)



![Screenshot 2024-11-17 alle 19 58 48](https://github.com/user-attachments/assets/d4152b77-5007-4012-96a3-4c2c4149298a)


```
gcloud compute addresses list

```

_________________________________________________


**external IP**

Cancello ISTANZA DELLA VIRTUAL MACHINE CREATA

Vado in vpc network :

![Screenshot 2024-11-17 alle 20 03 06](https://github.com/user-attachments/assets/6c3a2695-b899-49b7-9d15-9715b4ed4e75)

![Screenshot 2024-11-17 alle 20 03 52](https://github.com/user-attachments/assets/bf265f24-b8dd-4d0a-bf53-f4cd4b5b97d8)


NOTA : PREMIUM ha un costo maggiore 

NOTA : STATIC IP ADDRESSES NOT ATTACHED TO AN INSTANCE OR LOAD BALANCER ARE BILLED AT AN HOURLY RATE

![Screenshot 2024-11-17 alle 20 06 45](https://github.com/user-attachments/assets/9546a51d-939b-4a0d-aa26-fa377e8dbcc7)
![Screenshot 2024-11-17 alle 20 07 29](https://github.com/user-attachments/assets/8a21c677-55c8-4782-ac97-662bd1b3847e)

![Screenshot 2024-11-17 alle 20 08 23](https://github.com/user-attachments/assets/0e8b5033-2611-4c2c-b1a5-b02aad9996bb)

![Screenshot 2024-11-17 alle 20 12 27](https://github.com/user-attachments/assets/fef83b64-b097-481f-b53f-b52323850f6a)

![Screenshot 2024-11-17 alle 20 13 33](https://github.com/user-attachments/assets/b6d8dab7-8e92-454a-bbf6-dbc5e2fba0d8)


```
gcloud compute addresses list

```



















