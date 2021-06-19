# Installer Pterodactyl avec les IP Failover OVH

C'est génial !
Cela fait bientôt plus d'1 an que j'essaie de faire marcher [Pterodactyl](https://pterodactyl.io) avec mes IP failover chez moi, et je restais bloqué à une bête erreur de Traffic.
Grâce à [@Aven](https://github.com/Aven678) et [@DrKnaw](https://github.com/DrKnaw) et leurs investigations, on a réussi à contourner ce blocage bête et à réussir à avoir une solution stable.

Ducoup aujourd'hui on se retrouve pour un petit tuto afin d'installer le panel Pterodactyl sur une VM (qui possède une IP failover si besoin) afin de pouvoir gérer facilement ses serveurs de jeu et héberger ses amis.

## 1 - Prérequis

Comme d'habitude, mon tuto se basera sur une distro particulière. Pour avoir des résultats similaires voire identiques, il serait préférable que vous **utilisiez Ubuntu 20.04** pour ce tutoriel. C'est très similaire avec debian mais bon, chacun son avis, mais ubuntu c'est mieux.

Connectez-vous à votre VPS en SSH, et on va le mettre à jour pour bien commencer :

```
apt update && apt full-upgrade -y
```

Ensuite on va appliquer notre petit "patch" réseau en modifiant notre fichier /etc/hosts

```
nano /etc/hosts
```

![Fichier Host Classique](./img/pterodactyl1.png)

Une fois ceci fait on devrais avoir une base solide.
Ce tutoriel va suivre la documentation officielle de pterodactyl, elle est suceptible d'être modifiée avec le temps et ce tuto peut ne plus très bien fonctionner. Cependant, j'essaierai de le mettre à jour afin qu'il fonctionne sur le long terme.

