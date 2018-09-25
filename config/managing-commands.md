# Managing commands



| Name | Example | Usage |
| :--- | :--- | :--- |
| **ignore \[channel\]\[command\]**  | !ignore \#general temp home | If no channel is specified, the current channel is ignored. If a command is supplied, it will ignore that command in the specified channel. Manage server bypassese this. |
| **ignore server** | -- | This is essentially the same as making the entire bot mod-only |
| **ignore all \[command\]**  | !ignore all pc top | This is equal to typing !ignore channel command subcommand in all channels the bot can see, useful if you want to ignore a command in all channels except for one. This will not work for channels created in the future. If the command is already ignored in a channel, this will unignore it. |
| **unignore \[channel\] \[command\]** | !unignore \#general temp | Reverses what !ignore does |
| **unignore all** | -- | Unignores all channels \(this does not take ignored commands into account\) |
| **disable &lt;command&gt;** | !disable pc top | This really disables the command globally from the server, not even manage server bypasses this. |
| **disablemany &lt;commands...&gt;** | !disablemany "pc top" cat dog "tag get" | Like !disable except it takes more than one command |
| **enable &lt;command&gt;** | !enable pc top | Enables a previously disabled command. |
| **enablemany &lt;commands...&gt;** | !enablemany "pc top" cat dog "tag get" | Like !enable except it takes more than one command |
| **enable all** | -- | Sets all commands to enabled. |
| **disable all** | -- | Sets all commands to disabled. |
| **enable mod** | -- | Enables all moderation commands |
| **disable mod** | -- | Disables all moderation commands |
| enable list | -- | Shows all enabled/disabled commands. |
| **plonk** | !plonk @Carl\#0080 tag create | This works almost exactly like !ignore but for users instead. If no command is specified, the user is banned from using the bot completely. |
| **unplonk &lt;@member&gt; \[command\]** | !unplonk @Carl\#0080 | Unbans the user from using the bot |
| **plonks** | -- | Displays all plonked users. |
| **restrict &lt;command&gt;** | !restrict define | This requires a bot channel to utilize. Makes it so that if the command is used outside of the bot channel, the bot will ping the user in the botchannel and give the results there instead. |
| **unrestrict &lt;command&gt;** | !unrestrict d | Unrestricts it. Like all commands where you pass in a command, aliases work just as well. |
| **modonly &lt;command&gt;** | !modonly echo | Makes a command usable by mods only |
| **unmodonly &lt;command&gt;** | !unmodonly dog | Removes a command from the modonly list |
| **modrole &lt;role&gt;** | !modrole bot commander | Makes it so that any member with the specified role is seen as a moderator by the bot. This does not allow members with this role to kick, ban, mute, warn or any variation of these commands. |
| **modrole clear** |  | Removes the modrole |

