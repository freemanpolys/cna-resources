TP Docker: Déploiement du catalogue DSI

0-) Se conecter en ssh
IP: 10.100.46:105
USER: studentN  (N: 1..5)
PWD: sonatel

1-)  ## Vérifier le status des Container
--> docker ps

2-) ## Créer l'image Docker (GROUP_NUMBER: 1..5)
docker build -t catalogue-dsi:GROUP_NUMBER.0.0 .

Ex: docker build -t catalogue-dsi:2.0.0 .

3-)  ## Afficher la liosdte des images
--> docker images

4-) ## Démarrer le Container Docker sur le port CONTAINER_GROUP_PORT( 81, 82, 83, 84, 85)
docker run -d --name catalogue-dsi-GROUP_NUMBER -p CONTAINER_GROUP_PORT:8080 catalogue-dsi:GROUP_NUMBER.0.0

Ex: docker run -d --name catalogue-dsi-2 -p 82:8080 catalogue-dsi:2.0.0

5-)  ## Vérifier le status des Container
--> docker ps

6-) Ouvrir votre navigateur, aller sur l'url http://10.100.46.105:85/

7-) ## Arrêter le Container Docker
--> docker stop CONTAINER_NAME

8-) ## Supprimer l'image 
-> docker rm IMAGE_NAME
