# Uncategorized utilities



| Name | Example | Usage |
| :--- | :--- | :--- |
| poll &lt;question&gt; | !poll should I sleep? | Creates a yes/no poll where you vote with reactions |
| quickpoll &lt;question \| answers...&gt; | !quickpoll best game?\| wow \| overwatch \| only losers play games | Use pipes `|` or commas to separate the questions and answers. The first arg is the question, all after that are individual answers. You can't mix pipes and commas, pipes are intended for polls where you want commas in the question or answer. |
| \[d\|define\] &lt;word&gt; | !define well | Shows the oxford dictionary's definition for the word. Note: due to the length of some definitions it might be a good idea to restrict this command to prevent abuse. |
| wolfram | !wa e ^ \(pi \* i\) + 1 | This is similar to going to wolframalpha and entering the text yourself. Doesn't support complicated answers. |
| \[pick\|choice\|select\] &lt;choices&gt; | !choose go to sleep, play overwatch | Picks one of your specified arguments. Use commas for multiple words. |
| activity \[day/week/month/year\] | !activity week | Defaults to month, shows the 25 most active members by postcount for the specified timespan \(that the bot has seen\) |
| \[ud\|urbandictionary\] &lt;word&gt; | !ud cleveland steamer | Returns the urbandictionary definition for your word. @everyone proof. \(looking at you, b1nzy\) |
| \[i\|info\] \[@member\] | !i @Carl\#0080 | Returns Name, last 5 nicknames, id, postcount \(that the bot has seen\), creation date, server join date  and some cool information related to these |
| \[weather\|temp\] \[location\] | !weather stockholm | If no city is specified, it will give you info for your set home. If used for the first time, that city will be set as your home. Since countries don't have weather \(think about it\) you have to be more specific. |
| temp home &lt;location&gt; | !temp home tampa | Lets you set a city as your home for !temp to default to. |
| \[nicks\|nicknames\] \[@user\] | -- | Shows you your nicknames history, duplicates are moved to the end of the list. The names are ordered from oldest to newest. |
| dice \[sides\] \[rolls\] | !dice 6 | Rolls a \[sides\] sided die \[rolls\] times. Defaults to 6 sides and 1 roll. |
| roll \[lower-\[upper\]\] | !roll 100-1100 | Works just like in wow, defaults to 1 to 100. Changing just one number will change the upper bound. |
| \[flip\|coin\] | -- | Flips a coin |
| \[g\|google\] | !g umami wiki | Like googling, safesearch is set to medium. |
| avatar &lt;member/ID&gt; | !avatar | Shows the avatar of a mentioned user or yourself if you don't. Works even if the user doesn't share a server with the bot. Also works in dms, you creeps. |

