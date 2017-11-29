該頁面列出並解釋Easer所申請的權限——解釋它們被用在哪裏。  
This page describes the permissions required by Easer -- where they are used. ([Go to English version](#permission))

## 權限 ##
| 權限 | 用途 | 用於 |
| --- | --- | --- |
| `ACCESS_COARSE_LOCATION` | 獲取基站ID | `CellLocationEventPlugin` |
| `ACCESS_NETWORK_STATE` | `ACCESS_WIFI_STATE`的前置要求 (不確定) | `WifiEventPlugin` |
| `ACCESS_WIFI_STATE` | 獲取WiFi狀態 | `WifiEventPlugin` |
| `BLUETOOTH` | 獲取藍牙狀態 | `BTDeviceEventPlugin` |
| `BLUETOOTH_ADMIN` | 打開/關閉藍牙 | `BluetoothOperationPlugin` |
| `CHANGE_NETWORK_STATE` | `CHANGE_WIFI_STATE`的前置要求 (不確定) | `WifiOperationPlugin` |
| `CHANGE_WIFI_STATE` | 打開/關閉WiFi | `WifiOperationPlugin` |
| `MODIFY_AUDIO_SETTINGS` | 修改響鈴模式 | `RingerModeOperationPlugin` |
| `READ_CALENDAR` | 讀取日曆內容 | `CalendarEventPlugin` |
| `READ_SMS` | 讀取短信（發送人、內容） | `SmsEventPlugin` |
| `RECEIVE_BOOT_COMPLETED` | 監聽系統啓動完成並且（根據設置）自動啓動Easer | `BootupReceiver` |
| `RECEIVE_SMS` | 監聽收到短信事件（輔助`READ_SMS`） | `SmsEventPlugin` |
| `SEND_SMS` | 發送短信 | `SendSmsOperationPlugin` |
| `WRITE_EXTERNAL_STORAGE` | 導入/導出數據 && 保存日誌 | 系統設置中的*導出*功能 && 全局的Logger日誌 |
| `WRITE_SETTINGS` | 修改系統設置（如亮度） | `BrightnessOperationPlugin` `RotationOperationPlugin` |


## Permission ##
| Permission | Usage | Used by |
| --- | --- | --- |
| `ACCESS_COARSE_LOCATION` | Get basestation ID | `CellLocationEventPlugin` |
| `ACCESS_NETWORK_STATE` | Pre-request of `ACCESS_WIFI_STATE` (not exactly sure) | `WifiEventPlugin` |
| `ACCESS_WIFI_STATE` | Get WiFi status | `WifiEventPlugin` |
| `BLUETOOTH` | Access Bluetooth status | `BTDeviceEventPlugin` |
| `BLUETOOTH_ADMIN` | Switch Bluetooth on/off | `BluetoothOperationPlugin` |
| `CHANGE_NETWORK_STATE` | Pre-request of `CHANGE_WIFI_STATE` (not exactly sure) | `WifiOperationPlugin` |
| `CHANGE_WIFI_STATE` | Turn Wifi on/off | `WifiOperationPlugin` |
| `MODIFY_AUDIO_SETTINGS` | Change ringer mode | `RingerModeOperationPlugin` |
| `READ_CALENDAR` | Read calendar data | `CalendarEventPlugin` |
| `READ_SMS` | Read the content and sender of SMS | `SmsEventPlugin` |
| `RECEIVE_BOOT_COMPLETED` | Listen for system boot and (depending on settings) auto-start Easer | `BootupReceiver` |
| `RECEIVE_SMS` | Listen to the incoming of a new SMS (used as a companion of `READ_SMS`) | `SmsEventPlugin` |
| `SEND_SMS` | Send a new SMS | `SensSmsOperationPlugin` |
| `WRITE_EXTERNAL_STORAGE` | Import/Export data && Save logs | *Export* in Settings page && global Logger |
| `WRITE_SETTINGS` | Change system settings (e.g. brightness) | `BrightnessOperationPlugin` `RotationOperationPlugin` |