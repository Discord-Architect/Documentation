---
description: Apprenez à installer le framework
---

# Démarrage

Installer un framework pour l'utiliser n'est pas toujours évident de par la configuration que le développeur doit y apporter.

Certains frameworks ou librairies tel que React utilisent`yarn create react-app <projet>` . Malheureusement il n'y a actuellement aucun équivalent pour créer automatiquement le projet..  \(mais on y pense ! 😶\)

Entrons dans le vif du sujet. Afin de pouvoir développer avec le framework, vous devez avoir installé [NodeJS](https://nodejs.org/en) sur votre environnement de développement.

Ensuite, vous devrez cloner le projet initial vierge qui se trouve [ici](https://github.com/Discord-Architect/Architect).

```text
git clone git@github.com:Discord-Architect/Architect.git <nom de votre projet>
```

Maintenant que vous avez installé la structure de base du projet, vous devriez voir une structure semblable à celle-ci :

![Structure du framework](.gitbook/assets/image.png)

Une fois fait, dupliquez le fichier `.env.example` et renommez-le `.env` 

Ce fichier doit posséder au minimum les donnés suivantes :

```text
CLIENT_PREFIX=""
SECRET_TOKEN=""
```

{% hint style="info" %}
La clé CLIENT\_PREFIX représente le préfix que devra avoir chacun des messages afin d'être reconnu comme étant une commande.

La clé SECRET\_TOKEN correspond au token de votre bot. **Il ne doit jamais être divulgué** ou envoyé sur une plateforme de versionning tel que github. Un article est disponible [ici](https://github.com/reactiflux/discord-irc/wiki/Creating-a-discord-bot-&-getting-a-token) afin de savoir comment récupérer le token de son bot.
{% endhint %}

