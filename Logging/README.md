# Logging

| 📢 Read the entire README.md as it contains important information about the setup and usage! |
| ---- |

## A warning, ban, kick, mute and timeout log

This is a `-warnings` command for ban, kick mute (and to replace the inbuilt warnings command).  
You no longer need to hunt in your modlog how often the user was banned kicked or muted and can just use one command to check.  

<img src="../../assets/Logging/logs.gif?raw=true" width="60%"/>

---

### Setup & Requirements

Create a new custom command in **Core** > **Custom commands** and add the [log_get](log_get.yag) code.  
Trigger type: `Regex`  
Trigger: `\A(?:\-|<@!?204255221017214977>)\s*((?:warn(s|ings)|mutes|kicks|bans)|del(?:warn(ings?|s?)|mutes?|kicks?|bans?))\s*`
| ❗ If your prefix is not `-` then make sure to replace the first `-` in the trigger with your prefix. |
| ---- |

<br>

To be able to switch between several pages of logs you have to add the [pagination](pagination.yag) custom command to your server too.  
Trigger type: Reaction

<br>


For the [ban](banlog_set.yag), [kick](kicklog_set.yag), [mute](mutelog_set.yag), [timeout](timeout_set.yag) and [warn](warnlog_set.yag) you can decide which ones you want to add to the server.  
The instructions on where to save them are saved at the top of the custom command.

---

### Additional info

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
"ban" "BanMembers"
"timeout" "ManageRoles"}}
{{/*You can replace ManageMessages, ManageRoles, KickMembers and BanMembers with any of the following permissions if you want.
You'll need these permissions to delete an entry or even view them, if $view is set to false.*/}}
{{/*Permissions available: Administrator, ManageServer, ReadMessages, SendMessages, SendTTSMessages, ManageMessages, EmbedLinks, AttachFiles, ReadMessageHistory, MentionEveryone, VoiceConnect, VoiceSpeak, VoiceMuteMembers, VoiceDeafenMembers, VoiceMoveMembers, VoiceUseVAD, ManageNicknames, ManageRoles, ManageWebhooks, ManageEmojis, CreateInstantInvite, KickMembers, BanMembers, ManageChannels, AddReactions, ViewAuditLogs*/}}
```

**Restrict viewing entries**  
```go
{{$view := true}}
{{/*By setting this to true, anyone can view warnings, mutes, timeouts, kicks and bans. If you set it to false only people with the permissions from $permcalc can view it.*/}}
```

---

### Usage

After adding all the code you can use `-mutes`, `-timeouts`, `-kicks`, `-bans` and `-warns` / `-warnings` to view your logs.  
To delete them you can use `-delmute`, `-deltimeout`, `-delkick`, `-delban` and `-delwarn` / `-delwarnings`.  

---

### Important

| ⚠️ Remember, by just replacing your current warn, mute, timeout, kick and ban dm code, it will no longer dm the user! |
| ---- |

With that I mean these messages here. Make sure you keep the highlighted code if you still want to dm the user as usual when they are getting warned, muted, kicked or banned.  

<img src="../../assets/Logging/dm.png?raw=true" width="60%"/>