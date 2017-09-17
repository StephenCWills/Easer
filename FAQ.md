## Hackey functionalities ##
Some functionalities doesn't have official APIs so Easer uses some workarounds (reflection) to achieve that. However, they are unreliable and may not work on some devices. Here is a list of these functionalities:

* Turn mobile data (cellular data) on/off (`CellularOperationPlugin`)
* Turn hotspot (wireless AP) on/off (`HotspotOperationPlugin`)

It *may* be helpful to install Easer as a system app in order to make them work correctly (I remember there is a example in one of the issues stating this, but I couldn't find it now).
In future releases, a dedicated area will be used to organize them.

## Functionality Explained ##
Currently, the UI of Easer is not pretty and needs a lot of improvements; some behaviors may not exactly follow your mind. They are listed here.

* Easer will use relevant system **permissions** to check events and change settings. However, there is no runtime permission check currently. Please give Easer the relevant permission before you use certain events and/or profiles.
* Although the UI part for creating and editing *Event* shows as checkbox, but they should actually be radio buttons (which means only **one** of them is going to be used). Selecting _multiple_ items will do **nothing** other than exercising you finger.
* Time (`TimeEventPlugin`) uses Android's system level notification mechanism (`AlarmManager`), which is ***inexact*** (from Android 4.4) to *minimize wakeups and battery use* as said in the [official document](https://developer.android.com/reference/android/app/AlarmManager.html). My observation of the maximum shift is 3 minutes.
* Similarly, Date (`DateEventPlugin`) also uses `AlarmManager` so it may also be inexact (though this behavior is relatively less harmful because 3 minutes is only a small portion compared to a day).
* `Before` and `After` (`EventType`) are **inclusive**. (I'm not sure if it will be useful to have them exclusive.)
* Events won't be re-triggered if it is already satisfied and hasn't become unsatisfied yet. That said, you won't need to worry about creating an "after 3:00pm" event and it repeats triggering all the time.