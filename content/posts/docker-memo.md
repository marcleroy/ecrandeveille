---
title: 'Docker mémo'
date: 
draft: true
tags: ['Non classé']
---

### Commandes

Informations diverses sur Docker :

```lang-bash
\$ docker info
\$ docker version
```

Lancer un container :

```lang-bash
\$ docker run
```

Arrêter un container :

```lang-bash
\$ docker stop
```

Démarrer un container arrêté :

```lang-bash
\$ docker start
```

Supprimer un container (après l’avoir stopper) :

```lang-bash
\$ docker rm
```

Liste des containers actifs :

```lang-bash
\$ docker ps
```

Liste des containers actifs et inactifs :

```lang-bash
\$ docker ps -a
```

Arrêter tous les containers :

```lang-bash
\$ docker stop $(docker  ps -a -q)
```

Démarrer tous les containers :

```lang-bash
\$ docker start $(docker ps -a -q)
```

Supprimer tous les containers (après les avoir stopper) :

```lang-bash
\$ docker rm $(docker  ps -a -q)
```

Liste des images :

```lang-bash
\$ docker images
```

Supprimer une image :

```lang-bash
\$ docker rmi
```

Exécuter un Dockerfile :

```lang-bash
\$ docker-compose -d -f dockerfile.yml
```

Entrer dans un container :

```lang-bash
\$ docker exec -it \[container\] bash
```
