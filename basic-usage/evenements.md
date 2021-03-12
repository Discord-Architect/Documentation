---
description: 'Les évènements, la base de Discord.js'
---

# Evènements

Créer un évènement avec le framework est vraiment rapide.

Ouvrez un nouveau terminal dans votre projet et écrivez la commande suivante :

```bash
node arch make:event <nom de l'évènement>
```

Un fichier va être créé à la racine de votre projet avec la structure suivante :

```typescript
import { Event, BaseEvent } from '@discord-architect/core'

@Event('event')
export default class Tdets implements BaseEvent {
	public async run(...args: Array<any>): Promise<void> {
		// Please go to the documentation in order to know the parameters you can use
		// Your code here
	}
}
```

{% hint style="info" %}
Il est important de souligner que les arguments de l'évènement sélectionné sont disponibles sur la documentation [discord.js](https://discord.js.org) en y recherchant l'évènement utilisé.
{% endhint %}

Pour déclarer une classe comme étant un évènement, il vous faut utiliser le décorateur `@Event()` et lui passer l'un des paramètres suivants :

```typescript
interface ClientEvents {
	channelCreate: [Channel]
	channelDelete: [Channel | PartialDMChannel]
	channelPinsUpdate: [Channel | PartialDMChannel, Date]
	channelUpdate: [Channel, Channel]
	debug: [string]
	warn: [string]
	disconnect: [any, number]
	emojiCreate: [GuildEmoji]
	emojiDelete: [GuildEmoji]
	emojiUpdate: [GuildEmoji, GuildEmoji]
	error: [Error]
	guildBanAdd: [Guild, User]
	guildBanRemove: [Guild, User]
	guildCreate: [Guild]
	guildDelete: [Guild]
	guildUnavailable: [Guild]
	guildIntegrationsUpdate: [Guild]
	guildMemberAdd: [GuildMember]
	guildMemberAvailable: [GuildMember | PartialGuildMember]
	guildMemberRemove: [GuildMember | PartialGuildMember]
	guildMembersChunk: [Collection<Snowflake, GuildMember>, Guild, { count: number; index: number; nonce: string | undefined }]
	guildMemberSpeaking: [GuildMember | PartialGuildMember, Readonly<Speaking>]
	guildMemberUpdate: [GuildMember | PartialGuildMember, GuildMember]
	guildUpdate: [Guild, Guild]
	inviteCreate: [Invite]
	inviteDelete: [Invite]
	message: [Message]
	messageDelete: [Message | PartialMessage]
	messageReactionRemoveAll: [Message | PartialMessage]
	messageReactionRemoveEmoji: [MessageReaction]
	messageDeleteBulk: [Collection<Snowflake, Message | PartialMessage>]
	messageReactionAdd: [MessageReaction, User | PartialUser]
	messageReactionRemove: [MessageReaction, User | PartialUser]
	messageUpdate: [Message | PartialMessage, Message | PartialMessage]
	presenceUpdate: [Presence | undefined, Presence]
	rateLimit: [RateLimitData]
	ready: []
	invalidated: []
	roleCreate: [Role]
	roleDelete: [Role]
	roleUpdate: [Role, Role]
	typingStart: [Channel | PartialDMChannel, User | PartialUser]
	userUpdate: [User | PartialUser, User]
	voiceStateUpdate: [VoiceState, VoiceState]
	webhookUpdate: [TextChannel]
	shardDisconnect: [CloseEvent, number]
	shardError: [Error, number]
	shardReady: [number, Set<Snowflake> | undefined]
	shardReconnecting: [number]
	shardResume: [number, number]
}

```

