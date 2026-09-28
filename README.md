# Direct Malayalam Voice Translator to ESP32 LCD

A Web Bluetooth and Web Speech-enabled web application that translates Malayalam speech to English in real time and sends the translated text directly over Bluetooth Low Energy (BLE) to an ESP32 connected to an LCD display.

---

## 🚀 Features

- **Malayalam Speech Recognition**: Uses the Web Speech API (`ml-IN`) for voice transcription.
- **Real-time Translation**: Automatic Malayalam-to-English translation powered by the MyMemory API.
- **BLE Transmission**: Transmits translated text directly to an ESP32 via Nordic UART BLE service.
- **Lightweight & Dependency-free**: Pure HTML5 and vanilla JavaScript — runs directly in modern browsers without build tools.

---

## 📱 Hardware & BLE Specifications

- **Device Name**: `ESP32_AutoTranslator`
- **UART Service UUID**: `6e400001-b5a3-f393-e0a9-e50e24dcca9e`
- **RX Characteristic UUID**: `6e400002-b5a3-f393-e0a9-e50e24dcca9e`

---

## 🛠️ How to Run

### Requirements
- **Google Chrome** or **Microsoft Edge** (Required for Web Bluetooth API; Firefox does not support Web Bluetooth).
- Bluetooth enabled on your device.

### Running Locally
You can serve the directory using any HTTP server:

```bash
# Using Python
python -m http.server 3000

# Using Node.js
npx serve -l 3000
```

Open `http://localhost:3000` in Google Chrome.

### Running on Android Chrome
Web Bluetooth and the Web Speech API require a **Secure Context** (`https://` or `localhost`):
1. Connect your Android phone to your PC via USB with USB Debugging enabled.
2. In PC Chrome, navigate to `chrome://inspect/#devices`.
3. Enable **Port forwarding**: add `3000` pointing to `localhost:3000`.
4. Open Chrome on your phone and browse to `http://localhost:3000`.

---

## 📋 Usage Workflow

1. Power on your ESP32 with the firmware advertising as `ESP32_AutoTranslator`.
2. Open the web app and click **`1. Connect to ESP32`**.
3. Select your ESP32 from the Bluetooth chooser dialog.
4. Click **`🎤 2. Speak Malayalam`** and speak your sentence.
5. The Malayalam text is transcribed, translated to English, and sent to the ESP32 LCD display.
