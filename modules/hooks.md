---
description: >-
  Le module discord-architect/Hooks vous donne accès à des fragments du
  framework..
---

# Hooks

Le module discord-architect/Hooks vous donne accès à des fragments du framework tels que le client discord, l'instance des commandes, les événements, le middleware.. Pour l'utiliser, vous devrez installer le module au sein de votre projet :

{% tabs %}
{% tab title="NPM" %}
```text
npm install @discord-architect/hooks
```
{% endtab %}

{% tab title="YARN" %}
```
yarn add @discord-architect/hooks
```
{% endtab %}
{% endtabs %}

Vous pouvez utiliser les couleurs du module comme ci-dessous :

### UseClient

Si vous souhaitez récupérer l'instance de votre client discord et ainsi récupérer le nombre de membres sur l'ensemble des serveurs sur lesquels se trouvent votre bot.

```typescript
import { useClient } from '@discord-architect/hooks'

const client = useClient()
console.log(client)
```

### 

### UseCommands

Si vous souhaitez récupérer l'instance de votre client discord et ainsi récupérer le nombre de membres sur l'ensemble des serveurs sur lesquels se trouvent votre bot.

```typescript
import { UseCommands, useCommand } from '@discord-architect/hooks'

/**
 * Récupére l'entièreté des commandes
 * instanciées dans votre application.
 */
const commands = UseCommands()
console.log(commands) // Array<Map<tag, command>>

/**
 * Récupére une commande spécifique
 * instanciée dans votre application
 * par son tag
 */
const command = useCommand('tag')
console.log(command) // Map<tag, command>
```

