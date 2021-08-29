# Templates & code snippets for your code

## Bypass limit example

This is an example code that shows what the [bypass limit](bypass_limit.yag) code can do and how it can help you bypass some restrictions like only being able to use execAdmin or exec 5 times per custom command.

<img src="../../assets/Templates/bypass_limit_example.gif?raw=true" width="30%"/>

### Usage

This can be implemented into your own custom command so there isn't really much I can write here. This example shows how it can end up looking.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
Test|Command|**[Download Link](bypass_limit_example.yag)**|❌|❌

### Important

Remember you can only use 10 execCC per channel per minute.  
execAdmin also has limits like 5 times per custom command so make sure you do not go above that.

---

## Bypass limit

This is the basic idea behind bypassing some of the custom command limits by looping it via `execCC` with a delay.  
In the code I will display all database entries with the key **test**. The limit for dbTopEntries would be 100 entries at once


### Usage

The [example code](#bypass-limit-example) above explains what this does.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
*Any trigger*|*Any type*|**[Download Link](bypass_limit.yag)**|❌|❌

### Important

You can only call up to 100 entries at a time with dbTopEntries so don't go over that limit. What you can do to make it faster is use up to 2 (for none premium servers) dbTopEntries per custom command.

---

## Guild Icon

This will give you the link to your guild icon. It supports animated and non-animated images.  
Here an example of how it could be used.  
<img src="../../assets/Templates/guild_icon.png?raw=true" width="30%"/>

### Usage

The variable `$icon` will give you the full guild icon url. You can use `{{$icon}}` to output it into the chat and see if it works.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
*Any Trigger*|*Any type*|**[Download Link](guild_icon.yag)**|❌|❌

---

## Interval Time

This code lets you run your custom command at the time you want

### Usage

Configure `$time` and `$timezone` as explained in the comment in the code and paste the code or text you want to send & run at the `{{/*YOUR CODE GOES HERE*/}}` section.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
❌|10m Interval|**[Donload Link](interval_time.yag)**|❌|❌

### Important

Remember to configure your variables in the code or and paste whatever you want the bot to run / say to `{{/*YOUR CODE GOES HERE*/}}`.

---

## Permission Check

This code can be used to check if a user has the right permissions to execute the custom command. Here a little preview of how it can look with my database custom commands

#### v1  

Checks if a user has the permission `$perms` and if they don't send an error message.  

#### v2  

Use this if you have multiple permissions you want to check. $perms is a slice of all permissions the user has.  

#### different channel  

Use this if you want to see if a user has the permission `$perms` in the channel with the ID `$channelID`.


<img src="../../assets/Templates/permission_check.png?raw=true" width="30%"/>


### Usage

Paste the part of the code you want to use (either v1, v2 or different channel) into your custom command, set up the variables at the top of it and paste the code you want to run after the first if. You can add an else and do an output saying "you don't have enough permissions..." as shown in the image below for example or just use no else.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
*An trigger*|*Any type*|**[Download Link](permission_check.yag)**|❌|❌

### Important

Make sure the permission you want to check for is one of the following:
```
Administrator, ManageServer, ReadMessages, SendMessages, SendTTSMessages, ManageMessages, EmbedLinks, AttachFiles, ReadMessageHistory, MentionEveryone, UseExternalEmojis, VoiceConnect, VoiceSpeak, VoiceMuteMembers, VoiceDeafenMembers, VoiceMoveMembers, VoiceUseVAD, ChangeNickname, ManageNicknames, ManageRoles, ManageWebhooks, ManageEmojis, CreateInstantInvite, KickMembers, BanMembers, ManageChannels, AddReactions, ViewAuditLogs
```

---

## Role Color

This will get the top color that a member has on your server. That is also the color that their name will appear in chat. Can for example be used to auto color embeds if a user sends a message.


<img src="../../assets/Templates/rolecolor.png?raw=true" width="30%"/>


### Usage

`$color` will be the output for the decimal color code you'll get. You can delete the line with the sendMessage in it at the end of the code which is just there to test if it works.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
*Any trigger*|*Any type*|**[Download Link](rolecolor.yag)**|❌|❌
