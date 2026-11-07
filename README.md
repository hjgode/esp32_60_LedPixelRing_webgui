# esp32_60_neopixel_ring_clock

based on https://github.com/AndroidCrypto/ESP32_60_LED-Pixel_Ring_Clock

# Requirements

* Arduino IDE 2.x
* PlatformIO (within VS code)
* esp32 dev board

## Libs

* packages/esp32/hardware/esp32/2.0.17
* WiFi.h: WiFi@2.0.0
* MQTT.h: MQTT@2.5.3
* ArduinoJson.h: ArduinoJson@7.4.3
* Adafruit_NeoPixel.h: Adafruit NeoPixel@1.15.5
* npuckett/WebGUI@^1.9.2
* yiannisbourkelis/Uptime Library@^1.0.0

# Changes

* Added customization options by using variables for colors etc.

* Settings can be changed using mqtt (/esp32_clock/...), yes it starts with a slash (due to mqtt lib :-( :

## possible mqtt values

  * brightness  0-255
  * offset      0-59

  * handleMinuteColor as 32Bit Hex number, ie 001f3a40
  * handleHourColor
  * handleSecondColor
  * tickColor

  * dimOn
  * valueDim
  * hourStartDim
  * hourStopDim
  * dumpValues
  * save_Pref
  * load_Pref
  * getAutoDimmed

# esp32_60_LedPixelRing_webgui
Added the WebGUI lib, altered it and implemented the WebGui for the pixel clock.

<img width="408" height="953" alt="pxielclock_webgui" src="https://github.com/user-attachments/assets/706a8a7c-ebfc-4fa1-be13-a355c95ceb0f" />

# Python dashboard

psDashboard.py is a Python3 tkinter example showing how to control the settings remotely.

![psDashboard Main](https://github.com/hjgode/esp32_60_neopixel_ring_clock/blob/9d646ae0bf7fe0a3f8feaba2e00650157cc20d4e/psDashboard_main.png)

![psDashboard Color Selection](https://github.com/hjgode/esp32_60_neopixel_ring_clock/blob/9d646ae0bf7fe0a3f8feaba2e00650157cc20d4e/psDashboard_color.png)

# Changes

Settings are saved and reloaded between reboots.

The hour moves smoothly between the full hours, easier to read when you see it is after or before 11:00 AM. So, if it is 06:30, the hour pixel set is not at 6 but between 6 and 7.

The clock showing 09:25:45

![Pixel clock photo](https://github.com/hjgode/esp32_60_neopixel_ring_clock/blob/5ef2be4af3a323e3352b8f6ffa679801d1c3fcdf/pixel_clock_09-25-45.jpg)

You see the hour tick (red) is not on 09 but more to 10. The minute tick is the green one.

The hour tick is not only showing one LED but the neighbor LEDs too with 50% brightness.
