# Sauna — instructions Copilot (Node-RED, lumières + Spotify)

Conversation Copilot sauvegardée par Luc (sauna 2.docx, avril 2024) : contrôle d'un sauna infrarouge avec Raspberry Pi, capteur DHT11, 2 relais (lumières intérieure/extérieure) et musique Spotify via Node-RED.

---

Vous
peux tu me faire un code pour raspberry pi pour controler un sauna infrarouge avec 2 relais un sensor dht11 et lumiere interieur et lumiere exterieur et la music de spotify
Copilot
Bien sûr ! Voici un exemple de code pour contrôler un sauna infrarouge avec un Raspberry Pi en utilisant un capteur DHT11, deux relais pour les lumières intérieures et extérieures, et la musique de Spotify :
Matériel requis :
Raspberry Pi 3/4 avec Raspbian OS installé
Capteur DHT11
Deux relais
Fils de connexion
Lumières intérieures et extérieures (connectées aux relais)
Haut-parleurs ou un système audio pour la musique
Configuration :
Connectez le capteur DHT11 au Raspberry Pi. Le pin de signal du capteur DHT11 est connecté au GPIO4 du Raspberry Pi. Les broches VCC et GND du capteur sont connectées respectivement aux broches +5V et GND du Raspberry Pi.
Connectez les deux relais au Raspberry Pi en utilisant les broches appropriées.
Connectez les lumières intérieures et extérieures aux relais.
Installation de Node-RED :
Assurez-vous que Node-RED est installé sur votre Raspberry Pi. Si ce n’est pas le cas, suivez les instructions pour installer Node-RED.
Exécutez la commande suivante pour démarrer Node-RED :
Configuration du tableau de bord :
Ouvrez le navigateur (sur le Raspberry Pi ou sur votre ordinateur) et accédez à l’URL : http://adresse_IP_du_Raspberry_Pi:1880.
Dans Node-RED, installez les nœuds requis :
node-red-dashboard
node-red-contrib-dht-sensor
Création du flux Node-RED :
Dans l’interface Node-RED, faites glisser les nœuds suivants dans la zone de flux central :
Inject
Function
Debug
rpi-DHT22
rpi-relay (deux fois)
Spotify (utilisez le nœud Spotify pour contrôler la musique)
Configurez les nœuds :
Inject :
Propriétés : Réglez l’intervalle d’injection (par exemple, toutes les 2 secondes).
rpi-DHT22 :
Configuration : Définissez le numéro de broche sur 4 (correspondant au signal du DHT11).
Function (pour la température) :
JavaScript
Code généré par l'IA. Examinez et utilisez soigneusement. Plus d'informations sur la FAQ.
Gauge : Connectez-le au nœud rpi-DHT22 pour afficher les données brutes.
rpi-relay (deux fois) :
Configurez chaque nœud avec le numéro de broche approprié pour les relais.
Connectez-les au nœud Function pour activer/désactiver les relais en fonction de la température.
Spotify : Utilisez ce nœud pour contrôler la musique.
Test :
Vérifiez que les relais s’activent et se désactivent en alternance en fonction de la température mesurée par le capteur DHT11.
Utilisez le nœud Spotify pour jouer de la musique dans le sauna.
N’oubliez pas d’adapter les seuils de température selon vos besoins pour contrôler le sauna. Amusez-vous bien avec votre projet Node-RED ! 🌡️🔌🎵
