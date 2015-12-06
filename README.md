Cabot Ovh Plugin
=====

This plugin allows you to send sms alerts using OVH api.  
To interact with the APIS, you will need an OVH account on the appropriate endpoint and create API keys for your plugin:  
- [OVH Europe](https://eu.api.ovh.com/createToken/)  
- [OVH North-America](https://ca.api.ovh.com/createToken/)  
- [So you Start Europe](https://eu.api.soyoustart.com/createToken/)  
- [So you Start North America](https://ca.api.soyoustart.com/createToken/)  
- [Kimsufi Europe](https://eu.api.kimsufi.com/createToken/)  
- [Kimsufi North America](https://ca.api.kimsufi.com/createToken/)  
- [RunAbove](https://api.runabove.com/createToken/)  

The plugin required only post rights on a specific API endpoint:  
- POST /sms/\*/users/\*/jobs

OVH allow several validity options (time limit) on the WebUI, choose the appropriate one.  

The WebUI will provide following keys:  

- APPLICATION KEY  
- APPLICATION SECRET  
- CONSUMER KEY  

please note that you will also need sms credits and several configuration on your OVH Manager WebUI, at least:  

The sms account = sms-[ovh-nichandle]-X  
login = SMS login to use  
from = a sender you have configured on your sms account using the OVH Manager WebUI (international format, for example: 0033..... )  


Finally you will have to add theses keys in your cabot .env file:  

- OVH_ENDPOINT  : OVH endpoint to use
- OVH_APPLICATION_KEY  : token APPLICATION KEY
- OVH_APPLICATION_SECRET : token APPLICATION SECRET  
- OVH_CONSUMER_KEY  : token CONSUMER KEY
- OVH_SERVICE_NAME  : your sms account
- OVH_LOGIN  : your sms login
- OVH_SENDER  : sender configured using the OVH manager WebUI

for example:
```
OVH_ENDPOINT="ovh-eu"
OVH_APPLICATION_KEY="jooChoh8thee4noo"
OVH_APPLICATION_SECRET="abaxuja9aipueno5Duot7Aiv8aeghii1"
OVH_CONSUMER_KEY="Hegoosheiseethohwiequei4Mish5eiJ"
OVH_SERVICE_NAME="sms-[ovh-nichandle]-1" (*)
OVH_LOGIN="mycabot" (*)
OVH_SENDER="mynumber" (*)
```
- (\*) created using [OVH Manager](https://www.ovh.com/manager/web/login/) WebUI  
*NOTE: you may need to switch to the old manager*

Installation
----
1. Activate the Cabot venv (if you are using python venv)
1. Run `pip install cabot-alert-ovh`
1. Add cabot_alert_ovh to the CABOT_PLUGINS_ENABLED list in *\<environment\>*.env
1. Add need variables
1. Stop Cabot
1.  Run `foreman run python manage.py syncdb`
1. Start Cabot.
