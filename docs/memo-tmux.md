# Tmux

## Obtenir de l'aide

Afficher la liste des raccourcis clavier:

    C-b ?

## Gérer les sessions

Créé une session:

    tmux new-session -s work

Attacher la session:

    tmux attach -t work

Detacher la session: 

    `C-b d`.

Naviguer dans les sessions:

    C-b (          session précédente
    C-b )          session suivante
    C-b L          la dernière session
    C-b s          choisir une session de la liste

Autre:

    C-b $          renomée la session courante

## Gérer les fenêtres

Créer une fenêtre:

    C-b c          créer une nouvelle fenêtre

Naviguer dans les fenêtres:

    C-b 1 ...      passer de la fenêtre 1, ..., 9, 0
    C-b 9
    C-b 0
    C-b p          fenêtre précédente
    C-b n          fenêtre suivante
    C-b l          revenir à la dernière fenêtre
    C-b w          choisir une fenêtre de la liste

Autre:

    C-b ,          renomé la fenêtre courante
    C-b &          fermer la fenêtre


## Gérer les fenêtres divisés

Créer un nouveau panneau en divisant le panneau courant:

    C-b "          diviser horizontalement
    C-b %          diviser verticalement

Naviguer entre les panneaux:

    C-b left       Aller au panneau à gauche
    C-b right      à droite
    C-b up         en haut
    C-b down       en bas

Other:

    C-b x          fermer le panneau courant
