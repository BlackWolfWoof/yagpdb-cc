# Example code

## Introduction
If you are new to custom commands or don't know how how to do something you can take a look at these examples that will show you how to use a few functions.  
You can contact `Black Wolf#0001` on the [official support server for yagpdb](https://discord.gg/4udtcA5) and ask for examples to be added if you have difficulty with something.  
I'd highly recommend you to check out the [learning page](https://learn.yagpdb.xyz/) and the [docs](https://docs.yagpdb.xyz/reference/templates) which will also explain or show what and how you can use functions, variables and more.  


## Functions

### print

```go
{{sendMessage nil (print "Welcome to the server " .User.Mention ", and have a great stay!")}}
```

<img src="../../assets/Example_Code/print.png?raw=true" width="60%"/>


### cembed

```go
{{sendMessage nil (cembed
	"title" "Hello world"
	"description" (print .Server.Name " is a great server")
	"footer" (sdict
		"text" "This is a footer test"
		"icon_url" "https://yagpdb.xyz/static/img/logo_y_small.png")
	"thumbnail" (sdict
		"url" "https://github.com/BlackWolfWoof/yagpdb-cc/blob/assets/cat2.jpeg?raw=true")
	)}}
```
<img src="../../assets/Example_Code/cembed.png?raw=true" width="40%"/>


There is stuff you can and cannot use in your embeds here in the [discord docs](https://discord.com/developers/docs/resources/channel#embed-object-embed-structure) I have hilighted a bit for you.  

<img src="../../assets/Example_Code/discord_docs_embed.png?raw=true" width="60%"/>

### The pipe

You may have seen us using `|` before and if you are still confused then this simple example should help you understanding when and how to use it.  
I myself like to use it to make my code more compact or easier to read because for me it is more difficult reading the code because of all the `((()))`.  

<img src="../../assets/Example_Code/pipe.png?raw=true" width="60%"/>

Without | `{{mult 2 (mult 10 (fdiv 20 5))}}` = 80
With 	| `{{fdiv 20 5|mult 10|mult 2}}` = 80

Everything infront of the `|` will be added to the back of the code as you can see by the math example in the picture above.  
This way you can evade using many parenthesis.  