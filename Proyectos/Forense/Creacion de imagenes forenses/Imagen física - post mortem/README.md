# Creación de imagen forense RAW (Escenario 2)

## Objetivo

Demostrar de manera práctica cómo crear una imagen forense física de un computador encendido pero sin arrancar su propio sistema. 

---
### Habilidades aprendidas

- Adquisición de copia bit a bit arrancando sistema externo
- Validación de integridad de evidencia adquirida
- Preservacion de evidencia adquirida

---
### Equipo objetivo
- Máquina virtual con Windows 10  
- Sistema: sin arrancar  
- Disco sin cifrar
- UEFI configurada para permitir arranque desde medios externos 

---
## Metodología
- Adquisición en frio

---
### Normativa
- ISO IEC 2037  

---
## Herramientas
- Unidad USB flash
- Ventoy
- systemrescue
- Data duplicator (dd)    

---
## Reflexión
Procedimiento exitoso. Este tipo de procedimiento es util cuando se quiere realizar la adquisicion fisica sin necesidad de abrir el equipo para extraer el medio de almacenamiento. Requiere que la BIOS/UEFI este configurada para poder arrancar desde dispositivos externos como USB o CD. Si la configuracion no esta, se puede entrar a la BIOS/UEFI y realizar los ajustes, pero esto no siempre es una opcion viable. 

---
# PROCEDIMIENTO TECNICO REALIZADO

1.	Encendí mi máquina virtual con Windows 10 y la arranqué desde mi dispositivo USB llamado “Ventoy” con el sistema “systemrescue”. Aparte conecté otro dispositivo USB “backup” para almacenar la imagen forense.

<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/506d7945-4d5b-4bbe-a8b4-c0aeb1f6ac33" />
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/c207e22a-dc53-456f-8a12-ed08b5652f4c" />

2.	Ejecuté el comando fdisk -l para verificar los discos físicos presentes en la máquina virtual.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/a265148a-ebbf-4634-a88c-9f7ab3324c3f" />

3.	Procedí a crear un directorio llamado “mnt” con el comando mkdir 'mnt'
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/54d692e5-e455-45e9-a901-5db213ff9112" />

4.	Monté la partición de datos de “sdc” (mi memoria USB para guardar la imagen forense). Para esto utilice el comando:
    mount /dev/sdc1 /mnt
<img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/c932b8a0-b53d-4e0e-bb6e-6c9da1d1c2ec" />

5.	Utilicé el comando df -lh y luego el comando ls sobre el punto de montaje, para listar el contenido de la partición montada.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/778c28ab-e608-497d-9cd2-314814ad4593" />

6.	Procedí a crear la imagen forense física con la herramienta “dd” y a guardarla en mi memoria USB (de la cual he montado la partición de datos anteriormente). Para esto utilicé el comando dd if=/dev/sda of=/mnt/imagen.dd bs=512k conv=noerror,sync --status=progress
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/6ab0552c-7884-4346-9933-af6f1a19bc8d" />

La imagen se creo exitosamente.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/3b7e4355-dcb8-4a6c-aeaa-ff34b6c4f37c" />

7.	Lo siguiente fue obtener el hash sha256 de la imagen forense y guardarlo en un archivo de texto ubicado en “backup”. Para esto utilicé el comando sha256sum /mnt/imagen.dd > /mnt/hash_sha256.txt
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/1d0b0df6-6a1f-48b6-a0a7-7d88b52ac729" />

8.  Utilicé el comando cat para ver el hash guardado:
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/29b3573b-0cc9-4592-b996-1abdbfeb1a2f" />

Hash sha256: 95deeb54615fd269efdb5447db01b1e94cdfad802fecdf4f13ae18eb9e0d715f

8.	Terminada la adquisición, procedí a desmontar la partición montada. Para esto usé el comando umount /mnt
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/7d0528de-2356-4ee1-aaea-5488960b926a" />


9.	Expulsé de forma segura el dispositivo USB donde almacené la adquisición realizada. Para esto usé el comando eject /dev/sdc
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/3b96a91e-ad1d-4b95-afdd-a5890a549f4a" />

10.	 Finalmente, apagué el equipo. Utilicé el comando shutdown -h now
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/174d5f3a-3496-4baf-ac98-4266fadb282e" />






