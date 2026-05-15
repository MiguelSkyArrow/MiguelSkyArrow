# Creación de imagen forense lógica

## Objetivo

Demostrar de manera práctica cómo crear una imagen forense lógica del contenido de un directorio. 

---
### Habilidades aprendidas

- Realización de adquisiciones lógicas    

---
### Equipo objetivo
- Máquina real con Windows 11  
- Sistema: en funcionamiento  
- Disco cifrado  

---
## Metodología
- Adquisición lógica en vivo  

---
### Normativa
- ISO IEC 2037  

---
## Herramientas
- FTK Imager  

---
## Reflexión
A diferencia de una imagen física, una imagen lógica no adquiere sectores, espacio no asignado, los clústeres ni la estructura de las particiones de manera completa. Sin embargo, con la lógica se obtienen datos tal cual los muestra el sistema de archivos, algo útil cuando no se necesita todo lo que hay en disco, sino datos concretos y relevantes según la investigación y que a diferencia de la fisica, no presenta limitantes debido a que el medio de almacenamiento se encuentre cifrado. 

---
# PROCEDIMIENTO TECNICO REALIZADO

1.	Ejecuté la herramienta “FTK Imager”
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/c6b59f8b-5af2-40c6-b702-ca611909e147" />

2.	Hice clic en “File” y luego en “Create Disk Image”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/9849b996-0f3e-4a4a-bafd-fdbd819f40f3" />

3.	Seleccioné “Contents of a Folder” e hice clic en “Siguiente >”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/b5c11aa7-1ad0-4d07-b1cb-c63f18dc50e8" />

4.	Hice clic en “Si”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/ceaaf474-b991-4754-a5c2-deb04ef41494" />

5.	Hice clic en “Browse…”
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/21cb7b06-bc42-4cfe-bd9b-16bba75c5d17" />

6.	Seleccioné la carpeta “Program Files” e hice clic “Aceptar”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/e9766484-8db5-4448-9736-ea07bed8eb46" />

7.	Hice clic en “Finish”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/57e81bc3-89f6-4b9a-96f2-55d032acdd19" />

8.	Hice clic en “Add…”
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/21adacfc-001c-4742-9ed1-bb5a6dfe4db3" />

9.	Llené la información del caso e hice clic en “Siguiente >”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/917d363a-c44f-45e4-b224-8f7f548b5a4a" />

10.	Para seleccionar un destino, hice clic en “Browse”.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/b82e538e-0b4c-448a-98b1-37c6c52056c2" />

11.	Seleccioné la ubicación de destino.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/3c8c8b8f-77ed-4c24-9714-921f0f53f518" />

12.	Coloqué un nombre e hice clic en “Finish”.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/143de09c-a8ff-4774-83fa-0c7f148f812e" />

13.	Hice clic en “Start”.
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b4f7991e-0ea8-4769-be36-9c28331e5d60" />

14.	Esperé a que se completara el proceso.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/c7b27f19-3fcf-483f-8cb3-34ac82d59fd8" />
