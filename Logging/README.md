# Logging

| 📢 Read the entire README.md as it contains important information about the setup and usage! |
| ---- |

## A warning & ban & kick & mute log

This is a `-warnings` command for ban, kick mute (and to replace the inbuilt warnings command).  
You no longer need to hunt in your modlog how often the user was banned kicked or muted and can just use one command to check.  

<img src="../../assets/Logging/logs.gif?raw=true" width="60%"/>


### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
`\A(?:\-\|<@!?204255221017214977>)\s*((?:warn(s\|ings)\|mutes\|kicks\|bans)\|del(?:warn(ings?\|s?)\|mutes?\|kicks?\|bans?))\s*`|Regex|**[Download Link](log_get.yag)**|✅|❌
❌|Reaction add & remove|**[Download Link](pagination.yag)**|any of the below codes|❌
❌|Ban Message DM|**[Download Link](banlog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Kick Message DM|**[Download Link](kicklog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Mute Message DM|**[Download Link](mutelog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Warn Message DM|**[Download Link](warnlog_set.yag)**|**[log_get](log_get.yag)**|❌

The [log_get](log_get.yag) and [pagination](pagination.yag) always has to be on your server.  
For the [ban](banlog_set.yag), [kick](kicklog_set.yag), [mute](mutelog_set.yag) and [warn](warnlog_set.yag) you can decide which ones you want to add to the server.  

**I already have the paginator code on my server!**  
Thats great. You can replace the old code you used for the snippet system or counting system with this one as it handles all of them without you having to add several reaction custom commands.

**Toggling warning replacement**  
```go
{{$warnings := true}}
{{/*If this is set to false the code will ignore -warnings and -warns so you can still use the inbuilt one*/}}
```

**Permission check**  
```go
{{$permcalc := sdict
"warn" "ManageMessages"
"mute" "ManageRoles"
"kick" "KickMembers"
"ban" "BanMembers"}}
{{/*You can replace ManageMessages, ManageRoles, KickMembers and BanMembers with any of the following permissions if you want.
You'll need these permissions to delete an entry or even view them, if $view is set to false.*/}}
{{/*Permissions available: Administrator, ManageServer, ReadMessages, SendMessages, SendTTSMessages, ManageMessages, EmbedLinks, AttachFiles, ReadMessageHistory, MentionEveryone, VoiceConnect, VoiceSpeak, VoiceMuteMembers, VoiceDeafenMembers, VoiceMoveMembers, VoiceUseVAD, ManageNicknames, ManageRoles, ManageWebhooks, ManageEmojis, CreateInstantInvite, KickMembers, BanMembers, ManageChannels, AddReactions, ViewAuditLogs*/}}
```

**Restrict viewing entries**  
```go
{{$view := true}}
{{/*By setting this to true, anyone can view warnings, mutes, kicks and bans. If you set it to false only people with the permissions from $permcalc can view it.*/}}
```

### Usage

After adding all the code you can use `-mutes`, `-kicks`, `-bans` and `-warns` / `-warnings` to view your logs.  
To delete them you can use `-delmute`, `-delkick`, `-delban` and `-delwarn` / `-delwarnings`.  

### Important

| ❗ If your prefix is not `-` make sure to replace the `-` in `\A(?:\-\|<@!?204255221017214977>)\s*(?:warn(s\|ings)\|mutes\|kicks\|bans)\s*`|
| ---- |

That means if your prefix is `!`, use `\A(?:\!|<@...`.  
Make sure you save the [main command](log_get.yag) as custom command and add the others you want to have enabled to the right section on your control panel.  
For that you can follow the instructions in each of the codes at the top.  
An example, this is how [the mute one](mutelog_set.yag) looks at the top:  
```go
{{/*
	Trigger Type: Mute DM

	Save this code in 'Tools & Utilities > Moderation > Mute > Mute DM'

	Copyright (c): Black Wolf, 2021
	License: MIT
	Repository: https://github.com/BlackWolfWoof/yagpdb-cc/
*/}}
```
The `Save this code in 'Tools & Utilities > Moderation > Mute > Mute DM'` are the instructions on where to add it to your server.

| ⚠️ Remember, by just replacing your current warn, mute, kick and ban dm code, it will no longer dm the user! |
| ---- |

With that I mean these messages here. Make sure you keep the hilighted code if you still want to dm the user as usual when they are getting warned, muted, kicked or banned.  

<img src="../../assets/Logging/dm.png?raw=true" width="60%"/>