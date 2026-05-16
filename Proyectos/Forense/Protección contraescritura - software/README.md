# Protección contra escritura via software

## Objetivo

Demostrar de manera práctica cómo habilitar la protección contra escritura en todos los puertos USB de un computador.

---
### Habilidades aprendidas

- Preservación de evidencia previo a la adquisición de medios de almacenamiento conectados vía USB  

---
## Metodología
- Protección contra escritura vía software  

---
### Normativa
- ISO IEC 2037  

---
### Técnica empleada
- Modificación del registro de Windows  

---
## Reflexión
Proteger un dispositivo contra escritura implica evitar que se puedan escribir nuevos datos en este, salvaguardando la integridad de la evidencia digital que contiene y su valor probatorio. Si bien, lo ideal es utilizar hardware especializado con estos fines, su uso vía software resulta ser una solución económica y eficaz en situaciones en las que se deben conectar dispositivos vía USB a la estación de trabajo forense para la adquisición física o lógica de estos, o simplemente realizarles labores de triage en vivo.

---
# PROCEDIMIENTO TECNICO REALIZADO

1.	Utilicé la combinación de teclas “Windows + R” para abrir “Ejecutar”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/991dc810-1f40-4e60-8c0e-23feba419b69" />

2.	Coloqué “regedit” e hice clic en “Aceptar”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/945013b4-da3f-4150-8be6-31c6a38c48a8" />

3.	En el editor de registro, me dirigí a la ruta: Equipo\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/611fe2c8-322d-4d72-8e45-eea5caed65aa" />

4.	Hice clic derecho en “Control” y del menú desplegable seleccioné “Nuevo” y luego “Clave”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/9820d6fc-9668-4839-a46a-5713fe2be5fa" />

5.	Renombré la clave recién creada a “StorageDevicePolicies”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/9c58a31c-2892-407e-8496-5d0b133394f1" />

6.	Hice clic derecho sobre la clave “StorageDevicePolicies”, seleccioné “Nuevo”, seguido por “Valor de DWORD (32 bits)”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/e1a7fd33-4f8e-489d-beab-53bc35e596a7" />

7.	Renombré la subclave creada a “WriteProtect”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/d1091056-43b1-45a7-bc22-b41c46f9a087" />

8.	Hice clic derecho sobre la subclave “WriteProtect” y seleccioné “Modificar”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/1249c87c-dcff-4826-86b7-fedeb21989a3" />

9.	Cambié “Información de valor” de 0 a 1 y luego hice clic en “Aceptar”.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/d482fd25-15ae-4df9-a3cb-b29d4330fec4" />

10.	Por último, procedí a cerrar la ventana del editor del registro.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/239ee313-7c0c-4aeb-a916-30116edb3519" />

11.	Conecté una memoria USB cuya etiqueta es “backup_class” y cuya letra es (D:).
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/baa38b2a-ed51-416b-81fd-8f91a3323d3f" />

12.	Hice doble clic en la unidad (D:) para acceder a la memoria.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/7fdedd85-4803-415f-af3d-da7ea6afe38a" />

13.	Intenté copiar hacia la memoria el archivo llamado “Nuevo Documento de texto”, ubicado en el escritorio.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/c06b978f-cca8-49b5-b644-facb7647bd43" />

14.	Se interrumpió la acción debido a la protección contra escritura.
<img width="1090" height="613" alt="image" src="https://github.com/user-attachments/assets/6207bf27-3eaa-4f9b-9665-699abd01ef3e" />
