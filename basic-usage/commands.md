---
description: Créez vos propres commande en 10 secondes.
---

# Commandes

La conception d'un bot discord passe la quasi-totalité du temps pat le développement de commandes. Ces commandes ont pour but d'exécuter certaines actions par la modération ou la communauté.

Créer une commande avec le framework est très très simple.

Ouvrez un nouveau terminal dans votre projet et écrivez la commande suivante :

```bash
architect make:file
```

Choisissez de créer une `commande` puis répondez aux questions qui vous seront posés. Il est important de noter que lorsque vous définirez le nom du fichier, vous pouvez "placer" celui-ci dans des dossiers en spécifiant un path directory en plus du nom du fichier comme sur l'exemple suivant :

```text
Dossier/Sous-dossier/Fichier
```

Un fichier va être créé à l'emplacement spécifié sinon, à la racine de votre projet tout en ayant la structure suivante :

```typescript
import { BaseCommand, Command } from '@discord-architect/core'
import { Message } from 'discord.js'

@Command({ label: 'TestCommand command', description: 'TestCommand command description', tag: 'testcommand' })
export default class TestCommand implements BaseCommand {
	public async run(message: Message, args: Array<string>): Promise<void> {
		// Your code here
	}
}

```

{% hint style="info" %}
Les `prerequisites` définis dans la clé `require` sont exécutés dans l'ordre d'écriture.
{% endhint %}

Pour déclarer une classe comme étant une commande, il vous faut utiliser le décorateur `@Command()` et lui passer les arguments suivants :

```typescript
interface CommandOptions {
    label: string
    description: string
    tag: string
    usage?: Array<string>
    alias?: Array<string>
    roles?: Array<string>
    permissions?: Array<PermissionResolvable>
    require?: Array<string>
}
```

