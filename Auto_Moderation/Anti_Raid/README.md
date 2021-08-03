# Anti Raid

Whenever a lot of users join at the same time and maybe even start spamming all at once you know how difficult it can be to ban kick or mute all of those accounts in time.  
| ✅ This script has been tested on a big server with 60,000 members and has prooven itself doing it's job nearly perfect. |
| --- |

This script automatically turns on an automod v2 rule which will then moderate all incoming accounts.  

### How it works

Once it detects a raid, the custom command in the join message will enable an automod v2 rule, and for example ban all incoming members until the raid is over.  

| ⚠️ This script will detect how fast members join and thats how it activates. You may tweak the `$seconds` and the `$people` to fit your needs. |
| --- |

*The following screenshots show the code in action. In the final version you will not see that join and leave log. The on and off message can be toggled by setting `$debug` to true.*  

<p float="left">
	<img src="../../../assets/Auto_Moderation/Anti_Raid/antiraid_on.png?raw=true" width="30%" />
	<img src="../../../assets/Auto_Moderation/Anti_Raid/antiraid_off.png?raw=true" width="30%" />
	<img src="../../../assets/Auto_Moderation/Anti_Raid/antiraid_cp.png?raw=true" width="60%" />
</p>


### Setup & Requirements

| ❓ If this sounds too complicated to set up, please watch this video https://youtu.be/SZMi7FMOFh4 |
| --- |

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
❌|Join Message Server|**[Download Link](joinmessage.yag)**|❌|❌

- Create an automod v2 ruleset and copy the name of that ruleset into `$ruleset`.  
- Turn off the ruleset so it doesn't trigger right away.  
- Add a rule to the ruleset (name doesn't matter)
- Set as trigger `New Member` and as effect `Mute`, `Kick` or `Ban`
- Hit save
- Navigate to your join message (server) and paste in the [code](joinmessage.yag)
- Set up your variables and hit save

**Debug variable:**
```go
{{$debug := false}}{{$channel := .Channel.ID}}
{{/*If $debug is set to true it will output a 'Ruleset enabled' and 'Ruleset disabled' into the join leave log channel. By replacing .Channel.ID with another channel ID you can change where that debug message goes*/}}
```

**Ruleset variable**
```go
{{$ruleset := "placeholder"}}
{{/*Replace placeholder by the name of your automod v2 ruleset. Make sure they are the same or else it will not work!*/}}
```

**Seconds & people variable:**
```go
{{$seconds := 60}}{{$people := 5}}
{{/*This will activate the code if $people (example 5) join within $seconds (example 60)*/}}
```

**Action variable:**
```go
{{$effect := "kick"}}
{{/*You can decide bewteen "kick" "ban" and "mute". You should keep this the same effect as used in automod v2.*/}}
```

If you are not sure if you have set it up correctly or have any questions you can join [the support server](https://discord.gg/4udtcA5), provide a link to your dashboard / control panel, and ask `Black Wolf#0001` to take a look at the anti raid code.  

### Important

**You have to tweak the values to your serversize.  
Pleace decide that on your own, as I cannot guess how many people join how fast normally on your server.  
The default value of 5 people within 60 seconds might be good for small servers bot for big servers a lower seconds value is probably needed.  
Even for large servers I do not reccomend setting the `$people` higher than `5`. I'd only change the `$seconds` or lower the `$people` variable.**  
