# **zlinky-ui**
> *Exploiter la remontée d'infos du compteur Linky via le dongle Zlinky sous Node-Red*

>![schema](/img/schema-global.png)

>### Pré-requis
>>- Dongle [Zlinky](https://github.com/fairecasoimeme/Zlinky_TIC)
>>- Passerelle Zigbee ([Zigbee2Mqtt](https://github.com/Koenkk/zigbee2mqtt) dans mon cas)
>>- [Node-Red](https://nodered.org/docs/getting-started/local) (avec modules : node-red-dashboard, node-red-contrib-influxdb, node-red-contrib-cron-plus)
>>- [InfluxDB 1.8](https://docs.influxdata.com/influxdb/v1.8/introduction/install/)
>>- [Grafana](https://grafana.com/tutorials/install-grafana-on-raspberry-pi/)

>### Partie Node-Red
>>1-Créer la base de recueil des données remontées 
>>>*INFLUX -username __user__ -password __password__*
>>>*CREATE DATABASE zlinky WITH DURATION 78w*
>
>>2-Import du flow (src/zlinky.json)
>
>>![flow](/img/nodes.PNG)
>
>>![dashboard](/img/dashboard.PNG)
>
>>3-Import du model Grafana (src/grafana.json)
>
>![graphana](/img/graphana.PNG)
>
>>4-Définir les crontab
>
>>Daily -> 59 59 23 * * *
>
>>Monthly -> 58 59 23 L * *
>
>### [Article](https://www.maison-et-domotique.com/136395-lixee-zlinky-teleinfo-zigbee-linky/)
