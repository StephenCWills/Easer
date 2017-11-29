## Hackey functionalities ##
Some functionalities doesn't have official APIs so Easer uses some workarounds (reflection) to achieve that. However, they are unreliable and may not work on some devices; enabling *root features* will usually benefit these functions. Here is a list of these functionalities:

| Functionality | Class | Non-root compatibility | Root-feature compatible? |
| --- | --- | --- | --- |
| Turn mobile data (cellular data) on/off | `CellularOperationPlugin` | Maybe | Yes |
| Turn hotspot (wireless AP) on/off | `HotspotOperationPlugin` | Maybe | Not yet |
| Execute commands | `CommandOperationPlugin` | Probably not (it's said executing commands requires root permission, or it would faild) | Yes |

It is very welcomed to [[report compatibility | Compatibility]] situation on different devices and/or ROMs.

## Functionality Explained ##
Currently, the UI of Easer is not pretty and needs a lot of improvements; some behaviors may not exactly follow your mind. They are listed here.

* Easer will use relevant system **permissions** to check events and change settings. However, there is no runtime permission check currently. Please give Easer the relevant permission before you use certain events and/or profiles.
* Time (`TimeEventPlugin`) uses Android's system level notification mechanism (`AlarmManager`), which is ***inexact*** (from Android 4.4) to *minimize wakeups and battery use* as said in the [official document](https://developer.android.com/reference/android/app/AlarmManager.html). My observation of the maximum shift is 3 minutes.
* Similarly, Date (`DateEventPlugin`) also uses `AlarmManager` so it may also be inexact (though this behavior is relatively less harmful because 3 minutes is only a small portion compared to a day).
* `Before` and `After` (`EventType`) are **inclusive** (not sure if it will be useful to have them exclusive).
* Events won't be re-triggered if it is already satisfied and hasn't become unsatisfied yet. That said, you won't need to worry about creating an "after 3:00pm" event and it repeats triggering all the time.

## Permission ##
See [[here|權限 Permission]] for the full explaination.