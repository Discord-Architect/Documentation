# Prerequisites

Dans cet exemple, nous allons voir comment créer un pare-feu sur le nombre de paramètres requis lors de l'exécution d'une commande.

{% code title="App/Module/FooPrerequisite.ts" %}
```typescript
import { BasePrerequisite, Prerequisite, PrerequisiteContext } from '@discord-architect/core'

@Prerequisite({ name: '(?<count>\d+)-args' })
export default class T implements BasePrerequisite {
 public async isValid(context: PrerequisiteContext): Promise<boolean> {
 
  // Get persed number from REGEX
  const count = +context.get('count')!
  
  if (context.args.length < count) {
   await message.reply(`You should define ${count} arguments to execute this command.`)
   return false
  }
  return true
 }
}
```
{% endcode %}

{% hint style="danger" %}
Votre `prerequisite`doit impérativement retourner un type `boolean`
{% endhint %}

{% code title="App/Module/FooCommand.ts" %}
```typescript
import { BaseCommand, Command } from '@discord-architect/core'
import { Message } from 'discord.js'

@Command({ label: 'Foo command', description: 'Foo command description', require: ['1-args'], tag: 'foo' })
export default class Foo implements BaseCommand {
	public async run(message: Message, args: Array<string>): Promise<void> {
		// Your code here
	}
}

```
{% endcode %}

{% hint style="info" %}
Dans la déclaration de votre prerequisite au sein de votre commande \(pour cet exemple\), le chiffre 1 correspond à la variable `count` de `FooPrerequisite`.
{% endhint %}

