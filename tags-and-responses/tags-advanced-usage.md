# Tags - Advanced usage

Tags are easy to use, but very powerful. With some ingenuity you can create your own, dynamic commands. To aid with this, dynamic "blocks" can be added. It is for instance entirely possible to create an 8ball command, a !hug command and many other things using just tags.

As of writing this, these blocks are:

**Random lists** `{random: a, b, c}`

Unlike random lists assigned to a variable through variable blocks, unique random lists randomly pick an element each time. This allows for some very nice commands, see the link at the bottom.

**Math blocks** `{math: 1 + 1 / (3 ** 9)}`

Supports basic math.

**React blocks** `{react: :regional_indicator_f: :cool_roblox_emoji:}` `{reactu: :regional_indicator_f: :cool_roblox_emoji:}`

This will react to the tag\(react\) or original message \(reactu\) with the emojis placed inside the brackets

**50/50 blocks** `{50:Will anyone see me?}`

Has a 50% chance of showing up

**Command blocks** `{cmd: temp stockholm}`

Do you think that `!info` really should be called `!whois`? with command blocks you can do just that

`!tag + whois {cmd: info {args}}`

**Actions** `{dm} {delete} {silence}`

`dm` Redirects output to the user who uses the command

`delete` deletes the message that triggered the tag

`silence` Silences the output of any command being used

**Formatted time blocks** {strf\(optional datetime\): _strftime_}

Returns the current time formatted according to python's strftime, see [http://strftime.org/](http://strftime.org/) for more information.

**Example:** `The current year is {strf:%Y} hehe`

**Advanced** `Your account was created at {strf({user(created_at)}: %x}`

**Redirection blocks** {redirect: \#channel}

Redirects the output of the tag to the specified channel, the tag creator needs to have send message permissions in the pointed channel

**Example:** `{user} says: {args} {redirect:#screaming-out-loud}`

**Requirement blocks** {require:\#channel, role}

takes roles and channels. 

**Example:** `{require:Cool kids} Word around the office is that {user} is kind of a big deal`

**Blacklist blocks** {blacklist:\#channel, role}

works like require but the other way. As soon as it sees an entity that it doesn't like, it will evaluate to false.

**Example:** `{blacklist: muted} Wow, you've been a bad boy`

**variable assignment** `{let(foo):This can be anything}`

In addition to these blocks, it also comes with a few default arguments. These are:

`{unix}` - Unix time, useful for math blocks

`{uses}` - The amount of times the tag has been used

`{args}` - The words after the tag invocation. `!foo bar baz` means {args}=bar baz

`{user}` - Nickname of the author

`{target}` - Like user, except if you mention someone, this variable works for the mentioned user

`{server}` - The name of the server

`{mention}` - Mentions the user of the tag

 Additionally, tagscript 2.0 has better support for various discord objects like members, channels and servers. We call these 'adapters' and let you access certain properties that previously would have been too specific to justify putting in To access a property, you put the property name in parens like {user\(id\)} Right now for tags there are four adapters: user, target, channel and server 

**user & target:** 

* **avatar**: The user's avatar
* **id**: The user's id 
* **mention**: a string to mention the user
* **created\_at**: yyyy-mm-dd HH.MM.SS 
* **joined\_at**: yyyy-mm-dd HH.MM.SS 
* **color**: hex code 
* **name**: their actual _username_ 
* **position**: their position in the role hierarchy

**server**

* **icon**: server icon link 
* **id**: server id 
* **owner**: name\#discrim format of the server owner 
* **random**: random member 
* **randomonline**: random member who is online 
* **randomoffline**: random member who is offline 
* **members**: number of members: 
* **bots**: number of bots 
* **humans**: number of humans 
* **roles**: number of roles 
* **channels**: number of channels 
* **created\_at**: when the server was created

**channel**

* **id**: the channel id 
* **topic**: the channel topic 
* **slowmode**: the current slowmode delay 
* **position**: the channel's position 
* **mention**: clickable link to the channel

