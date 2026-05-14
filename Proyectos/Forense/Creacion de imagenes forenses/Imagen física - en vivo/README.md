# Creacion de imagen forense RAW (Escenario 1)

## Objetivo

Demostrar de manera practica como crear una imágen forense fisica de un computador encendido con su sistema en ejecucion. 

---
### Habilidades aprendidas

- Adquisicion de copia bit a bit en vivo
- Validacion de integridad de evidencia adquirida

---
### Equipo objetivo
- Maquina virtual con Windows 10
- Estado: en funcionamiento
- Disco sin cifrar

---
## Metodologia
- Adquisicion en vivo

---
### Normativa
- ISO IEC 2037

---
## Herramientas
- Data duplicator (dd)
- HashCalc

---
# PROCEDIMIENTO TECNICO REALIZADO

1.	Hice clic derecho sobre el icono de “PowerShell” y lo ejecuté como administrador.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/b056e380-2260-4261-9e4e-08ce02d9dcfd" />


2.	En “PowerShell”, me dirigí a la ruta del directorio que contiene la herramienta “dd”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/f66c2735-c70d-4f49-85df-d2bd4811f803" />


3.	Identifiqué el disco fisico con el sistema y donde guardar la imagen forense. Para esto utilicé el comando:
    wmic diskdrive list brief /format:list 
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/53a4e6e3-cc1a-477b-9a14-827444e7379e" />

4.	Luego procedí a crear la imagen forense física. Para esto utilicé el comando:
    .\dd if=\\.\PHYSICALDRIVE0 of=I:\imagen.dd bs=512k conv=noerror,sync --progress
  	<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/c5a2ff1e-2b18-4208-b170-008f0b720da9" />



