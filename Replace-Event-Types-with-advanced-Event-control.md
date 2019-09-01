When choosing Event as the Script trigger, you may notice there are two extra toggle bars below the Event name. They are the *advanced Event control* (known as *advanced Scenario condition* previously).

You can use them to alter the behaviour of that particular Script, overriding the original semantics of an "event".

## Volatile and Persistent

"Volatile" and "persistent" refers to the state change of the Script node, and in turn affects the children nodes.

By default, an Event is immediate, which is "volatile": The node will become `true` and then immediately `false` after (recursively) testing and processing the children nodes.

When setting "persistent", the node will be kept `true` after the Event has happened once (until Easer stops, of course). The only way to make it `false` is by using a specific Operation (named "Control Script Node Status").

## Repeatable

"Repeatable" means the corresponding Profile can be triggered again (and again...) when the Event happens again.

This setting is specifically useful when used together with "persistent". 


## Old notes (no need to read unless interested in history)

Event Types will be dropped in v0.5.7 (article written for v0.5.6). They can be replaced by advanced Scenario conditions.

Generally, Event Types have these direct mappings:
* is / any <--> nothing to do (i.e. set *reverse* to `false` & set *retriggerable* to `false` & set *volatile*)
* is_not / none <--> set *reverse* to `true`
* after <--> set *persistent* & (maybe) set *retriggerable* to `true`
* before <--> combination of *is_not* and *after*