# Systemd

## Obtenir le niveau de démarrage par défaut

    $ systemctl get-default 

## Changer le niveau de démarrage par défaut

    # systemctl set-default multi-user

## Démarrer au niveau de démarrage multi utilisateur (niveau 3)

    # systemctl isolate multi-user.target

## Démarrer au niveau de démarrage multi utilisateur avec interface graphique (niveau 5)

    # systemctl isolate graphical.target
