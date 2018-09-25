# Welcome and leave messages

{% hint style="info" %}
These commands do nothing before using set welcome &lt;\#channel&gt;
{% endhint %}

| Name | Example | Usage |
| :--- | :--- | :--- |
| **\[welcome\|greet\] &lt;text&gt;** | !greet Welcome $mention, we've been expecting you | Sets up a welcome message that will be sent when a new user joins. |
| **\[leave\|farewell\] &lt;text&gt;** | !farewell Goodbye $user, maybe it wasn't meant to be... | Like !greet but for people leaving |
| **banmsg &lt;text&gt;** | !banmsg **$user** just got blown the fuck out | Like !greet but for people getting banned |
| **\[dmjoin\|pmjoin\|joindm\|joinpm\] &lt;text&gt;** | !dmjoin Hello and welcome to $server, before chatting you need to assign roles in \#get-roles | Like !greet except it dms the message to the user upon joining |

All these messages will be sent to the channel saved with `!set welcome`. **Use a command without any text to remove the message.** Supports the following variables:

`$mention` - Pings the user

`$user` - The name of the user

`$nick` - The display name of the user \(not available for banmsg\)

`$server` - The name of the server

`$id` - The ID of the user

`$discrim` - The last four digits \(0080 for "Carl\#0080"\) does **not** include the hash sign.

`$membercount` - The number of members on the server \(after the event has happened\)

Also supports `#{random lists, separated by commas}` and `m{1 + 1} math blocks` not sure when you'd ever want a math block but random lists are pretty useful.

