# AWS-Lambda-Python

En esta practica pondremos el ejemplo de trabajar con python y discord, junto a AWS.

Empezamos instalando el python y dentro de la carpeta "venv", crearemos un *.py* para donde pondremos el siguiente código:

```
# importamos las librerias necesarias
from discord_webhook import DiscordWebhook, DiscordEmbed
import json
import requests

# Creamos el webhook y el embed, sustituyendo el enlace al webhook por el que hayamos creado en Discord
webhook = DiscordWebhook(url="https://discord.com/api/webhooks/1216767578244907118/QHTg_BCa9ZCQ3CnjRststHRgywHMUlqJ1f9AlEtTh5EbRTfS1XEtEXZEFEXqHfGcn90Z")

# Creamos el embed
embed = DiscordEmbed(
    # titulo, descripcion y color del embed
    title="Taco Love",
    description="Tu taquito ya está!",
    color="03b2f8")

# Añadimos la imagen del taco al mensaje
embed.set_image(url="https://cdn1.img.sputnikglobe.com/img/07e4/0a/04/1080663158_0:0:1366:1503_1920x0_80_0_0_0c0567aad577ba67af97990f2da18984.jpg")
# Añadimos el embed al webhook
webhook.add_embed(embed)
# Ejecutamos el webhook, enviando el mensaje a Discord
webhook.execute()



def lambda_handler(event, context):
    # TODO implement
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Discord Lambda!')
    }
```

Ahora, para que nos funcionen las librerias, tenemos que instalar