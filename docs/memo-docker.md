# Docker

## Installer Docker

### OSx 

Télécharger le fichier .dmg depuis le site officiel et double cliquer sur le fichier puis copier le fichier dans le dossier Application.

### Linux Fedora/RHEL

Podman est l'outil de gestion de container pour Fedora/RHEL8 et supérieur qui remplace Docker.

## Comment utiliser Docker ?

### Récupérer une image depuis docker hub

Saisir la commande comme ci-dessous et remplacer <image_docker> par l'image voulu :

    # docker pull <image_docker>

Par exemple :

    # docker pull fedora

### Démarrer une image Docker

    # docker run <image_docker>

Démarrer un conteneur docker :
docker start nom_conteneur

### Entrer dans le conteneur

    # docker exec -t -i nom_conteneur /bin/bash

Ajouter un répertoire d'échange :
docker run -i -v /tmp/:/tmp -t docker_image /bin/bash

Démarrer container Fedora pour la construction de RPMs :
docker run --rm --privileged=true -v ~/.ssh/id_rsa:/home/build/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/home/build/.ssh/id_rsa.pub -it fedora-packaging /bin/bash

