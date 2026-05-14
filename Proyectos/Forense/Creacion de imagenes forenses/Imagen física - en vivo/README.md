# Creación de imagen forense RAW (Escenario 1)

## Objetivo

Demostrar de manera práctica cómo crear una imagen forense física de un computador encendido con su sistema en ejecución. 

---
### Habilidades aprendidas

- Adquisición de copia bit a bit en vivo  
- Validación de integridad de evidencia adquirida  

---
### Equipo objetivo
- Máquina virtual con Windows 10  
- Sistema: en funcionamiento  
- Disco sin cifrar  

---
## Metodología
- Adquisición en vivo  

---
### Normativa
- ISO IEC 2037  

---
## Herramientas
- Data duplicator (dd)  
- HashCalc  

---
## Reflexión
Si bien el procedimiento fue exitoso, recomiendo la creación de una imagen forense física o copia bit a bit empleando otros tipos de metodologías como son la adquisición muerta o en frío. La adquisición en vivo realizada está sujeta a errores debido a la copia que se hace a nivel de bit de datos que pueden estar en sectores protegidos por el sistema. Recomiendo su uso en casos excepcionales, como puede ser si el equipo objetivo es parte de una infraestructura crítica y por ello no pueda apagarse.

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

5.  Completado el proceso, pude ver la imagen forense.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/ee62607d-567a-400a-b7b9-c5bd2adae8f5" />

8.	Ejecuté la herramienta "HashCalc", dejé seleccionado únicamente el hash MD5, coloqué la ubicación de la imagen.dd e hice clic en “Calculate”
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/81b99876-93a6-4635-8429-e386f461e0eb" />

Hash MD5: 2c521aafd183b566f12293bfef12780e
