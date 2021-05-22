# Sticky Message 2

**Q: What is sticky message 2?**  
A: Sticky message 2 is an advanced version of the sticky message I added to the YAGPDB Community & Support server. It makes it easier for us volunteers to for example announce to users in several channels that the bot is having issues. It works the same as the [other sticky message](https://github.com/BlackWolfWoof/yagpdb-cc/blob/master/Automated/sticky%20message.gotmpl) I have coded but with this version you can:

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
![Preview](https://i.imgur.com/ohRubPw.gif)  