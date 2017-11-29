This page describes the permissions required by Easer -- where they are used.

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