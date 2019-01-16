# Tags - Advanced usage

Tags are easy to use, but very powerful. With some ingenuity you can create your own, dynamic commands. To aid with this, dynamic "blocks" can be added. It is for instance entirely possible to create an 8ball command, a !hug command and many other things using just tags.

As of writing this, these blocks are:

**Random lists** `{random: a, b, c}`

Unlike random lists assigned to a variable through variable blocks, unique random lists randomly pick an element each time. This allows for some very nice commands, see the link at the bottom.

Seeded Random `{random(seed): a,b,c}` 
The same seed will yield the same result every time. Can be anything.

Weighted Random `{random:<weight>|a,<weight>|b,<weight>|c}`
<weight> works as if it was a shortcut for writing the same option many times. 
`{random:4|a,2|b}` is the same as `{random:a,a,a,a,b,b}`
 
**Random range** `{range:1-200}` 

Picks a random number between 1 and 200 (inclusive). Can be seeded just as `{random}`

**50/50 blocks** `{50:Will anyone see me?}`

Has a 50% chance of showing up

**Math blocks** `{math: 1 + 1 / (3 ** 9)}`

Supports basic math:

`a+b` addition

`a-b` subtraction

`a*b` multiplication

`a/b` division

`a%b` modulo

`abs(a)` absolute value

`a^b` exponent

`round(a)` ignores numbers past the decimal point


**React blocks** `{react: :regional_indicator_f: :cool_roblox_emoji:}` `{reactu: :regional_indicator_f: :cool_roblox_emoji:}`

This will react to the tag \(react\) or original message \(reactu\) with the emojis placed inside the brackets


**Command blocks** `{cmd: temp stockholm}`

Do you think that `!info` really should be called `!whois`? with command blocks you can do just that

`!tag + whois {cmd: info {args}}`

**Actions** `{dm} {delete} {silence}`

`dm` Redirects output to the user who uses the command

`delete` deletes the message that triggered the tag

`silence` Silences the output of any command being used

**Formatted time blocks** {strf\(optional datetime\): _strftime_}

Returns the current time formatted according to python's strftime, see [http://strftime.org/](http://strftime.org/) for more information.

**Examples:** `The current year is {strf:%Y} hehe`

`Your account was created at {strf({user(created_at)}: %x}`

**Redirection blocks** {redirect: \#channel}

Redirects the output of the tag to the specified channel, the tag creator needs to have send message permissions in the pointed channel

**Example:** `{user} says: {args} {redirect:#screaming-out-loud}`

**Requirement blocks** {require:\#channel, role}

takes roles and channels. 

**Example:** `{require:Cool kids} Word around the office is that {user} is kind of a big deal`

**Blacklist blocks** {blacklist:\#channel, role}

works like require but the other way. As soon as it sees an entity that it doesn't like, it will evaluate to false.

**Example:** `{blacklist: muted} Wow, you've been a bad boy`

**Variable assignment** `{let(foo):This can be anything}`

You can then use the value in foo with brackets: `{foo}`

**If/Else** `{if(condition):Truthly|(optional) falsy}`

Currently only supports basic operations with `==`, `!=`, `<`, `>`, `<=`, `>=`. 
Limitations are that you can't use `{redirect}`, `{require}`, or `{let(variable):Assignment}`inside If statements, because those blocks will **always** evaluate, regardless of where they are. 

**Example:** `{if({user(id)}=={target(id)}):You just mentioned yourself or didn't mention anyone.|{user(name)} says {target(name)} is a wuss!}`

**any, all, break** `{any(condition1|condition2|condition3):Will evaluate to true if any of the conditions is true}`

`{all(condition1|condition2|condition3):Will evaluate to true if all of the conditions are true}`

`{break(condition):Will return ONLY what's inside this bracket}`

In addition to these blocks, tagscript also comes with a few default arguments. These are:

`{unix}` - Unix time, useful for math blocks

`{uses}` - The amount of times the tag has been used

`{args}` - The words after the tag invocation. `!foo bar baz` means {args}=bar baz

`{user}` - Nickname of the author

`{target}` - Like user, except if you mention someone, this variable works for the mentioned user

`{server}` - The name of the server

`{mention}` - Mentions the user of the tag

 Additionally, tagscript 2.0 has better support for various discord objects like members, channels and servers. We call these 'adapters' and let you access certain properties that previously would have been too specific to justify putting in. To access a property, you put the property name in parens like {user\(id\)} Right now for tags there are four adapters: user, target, channel and server. 

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

