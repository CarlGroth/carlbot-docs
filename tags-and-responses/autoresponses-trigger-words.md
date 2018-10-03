# Autoresponses \(trigger words\)

{% hint style="danger" %}
Autoresponses are not custom commands, if you want things that are triggered by a prefix and a keyword, see the tag section. They offer more functionality, better editing capabilities, will _never_ have a limit to them and are just generally nicer for their intended purpose.
{% endhint %}

| Name | Example | Usage |
| :--- | :--- | :--- |
| **\[ar\|autoresponse\]** | -- | Lists the triggers, and ignores for the server |
| **ar list** | -- | Lists all the triggers in a paginated fashion |
| **ar \[add\|create\] &lt;trigger&gt; &lt;response&gt;** | !ar add "hello there" Hello! I'm a bot created by carl :muscle: | Adds a trigger that carlbot will look for and say/do something when it is said. This command looks for a substring within the message, meaning that if you add _hi_ then _t_**hi**_s_ will also match. See the next command if that is too greedy for you. |
| **ar \[strict\|s\] &lt;trigger&gt; &lt;response&gt;** | !ar strict "its coming home" reactu{⚽️} | This works a lot like normal ar add with one vital exception: it looks for exact sequences of words, rather than substrings. What this means is that if you add the strict trigger `hell` and someone says `hello` it will not match, it also means that triggers with more than one word requires an exact match per word \(this is a lot more reasonable to use than this text makes it out to be\). |
| **ar \[exact\|e\] &lt;trigger&gt; &lt;response&gt;** | !ar exact "hey guys" Hello! | This matches if the content of a message is the same as the trigger. Some exceptions such as punctuation and capitalization applies. |
| **ar \[startswith\|sw\] &lt;trigger&gt; &lt;response&gt;** | !ar sw "how do i" read the wiki! | Matches if the start of the message matches |
| **ar \[endswith\|ew\] &lt;trigger&gt; &lt;response&gt;** | !ar ew "i think" no you don't | Like startswith except if it ends with it. |
| **ar \[remove\|del\|-\|delete\] &lt;trigger&gt;** | !ar del its coming home | Removes an autoresponse |
| **ar clear** | -- | Removes all autoresponses \(with a prompt\) |
| **ar \[channel\|cs\] &lt;trigger&gt; &lt;response&gt;** | !ar channel "king crimson" HOW DOES KING CRIMSON WORK I DON'T UNDERSTAND | Like a normal autoresponse except it only listens in the channel you used the command in. **Note:** This will bypass any channel ignores \(member ignores still work\). |
| **ar ignore &lt;members or channels...&gt;** | !ar ignore @Carl\#0001 @Kintark\#0588 \#general  @idiotuser\#1337 \#welcome | Blocks channels and or users from triggering responses |
| **ar unignore &lt;members or channels...&gt;** | !ar unignore \#general @Carl\#0001 | Undoes what !ar ignore does |

Autoreactions support a subset of tagscript.

**Redirecting output** `redirect{#log}`

If you want to send the message to the person who triggered it, see action blocks.

**Random lists** `#{comma, separated,#{nested args}}`

**Unique random list variables** `#variablename{comma, separated, values}`

Unlike random lists assigned to a variable through variable blocks, unique random lists randomly pick an element each time.

**Math blocks** `m{1 + 1 / (3 ^ 9)}`

Supports relatively advanced math.

`+ - * / ^ % sin cos tan exp abs trunc round sgn log ln log2`

**React blocks** `react{:regional_indicator_f:}` `reactu{:regional_indicator_x:}`

This will react to the response \(react\) or original message \(reactu\) with the emojis placed inside the brackets

**50/50 blocks** `?{Will anyone see me?}`

**Action blocks** a{_action_} where _action_ is `pm` or `delete` \(or both, comma separated\)

`pm` pms the content of the response to the user who triggered it

`delete` deletes the trigger message

**Requirement blocks** require{\#channel, member, role}

takes roles, members and channels. Feel free to mix these, the logic goes as following: Channels are linked together with OR meaning as long as you use the tag in any of the mentioned channels, the channel logic evaluates to true. Roles are linked together with AND meaning you need all the specified roles. Members are linked together with OR meaning you have to be one of the specified members. Together, these are linked together with AND, meaning you can require a role AND a channel in order for it to work.

**Example:** `require{Cool kids} Word around the office is that $author is kind of a big deal`

**Blacklist blocks** blacklist{\#channel, member, role}

works like require but the other way. As soon as it sees an entity that it doesn't like, it will evaluate to false.

**Formatted time blocks** strf{_strftime_}

Returns the current time formatted according to python's strftime, see [http://strftime.org/](http://strftime.org/) for more information.

**Example:** `The current year is strf{%Y} hehe`

**variable assignment** `!{foo=This can be anything}`

In addition to these blocks, it also comes with a few default arguments. These are:

`$authorid` - The ID of the person who triggered the response

`$userid` - The ID of the first mention or author if there aren't any

`$user` - Nickname of the first mentioned user or author if there aren't any mentions

`$author` - Nickname of the member using the command

`$channel` - The name of the channel mentioned or the channel the command was used in

`$server` - The name of the server

`$mention` - Mentions the member who triggered the autoresponse

`$nuser` - The _name_ of $user

`$nauthor` - The _name_ of $author

`$authorid` - The ID of the author

`$userid` - The ID of the mentioned user if mentioned or the author if there aren't any mentions

`$serverid` - The ID of the server

`$randommember` - A random member's nickname

`$randomonline` - A random online member's nickname \(online in this case means not-offline i.e. away and busy count as online\)

`$randomoffline` - A random offline member's nickname

