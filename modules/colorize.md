---
description: >-
  Utilisez une magnifique  palette de couleur afin de sublimer les embeds de
  votre serveur discord.
---

# Colorize

Le module @discord-architect/Colorize vous offre une palette prête à l'emploi pour vos embeds. Pour l'utiliser, vous devrez installer le module au sein de votre projet :

{% tabs %}
{% tab title="NPM" %}
```text
npm install @discord-architect/colorize
```
{% endtab %}

{% tab title="YARN" %}
```
yarn add @discord-architect/colorize
```
{% endtab %}
{% endtabs %}

La palette de couleur est issue de celle de [Tailwind](https://tailwindcss.com/docs/customizing-colors), il est important de noter que certaines couleurs de la palette de tailwind color ne sont pas disponibles.

Vous pouvez utiliser les couleurs du module comme-ci :

```typescript
import { Special } from '@discord-architect/colorize' // 👈 Choisissez vos couleurs


const embed = new MessageEmbed({
    title: 'Hello world',
    color: Special.INVISIBLE
})

await message.channel.send(embed)

```

