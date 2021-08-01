# Sticky Message v2

**Q: What is sticky message 2?**  
A: Sticky message 2 is an advanced version of the sticky message I added to the YAGPDB Community & Support server. It makes it easier for us volunteers to for example announce to users in several channels that the bot is having issues. It works the same as the [other sticky message](../v1/sticky_message.yag) I have coded but with this version you can:

### Flags you can use

With the flag `-d` you can overwrite the default cooldown of the sticky message.  
Example: `-sm Hello -d 5m`.  
With the flag `-img` you can attach images to the embed.   Example: `-sm Hello world -img https://github.com/BlackWolfWoof/yagpdb-cc/blob/assets/cat2.jpeg?raw=true`


### You can change the permission who can enable and disable the message  

```go
{{$perms := "ManageMessages"}}
{{/*The bot will check if the user has this permission.
Permissions available: Administrator, ManageServer, ReadMessages, SendMessages, SendTTSMessages, ManageMessages, EmbedLinks, AttachFiles, ReadMessageHistory, MentionEveryone, VoiceConnect, VoiceSpeak, VoiceMuteMembers, VoiceDeafenMembers, VoiceMoveMembers, VoiceUseVAD, ManageNicknames, ManageRoles, ManageWebhooks, ManageEmojis, CreateInstantInvite, KickMembers, BanMembers, ManageChannels, AddReactions, ViewAuditLogs*/}}
```

### You can enable and disable an inbuilt channel whitelist  

```go
{{$whitelist := false}}
{{/*This enables the whitelist of channels where it should run*/}}
{{$channels := cslice 166207328570441728 384011387132706816}}
{{/*Replace these channel id's with your channels if you have enabled the whitelist*/}}
```

### You can change the cooldown how often the sticky message should post  

```go
{{$cooldown := "60s"}}{{/*FORMAT EXAMPLE: "10s" "20m10s" "1mo10d" "3w2h"*/}}
{{/*The cooldown how long the sticky message shouldn't be sent in the same channel*/}}
```

Here is an example with the default values:
![Preview](https://i.imgur.com/ohRubPw.gif "Preview of the command")  
