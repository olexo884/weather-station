# ESP32 Smart Climate & Air Quality Monitor

Smart device based on **ESP32** for monitoring **indoor climate conditions and air quality** with a TFT display, Wi-Fi connectivity, web configuration interface, and Telegram alerts.

---

## ✨ Features

- Temperature & humidity monitoring (**DHT11**)
- Atmospheric pressure monitoring (**BMP180**)
- Gas / smoke detection (**MQ-2**)
- 1.8" IPS TFT display (**ST7735**, SPI)
- Battery-powered (**18650 + TP4056 + DC-DC**)
- Wi-Fi connectivity
- Built-in web configuration interface
- **Telegram bot** notifications
- RSSI signal monitoring
- Alarm indication (visual + sound)

---

## 🧠 Technology Stack

- **MCU:** ESP32
- **Language:** C++ (Arduino framework)
- **Display:** ST7735 (SPI)
- **Sensors:** DHT11, BMP180, MQ-2
- **Power:** TP4056 + DC-DC converter
- **Networking:** Wi-Fi, HTTP
- **APIs:** OpenWeatherMap, Telegram Bot API
- **Hardware design:** EasyEDA 

---

## 🧩 Hardware (Schematic & PCB)

📐 **EasyEDA link:**  
https://oshwlab.com/olexo884/diploma

---

## 🎨 User Interface (UI)

📐 **Figma link:**  
https://www.figma.com/design/dskFPgoI2V18Ywhwl1imvP/ESP32-Smart-Climate---Air-Quality-Monitor

---

## ⚙️ Setup & Configuration

### 1) OpenWeatherMap API

To enable weather data, you must use your own OpenWeatherMap API key.

In the firmware code, update the weather API URL:

```cpp
char eeromweatherApiUrl[128] =
"https://api.openweathermap.org/data/2.5/weather?lat=49.21&lon=28.42&appid=YOUR_API_KEY&units=metric&lang=uk";
```
✅ Replace `YOUR_API_KEY` with your key.
⚠️ **Do NOT commit your real API key to GitHub.**

---

### 2) Create a Telegram Bot (BotFather)

1. Open Telegram and go to **@BotFather**
2. Create a bot using `/newbot`
3. Copy the generated **bot token** (`botToken`)
4. Get your **chat ID** (`chatId`) (e.g. using `@userinfobot`)
5. You will enter `botToken` and `chatId` later through the device web interface.

---

## Wi-Fi Configuration (First Launch)

### Step 1 — Connect to the device access point

After powering the device, connect from your phone/PC to:

* **Wi-Fi name (SSID):** `Weather station`
* **Password:** `88888888`

---

### Step 2 — Set your home Wi-Fi credentials

1. Open the device web interface (after connecting to the AP above)
2. Enter:

   * Your **Wi-Fi network name (SSID)**
   * Your **Wi-Fi password**
3. Save settings
4. The device will connect to your network

---

### Step 3 — Enter location + Telegram settings

After the device connects to your Wi-Fi:

1. **Reconnect to the device** (open its web interface again)
2. Enter:

   * **Latitude** 
   * **Longitude** 
   * **Telegram `botToken`**
   * **Telegram `chatId`**
3. Save settings

✅ After saving, the device will:

* Fetch weather data from OpenWeatherMap
* Display sensor + weather data on TFT screen
* Send alerts/updates to Telegram (if enabled in firmware)

---

## Notes

* If something doesn’t work, check:

  * Wi-Fi credentials are correct
  * OpenWeather API key is valid
  * Telegram bot token and chat id are correct
  * Device has stable power

---

## Photo

<p align="center">
  <img src="device photo/photo_2025-12-15_13-57-48.jpg" >
  <img src="device photo/photo_2025-12-15_13-57-49.jpg" >
  <img src="device photo/photo_2025-12-15_13-57-51.jpg" >
</p>

---

## Author

**Oleksii Shevchuk**
ESP32 • C++ • EasyEDA • IoT / Embedded

---
