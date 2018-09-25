# Anti-raid and mentionspam



| Name | Example | Usage |
| :--- | :--- | :--- |
| **mentionspam &lt;count&gt;** | !mentionspam 5 | Enables the bot to automatically punish mentionspammers. By default this action is banning, but it can be changed using the next command. |
| **mentionspam action &lt;action&gt;** | !mentionspam action ban | Action is one of kick, mute, ban or delete. Delete just deletes the message, which is actually sort of counterproductive. |
| **mentionspam ignore &lt;\#channels...&gt;** | !mentionspam ignore \#announcement | Although mods are excluded from the mentionspam prevention, using this allows your members to spam mentions in certain channels, if you so desire. |
| **mentionspam unignore &lt;\#channels...&gt;** | !mentionspam ignore \#general \#announcements | Undoes what **!mentionspam ignore** does. |
| **raid basic** | -- | Basic antiraid. Sets verification level to table flip and deletes messages from members who joined less than 30 minutes ago. |
| **raid strict** | -- | Strict antiraid kicks members who joined less than 30 minutes ago whenever they send a message or join a voice channel. |
| **raid insane** | -- | Insane antiraid is strict but kicked members who rejoin will immediately be kicked. |
| **raid off** | -- | Disables the anti-raid \(mentionspam will still be active if you had it\). |

