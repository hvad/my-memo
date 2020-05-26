# Docker

## Installer Docker

* OSX 

Télécharger le fichier .dmg et double cliquer sur le fichier puis copier le fichier dans le dossier Application.

* Linux Fedora/RHEL

Podman est l'outil de gestion de container depuis 2020. Et il fonctionne de la même façon que Docker.

## Comment utiliser Docker ?

### Récupérer une image depuis docker hub

Saisir la commande comme ci-dessous et remplacer <image_docker> par l'image voulu :

    # docker pull <image_docker>

Par exemple :

    # docker pull fedora

### Démarrer une image Docker

    # docker run <image_docker>
