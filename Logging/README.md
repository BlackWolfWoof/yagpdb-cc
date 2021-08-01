# Logging


## A warning & ban & kick & mute log

This is a `-warnings` command for ban, kick mute (and to replace the inbuilt warnings command).  
You no longer need to hunt in your modlog how often the user was banned kicked or muted and can just use one command to check.  

<img src="../../assets/Logging/logs.gif?raw=true" width="60%"/>


### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
`\A(?:\-\|<@!?204255221017214977>)\s*(?:warn(s\|ings)\|mutes\|kicks\|bans)\s*`|Regex|**[Download Link](log_get.yag)**|✅|❌
❌|Reaction add & remove|**[Download Link](banlog_set.yag)**|any of the below codes|❌
❌|Ban Message DM|**[Download Link](banlog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Kick Message DM|**[Download Link](kicklog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Mute Message DM|**[Download Link](mutelog_set.yag)**|**[log_get](log_get.yag)**|❌
❌|Warn Message DM|**[Download Link](warnlog_set.yag)**|**[log_get](log_get.yag)**|❌

The [log_get](log_get.yag) always has to be on your server.  
For the [ban](banlog_set.yag), [kick](kicklog_set.yag), [mute](mutelog_set.yag) and [warn](warnlog_set.yag) you can decide which ones you want to add to the server.  


**I want to use the inbuilt warning command and not the custom one!**  
No worries, you can turn that off in the [log_get](log_get.yag) settings.  
There you can set `$warnings` from `true` to `false` to disable the custom warning log from displaying when you run -warnings or -warns.  

**I already have the paginator code on my server!**  
Thats great. You can replace the old code you used for the snippet system or counting system with this one as it handles all of them without you having to add several reaction custom commands.


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
