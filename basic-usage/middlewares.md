---
description: >-
  Les middlewares sont à utiliser sans modération afin de greffer certains
  comportements lors du cycle de vie de votre application.
---

# Middlewares

Les middlewares vous permettent d'interagir à certains moments de l'application. Par exemple, le middleware `app:message:received` vous permet d'effectue une action lorsqu'un message qui n'est pas une commande est reçus.

Utiliser un middleware avec le framework est très très simple.

Ouvrez un nouveau terminal dans votre projet et écrivez la commande suivante :

```bash
architect make:file
```

Choisissez de créer un `middleware` puis répondez aux questions qui vous seront posés. Il est important de noter que lorsque vous définirez le nom du fichier, vous pouvez "placer" celui-ci dans des dossiers en spécifiant un path directory en plus du nom du fichier comme sur l'exemple suivant :

```text
Dossier/Sous-dossier/Fichier
```

Un fichier va être créé à l'emplacement spécifié sinon, à la racine de votre projet tout en ayant la structure suivante :

```typescript
import { Middleware, BaseMiddleware } from '@discord-architect/core'

@Middleware('middleware selectionné')
export default class Foo implements BaseMiddleware {
	public async run(args: Array<any>): Promise<void> {
		// Please go to the documentation in order to know the parameters you can use
		// Your code here
	}
}
```

{% hint style="info" %}
Il est important de souligner que les arguments de l'évènement sélectionné sont disponibles sur la documentation [discord.js](https://discord.js.org) en y recherchant l'évènement utilisé
{% endhint %}

