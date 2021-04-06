# discord-api-bot : make testing discord api easier

# commands

Display the information of discord user who run this command
```
!r  runner
```

Display the discord user structure of whoever runs this command
```
!r  cee.get_user(runner.id)
```

# Discord APIs

## Get the current channel infomation in JSON

```
!r cee.get_channel(runner.channel_id)
```

## Modify the current channel

```
!r cee.modify_channel(runner.channel_id, { name:"a-new-channel-name" })
```

## Delete the current channel

```
!r cee.delete_channel(runner.channel_id);
```

## Get Channel Messages

```
!r cee.get_channel_messages(runner.channel_id);
```

```
// One message
!r var msgs = cee.get_channel_messages(runner.channel_id);
msgs[0];
```

```
// Print out the autor of each message
!r ```js
  var msgs = cee.get_channel_messages(runner.channel_id);
  for (var i in msgs)
    console.log(msgs[i].author.username)```
 
```

## Get channel message
```
!r cee.get_channel_message(runner.channel_id, runner.message_id);
```

## Create a message
```
!r cee.create_message(runner.channel_id, { content: "Hello World!" });
```

## Create a reaction
```
!r ```js
var heart = transformer.url_encode("❤️");
cee.create_reaction(runner.channel_id, runner.message_id, heart);
```

```


## Get all users who reaact to an emoji
```
!r ```js
var play = transformer.url_encode("▶️");
cee.get_reactions(runner.channel_id, runner.message_id, play);
```

```

## Delete all reactions of a message
```
!r ```js
cee.delete_all_reactions(runner.channel_id, runner.message_id)
```

```

## Delete all reactions for an emoji
```
!r ```js
var play = transformer.url_encode("▶️");
cee.delete_all_reactions_for_emoji (runner.channel_id, runner.message_id, play);
```

```

## Edit a message
```

!r ```js
cee.edit_message(runner.channel_id, runner.message_id, { content: "!r console.log(1)" });```

```

## Delete a message
```

!r ```js
cee.delete_message(runner.channel_id, runner.message_id);```

```