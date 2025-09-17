<img width="640" height="400" alt="image" src="https://github.com/user-attachments/assets/b2745ef6-a1f9-4a59-91cb-3cd69fd612bf" />



# 📘 Práctica: Servidor Flask con Dashboard del Clima usando Tailscale

## 🌟 Objetivo
- Crear un servidor Flask que obtenga datos del clima desde OpenWeatherMap.
- Mostrar un mini dashboard web con colores que reflejen el estado del clima.
- Ejecutar el servidor directamente desde el teléfono (Android o iOS).
- Usar Tailscale para acceder remotamente al dashboard desde otro dispositivo dentro de la red privada.

---

## 📊 Requisitos
- Cuenta gratuita en [https://openweathermap.org/](https://openweathermap.org/) y clave API.
- Tailscale instalado en el teléfono y en otro dispositivo de prueba.
- Red Tailscale activa para ambos nodos.

---

## 📱 Parte A: Instalación en Android (usando Termux)

### 1. Instalar Termux desde F-Droid o Google Play

### 2. Instalar Python y Flask
```bash
pkg update && pkg upgrade
pkg install python
pip install flask requests
```

### 3. Crear `app.py`
```python
from flask import Flask
import requests

app = Flask(__name__)

API_KEY = "TU_API_KEY"
CITY = "NombreCiudad"

@app.route("/")
def clima():
    url = f"http://api.openweathermap.org/data/2.5/weather?q={CITY}&appid={API_KEY}&units=metric"
    data = requests.get(url).json()
    temp = data["main"]["temp"]
    weather = data["weather"][0]["description"]
    color = "lightblue" if temp < 10 else "lightgreen" if temp < 25 else "salmon"
    return f"""
    <html><body style='background-color:{color};'>
    <h1>Clima en {CITY}</h1>
    <p>Temperatura: {temp} °C</p>
    <p>Condiciones: {weather}</p>
    </body></html>
    """

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

### 4. Ejecutar el servidor
```bash
python app.py
```

### 5. Acceder al dashboard desde otro nodo Tailscale
```plaintext
http://100.x.y.z:5000
```
Usar la IP de Tailscale del teléfono Android.

---

## 🌐 Parte B: Instalación en iOS (usando iSH Shell)

### 1. Instalar iSH Shell desde la App Store

### 2. Instalar Python y pip
```sh
apk update
apk add python3 py3-pip
```

### 3. Instalar Flask
```sh
pip3 install flask requests
```

### 4. Crear archivo `app.py` con el mismo contenido mostrado arriba
Puedes usar `vi`, `nano`, o copiar desde Safari usando `echo`:
```sh
echo 'CODIGO_AQUI' > app.py
```

### 5. Ejecutar Flask
```sh
python3 app.py
```

### 6. Verificar desde otro nodo
Accede a:
```plaintext
http://100.x.y.z:5000
```
Usar la IP privada de Tailscale asignada al iPhone por la app Tailscale.

---

## 🛡️ Seguridad y opciones avanzadas
- Puedes usar **Tailscale Serve** para evitar especificar puertos.
- Con **Tailscale Funnel**, puedes exponer el dashboard públicamente con HTTPS.
- Activa **MagicDNS** para acceder por nombre en lugar de IP.

---

## ✅ Resultado esperado
- Flask corriendo en el teléfono.
- Dashboard accesible desde otra máquina del tailnet.
- Colores que reflejan condiciones climáticas.

## 🎥 Para iphone favor de:
Graba en Loom.com un demo mostrando el dashboard y la IP de Tailscale usada.


