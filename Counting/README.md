# Counting Code

## Main Counting Code

This part is needed for the main part of the code to work.  
Features that can be toggled:

#### Counting role

The counting role will be a role that gets given if the user counted. You can hoist it and move it to the top so people will see who just counted and then also want to count to be displayed at the top of the server.  
Enable this feature by setting `$countingrole` from `0` to a role id.

<img src="../../assets/Counting/counting_role.gif?raw=true" width="60%"/>

#### Anti status ad

This will block any users from getting the counting role if they are currently advertising a discord server in their status, because nobody wants to see ads everywhere they look.  
Enable this feature by setting `$antiad` to true.

#### Same user

You can toggle if the same user that last counted can count again. That means if `$sameuser` is set to true, the same user will be able to count multiple times in a row. If set to false another user will have to count again before you will be able to count.

#### Counting tracker

The counting tracker will track how often a user counted. You can use this together with the codes [topcount](topcount.yag), [counter](counter.yag) and [pagination](pagination.yag) which will have to be added in order to display the top people that counted and how often you counted.  

<p float="left">
	<img src="../../assets/Counting/topcount.png?raw=true" width="30%" />
	<img src="../../assets/Counting/count.png?raw=true" width="30%" />
</p>

### Usage (without tracker)

Add the [main counting command](main_counting_cc.yag) to your server and set it up as shown below. Then configure the variables to your liking.

### Setup & Requirements (without tracker)

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
\A|Regex|**[Download Link](main_counting_cc.yag)**|❌|Only run in the following channels (counting channel)

### Usage (with tracker & leaderboard)

Add the [main counting command](main_counting_cc.yag) to your server and set it up as shown below. Then configure the variables to your liking.
Then add the [topcount](topcount.yag), [setcount](setcount.yag), [counter](counter.yag) and the [pagination](pagination.yag).  
Make sure you set up everything as shown below.

### Setup & Requirements (with tracker & leaderboard)

Trigger|Trigger Type|Code|Dependencies|Custom Command Settings
---|---|---|---|---
\A|Regex|**[Download Link](main_counting_cc.yag)**|❌|Only run in the following channels (counting channel)
topcount|Command|**[Download Link](topcount.yag)**|[Main counting cc](main_counting_cc.yag)|❌
❌|Reaction (add & remove)|**[Download Link](pagination.yag)**|[topcount](topcount.yag)|❌
count|Command|**[Download Link](counter.yag)**|[Main counting cc](main_counting_cc.yag)|❌
setcount|Command|**[Download Link](setcount.yag)**|[Main counting cc](main_counting_cc.yag)|❌

### Important
If you have been using the old counting system from yagpdb before you can use the [converter](converter.yag) to switch to this updated system. While adding all custom commands and running the [converter](converter.yag) you shouldn't let any users count and lock the counting channel until the converter and you are done converting and adding all custom commands you want.

### Disclamer

If you do not like this code, there is also [another counting code](https://yagpdb-cc.github.io/fun/counting) on the official custom command website.  
I `Black Wolf#0001` didn't come up with this idea, nor do I own the full code. The following parts of the code were all made a while ago but I re-uploaded & edited them because the old counting custom command on the [YAGPDB Community & Support server](https://discord.gg/4udtcA5) was outdated ~~and messy~~ and people kept having issues with it on their servers when adding it.
