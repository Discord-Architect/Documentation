---
description: Créez vos propres commande en 10 secondes.
---

# Commandes

La conception d'un bot discord passe la quasi-totalité du temps pat le développement de commandes. Ces commandes ont pour but d'exécuter certaines actions par la modération ou la communauté.

Créer une commande avec le framework est très très simple.

Ouvrez un nouveau terminal dans votre projet et écrivez la commande suivante :

```bash
node arch make:command <nom de votre command>
```

Un fichier va être créé à la racine de votre projet avec la structure suivante :

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

