# Convertir imagen dd a vdi

## Objetivo

Demostrar de manera práctica cómo convertir una imagen forense en formato RAW, obtenida con dd, a un disco duro virtual.

---
### Habilidades aprendidas

- Conversión de imagen forense a formato virtualizable  

---
## Metodología
- Conversión de imagen forense a formato virtualizable  

---
### Herramienta
- VirtualBox  

---
## Reflexión
Gracias a este procedimiento pude convertir una imagen forense obtenida en formato RAW con la herramienta dd a un disco duro virtual (VDI), formato compatible con VirtualBox, para entonces poder virtualizar el equipo desde el cual fue obtenida la imagen.

---
# PROCEDIMIENTO TECNICO REALIZADO

1.	Desde mi dispositivo USB “backup” copié hacia mi host una copia de la imagen forense adquirida y del archivo de texto que contiene su hash. Después, ejecuté “PowerShell” y me ubiqué en el escritorio.
<img width="880" height="494" alt="image" src="https://github.com/user-attachments/assets/23c0c9b6-5a5b-4f4c-8526-6de46fd8c29c" />

2.	Procedí a crear el disco VDI a partir del archivo “imagen.dd”. Para ello utilicé el comando: vboxmanage convertdd imagen.dd imagen.vdi --format VDI
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/5e22ae02-422b-4669-b4ba-65c3b8c5219b" />

<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/c2318947-687e-4444-8d5d-4888de37b893" />

Una vez completado, el archivo “imagen.vdi” estuvo listo para utilizarse.
<img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/f9f61448-f060-4c38-9a50-3a403ddb8356" />




