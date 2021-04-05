---
description: Apprenez à installer le framework
---

# Démarrage

Installer un framework pour l'utiliser n'est pas toujours évident de par la configuration que le développeur doit y apporter.

Certains frameworks ou librairies tel que React utilisent`yarn create react-app <projet>` . Malheureusement il n'y a actuellement aucun équivalent pour créer automatiquement le projet..  \(mais on y pense ! 😶\)

Entrons dans le vif du sujet. Afin de pouvoir développer avec le framework, vous devez avoir installé [NodeJS](https://nodejs.org/en) \(v.14+\) sur votre environnement de développement.

Ensuite, installez globalement le CLI Architect du bot.

{% tabs %}
{% tab title="NPM" %}
```bash
npm install -g @discord-architect/arch
```
{% endtab %}

{% tab title="YARN" %}
```
yarn global add @discord-architect/arch
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Il est possible que l'utilisation de `YARN` afin d'ajouter le CLI de manière global ne fonctionne pas correctement, dans ce cas, veuillez utiliser `NPM`
{% endhint %}

Le module `@discord-architect/arch` est un CLI qui de la même manière qu'Artisan pour Laravel, vous permettra d'interagir rapidement avec les fonctionnalités du bot.

Vous pouvez maintenant initialiser un projet très facilement grâce à la commande suivante :

```bash
architect create-project
```

Répondez aux questions et un projet vierge sera initialisé en fonction des éléments que vous aurez définis ces dernières.

Un fichier `.env` sera créé, ce fichier doit posséder au minimum les donnés suivantes :

```text
CLIENT_PREFIX=""
SECRET_TOKEN=""
```

{% hint style="info" %}
La clé CLIENT\_PREFIX représente le préfix que devra avoir chacun des messages afin d'être reconnu comme étant une commande.

La clé SECRET\_TOKEN correspond au token de votre bot. **Il ne doit jamais être divulgué** ou envoyé sur une plateforme de versionning tel que github. Un article est disponible [ici](https://github.com/reactiflux/discord-irc/wiki/Creating-a-discord-bot-&-getting-a-token) afin de savoir comment récupérer le token de son bot.
{% endhint %}

Il ne vous reste plus qu'à installer les dépendances avec les commandes suivantes

{% tabs %}
{% tab title="NPM" %}
```text
npm install
```
{% endtab %}

{% tab title="YARN" %}
```
yarn install
```
{% endtab %}
{% endtabs %}

Afin de lancer le bot, il vous faut exécuter 2 scripts parallèlement.

Le premier permet la compilation typescript vers javascript.

{% tabs %}
{% tab title="NPM" %}
```text
npm run dev
```
{% endtab %}

{% tab title="YARN" %}
```
Yarn dev
```
{% endtab %}
{% endtabs %}

La deuxième exécutera simplement l'application du bot.

{% tabs %}
{% tab title="NPM" %}
```text
npm run start
```
{% endtab %}

{% tab title="YARN" %}
```
yarn start
```
{% endtab %}
{% endtabs %}

