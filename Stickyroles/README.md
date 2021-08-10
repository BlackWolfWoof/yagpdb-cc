# Stickyroles

## What are stickyroles

Stickyroles are basically roles that are given back on re-join when you leave and join a server. So if you had your special "Cool furry" role and re-join you will now get it back without having to annoy the admins :).

---

## Limitations

There are a few limitations sadly. Making sticky roles isn't as easy as it sounds because when a user leaves you can't just check `{{.Member.Roles}}` in the leave message since the user has already left and therefor has no roles.  
What we can do is save the roles whenever the user reacts to a message or sends a message to make sure their current roles are saved in the database before they leave the server.  

---

## Usage / Setup

In order for the code to work as intended you have to add all of the custom commands in this folder to your server. If you do not have a lot of members joining and leaving then you do not need to add [Leave_Message](Leave_Message.yag) to your server.  
When you have finished adding everything you should give a friend or your second account some roles, write a message or react & re-join the server to make sure you have set up everything right.  
Make sure to configure the variables at the top of the code in the [Join_Message](Join_Message.yag).  
Here are a few examples of how it can look like:

### Whitelisting 3 roles
```go
{{$mode := true}}
{{/*true = WHITELIST; A $list of roles that WILL be given back on join*/}}
{{/*false = BLACKLIST; A $list of roles that WON'T be given back on join*/}}
{{$list := cslice 490096920300093442 279773568764477440 489653888258146315}}
{{/*A list of the roles. When using $mode false you can keep this empty if you want to give back all roles*/}}
```

### Blacklisting 2 roles

```go
{{$mode := false}}
{{/*true = WHITELIST; A $list of roles that WILL be given back on join*/}}
{{/*false = BLACKLIST; A $list of roles that WON'T be given back on join*/}}
{{$list := cslice 861997703759134770 861997702396772373}}
{{/*A list of the roles. When using $mode false you can keep this empty if you want to give back all roles*/}}
```

### Giving back all roles

```go
{{$mode := false}}
{{/*true = WHITELIST; A $list of roles that WILL be given back on join*/}}
{{/*false = BLACKLIST; A $list of roles that WON'T be given back on join*/}}
{{$list := cslice}}
{{/*A list of the roles. When using $mode false you can keep this empty if you want to give back all roles*/}}
```

---

## Filling the database

It can happen that you run out of database space for yagpdb.  
Thats why I included [Leave_Message](Leave_Message.yag) in here which sets the database entry to expire after N amout of time.  
The default is 1 year which should be ok for small or even big servers. If you run into issues pick a smaller duration tho.
```go
{{$expire := "1y"}}
{{/*The time after the stickyroles get forgotten. Example formats: 1y, 2mo3w, 200m, 1y2mo3d, 200d*/}}
{{/*NOTE: If your server has many members joining & leaving this will prevent it from filling up the database over tinme
If you dont know what you are doing include this code on your server.*/}}
```
