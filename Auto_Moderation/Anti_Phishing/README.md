# Anti Phishing

# READ THIS FIRST!! (Updated 12.10.2021)
## A user with the name [Benricheson101](https://github.com/Benricheson101/) made an anti phishing bot which uses an 24/7 up to date api, [that you can invite via this link](https://discord.com/oauth2/authorize?client_id=892420397570592768&scope=bot%20applications.commands&permissions=268446726).  
## The project is open source and can be viewed [here](https://github.com/Benricheson101/anti-phishing-bot). 
## Use slash commands to set up the bot  
| ❓ Too lazy to read? Watch this tutorial that will show you how to set it up! https://youtu.be/cVzNCs1FtXM |
| --- |

**If you still want to do it via YAGPDB tho then you can do that too. I will slow down updating the phishing lists here from now on.**  
With this code you will get notified about a phishing scam link or they will be deleted. This can be used against those annoying Steam & Discord phishing links on all servers.  
If you find a link that wasn't added yet and wasn't detected you can always message me on [my Discord server](https://discord.gg/GRns3fg) to add them to the code.

### Usage

Add both custom commands to your server, configure the variables at the top of the code, run the `setup` command, delete it again and then you are good to go.

### Setup & Requirements

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
\A|Regex|**[Download Link](anti_phishing.yag)**|setup 1 - 8|❌

**Add all files with the name `phishing_list` as command to your server and run it.**

Make sure to run at all setup / phishing_list codes at least once to import them into the database.  


### Important

Remember to configure your variables in the code. Here is what each variable does:

**The bot will kick a user when sending a blacklisted link:**
```go
{{$action := "kick"}}
{{/*Select which action you want to take: "mute", "kick", "ban", false (disabled)*/}}
{{/*Make sure you have the module that is seleted enabled and set up on the yagpdb control panel / website*/}}
```

**The users will be notified about how to report the above message to discord:**
```go
{{$message := true}}
{{/*Enables the how to report message. Cannot be used if $delete is on true*/}}
```

**The phishing link will be deleted (CAN NO LONGER BE REPORTED TO DISCORD)**
```go
{{$delete := true}}
{{/*!!!!WARNING: WHEN TURNING THIS ON THE MESSAGE CAN NO LONGER BE REPORTED TO THE 'Trust & Safety-Team' FROM DISCORD!!!!*/}}
{{/*If you set this to true it will delete the message from the chat so nobody can fall for the scam / pishing link*/}}
```

**A moderator or admin role will be pinged so they can act:**
```go
{{$modrole := 607846078863376394}}
{{/*Input a staff role id in there which will be used to notify the staff about the link. This should be enabled if $delete is set to false.*/}}
```

| ❓ Still need help with the setup or have questions? Join the [official yagpdb support & community server](https://discord.gg/4udtcA5) |
| --- |
