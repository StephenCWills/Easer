[[Some functionalities|FAQ]] of Easer have to be implemented in a hacky way because of the restriction of Android. This page lists that, and points to the relevant contents for future use (if any).  
由於Android的限制，Easer的[[部分功能|須知]]不得不用hacky的方式實現。本頁面列出它們，並指向相關的內容以便（或許存在的）未來使用。

    This page is not complete. Please feel free to add more relevant information.

# Not-supported by API | 無API支持

Generally speaking, if something is not supported by API, it can't be done reliably at all -- something works on one device may not work on another, on one ROM but not on another.  
In most cases, they are done either by using "hidden API" or using "root".  
可以認爲，沒有API支持的功能完全無法被可靠實現——部分設備可能能用，其他的可能不能；某個ROM上能用，但另一個上不行。  
絕大多數情況下，實現依賴「隱藏API」或「root」。

## `CellularOperationPlugin` (toggle mobile data | 開關數據網絡)

[#118](../issues/118)

## `HotspotOperationPlugin` (toggle hotspot | 開關熱點)

## `AirplaneOperationPlugin` (toggle airplane | 開關飛行模式)

[#261](../issues/261)

## Toggle NFC | 開關NFC

[#253](../issues/253)

## Split mode | 分屏模式

[[#248](../issues/248)


# Restricted API | 受限的API

## `CommandOperationPlugin` (execute commands | 執行命令)

## Detect app launching / current app | 檢測app啓動/當前app

[#119](../issues/119)
