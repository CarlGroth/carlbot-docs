# Tags - Advanced usage

Tags are easy to use, but very powerful. With some ingenuity you can create your own, dynamic commands. To aid with this, dynamic "blocks" can be added. It is for instance entirely possible to create an 8ball command, a !hug command and many other things using just tags.

As of writing this, these blocks are:

**Random lists** `#{comma, separated,#{nested args}}`

**Unique random list variables** `#variablename{comma, separated, values}`

Unlike random lists assigned to a variable through variable blocks, unique random lists randomly pick an element each time. This allows for some very nice commands, see the link at the bottom.

**Math blocks** `m{1 + 1 / (3 ^ 9)}`

Supports relatively advanced math.

`+ - * / ^ % sin cos tan exp abs trunc round sgn log ln log2`

**React blocks** `react{:regional_indicator_f:}` `reactu{:regional_indicator_x:, :regional_indicator_d:}`

This will react to the tag\(react\) or original message \(reactu\) with the emojis placed inside the brackets

Unsure what this could be used for? `!tag create doubt react{:regional_indicator_x:} https://i.imgur.com/EacBuLR.png`

**50/50 blocks** `?{Will anyone see me?}`

**Command blocks** `c{temp stockholm}`

Do you think that `!info` really should be called `!whois`? with command blocks you can do just that

`!tag + whois c{info $args}`

Maybe you think speak defaulting to 5 uses is an idiotic design choice, simply do

`!tag + betterspeak c{speak 20 $args}`

Important to note is that command tags are effectively not tags in the sense that whatever else you put in a tag won't be sent

**Action blocks** a{_action_} where _action_ is `pm` or `delete` \(or both, comma separated\)

`pm` pms the content of the tag to the user who triggered the tag

`delete` deletes the message that triggered the tag

**Formatted time blocks** strf{_strftime_}

Returns the current time formatted according to python's strftime, see [http://strftime.org/](http://strftime.org/) for more information.

**Example:** `The current year is strf{%Y} hehe`

**Redirection blocks** redirect{\#channel}

Redirects the output of the tag to the specified channel, the tag user needs to have send message permissions in the pointed channel

**Example:** `$author says: $args redirect{#screaming-out-loud}`

**Requirement blocks** require{\#channel, member, role}

takes roles, members and channels. Feel free to mix these, the logic goes as following: Channels are linked together with OR meaning as long as you use the tag in any of the mentioned channels, the channel logic evaluates to true. Roles are linked together with AND meaning you need all the specified roles. Members are linked together with OR meaning you have to be one of the specified members. Together, these are linked together with AND, meaning you can require a role AND a channel in order for it to work.

**Example:** `require{Cool kids} Word around the office is that $author is kind of a big deal`

**Blacklist blocks** blacklist{\#channel, member, role}

works like require but the other way. As soon as it sees an entity that it doesn't like, it will evaluate to false.

**Example:** `blacklist{muted, Carl#0001} Wow, this tag really is for cool people only`

**variable assignment** `!{foo=This can be anything}`

In addition to these blocks, it also comes with a few default arguments. These are:

`$unix` - Unix time, useful for math blocks

`$uses` - The amount of times the tag has been used

`$args` - The words after the tag invocation. `!foo bar baz` means $args=bar baz

`$commandargs` - The words after the tag invocation, unlike `$args` this includes mentions in the `<@id>` format \(useful for command blocks\)

`$authorid` - The ID of the person using the command, useful for command blocks

`$userid` - The ID of the first mention or author if there aren't any

`$user` - Nickname of the first mentioned user or author if there aren't any mentions

`$channel` - The name of the channel mentioned or the channel the command was used in

`$server` - The name of the server

`$mention` - The nickname of the first mentioned user or NOTHING if there aren't any mentions

`$nuser` - The _name_ of $user

`$nmention` - The _name_ of $mention

`$nauthor` - The _name_ of $author

`$authorid` - The ID of the author

`$userid` - The ID of the mentioned user if mentioned or the author if there aren't any mentions

`$serverid` - The ID of the server

`$randommember` - A random member's nickname

`$randomonline` - A random online member's nickname \(online in this case means not-offline i.e. away and busy count as online\)

`$randomoffline` - A random offline member's nickname

`$membercount` - The total number of members in the server

`$humancount` - The total number of non-bots in the server

`$botcount` - The total number of bots in the server

`$1 $2 $3 etc` - Like $args but only the first, second, third word etc. `!foo bar baz` means $1=bar

Still not sure how to use this? [See this link for some interesting and funny tags people have created using TagScript](https://pastebin.com/hXmtSpkF)

