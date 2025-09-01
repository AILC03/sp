
---
|  |  |
|----------|----------|
| <img width="300" src="https://github.com/user-attachments/assets/22c50836-a301-4324-b37c-b57e810fdc72" /> | <img width="300" src="https://github.com/user-attachments/assets/22f52d88-1071-4041-9b51-6f883af969a6" /> |

---


# Práctica 0: Creación instancia Amazon Web Servicec EC2, gestion básica de una Raspberry Pi 4 con grabación de consola del estudiante con Asciinema  2 streams.

**Objetivo:**  
El estudiante será capaz de crear una instancia EC2 en AWS Academy y ARM Virtual Hardware con una Raspberry pi 4, instalar Asciinema, grabar una sesión de actualización del sistema operativo con uso comandos básicas de Linux, y finalmente compartir el enlace de la grabación.

**Materiales:**
- Cuenta en AWS Academy y ARM.com (y una vez acceder a el laboratorio AVH via  https://app.avh.corellium.com/login ) con **la cuenta de ARM**.
- Software de acceso SSH (puede ser mediante el panel de AWS video incluido de Loom), incluye Microsoft Powe Shell o masOS terminal
- Acceso a Internet puede ser incluso 4G
- Tres Tabulador de navegador para revisar las indicaciones, AWS Academy y AVH

---

## Instrucciones:

### 1. Acceso a AWS Academy y creación de una instancia EC2 en Amazon Web Services:
- Ingresa a tu cuenta de **AWS Academy**, otro tabulador ARM Virtual Hardware site https://app.avh.corellium.com/login
- Crea una nueva **instancia EC2** con las siguientes especificaciones:
  - Selecciona una **Amazon Machine Image (AMI)** trabajaremos con el famoso Ubuntu 20.04 LTS.
  - Escoge el **tipo de instancia** (recomendado: t2.micro, para esta practica básica
  - Configura correctamente los **grupos de seguridad** (asegurándote de abrir el puerto 22 para SSH, este ya viene habilitado en la creación.

### 2. Conexión SSH:
- Utiliza el panel de AWS para conectarte por SSH o usa un cliente SSH (como PuTTY).
- De usar un software cliente SSH, asegúrate de conectar usando una clave privada segura, y no expongas esta clave.

### 3. Instalación de Asciinema:
- Actualiza tu sistema con los siguientes comandos:
  ```bash
  sudo apt update
  sudo apt upgrade
  ```
- Instala **Asciinema** y **figlet** usando el siguiente comando:
  ```bash
  sudo apt install asciinema, figlet
  ```
- Verifica que la instalación haya sido exitosa con:
  ```bash
  asciinema --version
  ```

### 4. Grabación con Asciinema:
- Inicia la grabación de la sesión de terminal:
  ```bash
  asciinema rec
  figlet  Practica de Asciinema por _____________
  ```
- Escribe tu **referencias, objetivos** o identificador en el terminal, precedido por el símbolo `#` (Ejemplo: `# Instalacion del depurador ....`).
- Ejecuta los comandos para actualizar el sistema y herramientas básicas:
  ```bash
  sudo apt update
  sudo apt upgrade

  # Bueno aqui  ya estaria el procedimiento a trabajar ...
  ```
- Detén la grabación con:
  ```bash
  Ctrl+D
  ```

### 5. Compartir el enlace de Asciinema:
- Una vez que se haya detenido la grabación, obtén el **enlace de la grabación** desde la interfaz de Asciinema.
- Accede al enlace de la grabación
- Documenta en markdown la revisión de la demostración que se busca evaluar, puede usar ChatGTP para ese trabajo.
- Estará listo para **comparte el link** en **iDoceo** u otras indicaciones de revisión.

**Nota Importante:**  
- Recuerda que si no validas el enlace de grabación en un plazo de **7 días**, este se **expirará** y no podrá ser compartido ni revisado.
- Por consecuencia si el docente revisa a los 7 dias con 1 segundo, su trabajo estarà borraro y sera un cero de calificación, **no dejar esta indicacion a la ligera**
- Sea eficiente de esta indicación, no hay 2das oportunidades debe practicarlo y dominar la base del curso.



--- 


**RUBRICA UNIFICADA![Screenshot 2025-02-12 at 2 23 43 p m](https://github.com/user-attachments/assets/2417cb93-15a0-4ba6-8ea3-da909b839196)
**  

# NOTA:
![Screenshot 2025-02-13 at 2 38 37 p m](https://github.com/user-attachments/assets/f627bc27-337b-47f0-8c50-7e57f47ed97d)




