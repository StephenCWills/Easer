## Better to know ##
### Condition, Event, Operation, Scenario, Profile, Script ###
These are some terms / words used in Easer. This section explains their meaning.

* Condition
  * A long-time state
  * Involves an enter and leave 
* Event
  * A short-time (momentary) "event" (as in language meaning)
* Operation
  * An action which can be carried out (by Easer)
* Scenario
  * Historical name for a pre-defined Event
* Profile
  * A collection of Operations
* Script
  * User-defined state-action sequence (consider the meaning of this word in a play / film)
  * Scripts are structured as [tree](https://en.wikipedia.org/wiki/Tree_(data_structure))
    * Script also refers to a node in the Script Tree

### From Event to Event+Condition ###
Currently, Easer is in a transition state, going from Event to Event+Condition (see [#86](https://github.com/renyuneyun/Easer/issues/86)). For backward compatibility, all Events remain there.

If you find a Condition having the same name as an Event, you should always prefer to use the Condition (and/or its corresponding `ConditionEvent`).
The only exception is when you seriously need an Event (short-time effect) rather than a Condition (continous state).

## Hackey functionalities ##
Some functionalities doesn't have official APIs so Easer uses some workarounds (reflection) to achieve that. However, they are unreliable and may not work on some devices; enabling *root features* will usually benefit these functions. Here is a list of these functionalities:

| Functionality | Class | Non-root compatibility | Root-feature compatible? |
| --- | --- | --- | --- |
| Turn mobile data (cellular data) on/off | `CellularOperationPlugin` | Maybe | Yes |
| Turn hotspot (wireless AP) on/off | `HotspotOperationPlugin` | Maybe | Not yet |
| Execute commands | `CommandOperationPlugin` | Probably not (it's said executing commands requires root permission, or it would faild) | Yes |

It is very welcomed to [[report compatibility | 兼容性 Compatibility]] situation on different devices and/or ROMs.

## Functionality Explained ##
Currently, the UI of Easer is not pretty and needs a lot of improvements; some behaviors may not exactly follow your mind. They are listed here.

* Easer will use relevant system **permissions** to check events and change settings. Although there is runtime permission check, please do not REVOKE the permissions granted to Easer (or the relevant functions won't run correctly).
* Changing brightness will start a transparent screen (`Activity`) for a very short period (and it will finish itself automatically), which may affect the work or game you are current doing. This is due to the fact that there is no "official" way to change the brightness from a background service.
* Time (`TimeEventPlugin`) uses Android's system level notification mechanism (`AlarmManager`), which is ***inexact*** (from Android 4.4) to *minimize wakeups and battery use* as said in the [official document](https://developer.android.com/reference/android/app/AlarmManager.html). My observation of the maximum shift is 3 minutes.
* Similarly, Date (`DateEventPlugin`) also uses `AlarmManager` so it may also be inexact (though this behavior is relatively less harmful because 3 minutes is only a small portion compared to a day).
* `Before` and `After` (`EventType`) are **inclusive** (not sure if it will be useful to have them exclusive).
* Most events won't be re-triggered if it is already satisfied and hasn't become unsatisfied yet. That said, you won't need to worry about creating an "after 3:00pm" event and it repeats triggering all the time. The small amount of re-triggerable events are designed to be so because of their natural property, so users won't need to worry about that -- just follow what you feel to use them.

## Permission ##
See [[here|權限 Permission]] for the full explaination.