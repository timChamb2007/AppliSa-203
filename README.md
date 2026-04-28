# Docker Sae_203

## Instructions pour lancer le site apache sur un docker

- Vérifiez si docker est installé :
```shell
docker --version
```

- Cloner le référentiel :
 ```shell
git clone git@github.com:timChamb2007/docker-sae203.git
```

- Construisez l'image décrite dans dockerfile avec docker build : 
```shell
docker build -t <choisir-un-nom-pour-l'image> .
```

- Lancer le serveur web :
```shell
docker run -d -p <PortChoisie>:80 <nom-de-l'image-choisie>
```

- Vérifier que le site est en cours d'exécution. Pour ce faire, ouvrez un navigateur et tapez ```localhost:<PortChoisie>```

- Vérifier que le conteneur associé est actif :
```shell
docker ps
```

- La sortie de ```docker ps``` doit être similaire à :
```shell
CONTAINER ID   IMAGE          COMMAND              CREATED          STATUS          PORTS                                   NAMES
<hachage>   <Votre-image>   "Apache2"   30 minutes ago   Up 30 minutes   0.0.0.0:<PortChoisie>->80/tcp, :::<PortChoisie>->80/tcp   <Votre-Conteneur>
```

- Si vous souhaitez arrêtez le conteneur vous pouvez le faire avec la commande suivante :
```shell
docker stop <hachage>
```

- De même si vous souhaitez le supprimez :
```shell
docker rm <hachage>
```

**NOTE :** Au lieu du code de hachage, on peut toujours taper le nom du conteneur. Dans le cas d'exemple nous n'avons pas choisie de nom nous vous laissons faire mais il est possible de le faire.