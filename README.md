# 🤖 ChuchuBot: Scheduled Sweetness System

This repository contains the JSON configuration for **ChuchuBot**, an ESP32-based AI companion designed specifically for Tin. The bot fetches messages from this repository to deliver personalized, time-sensitive greetings and special occasion wishes.

## 📁 Repository Structure
* `sweetness.json`: The main database of scheduled messages and special dates.
* `README.md`: Instructions for managing the bot's schedule.

---

## ⚙️ How It Works
1. **Fetch:** Every hour, ChuchuBot connects to GitHub to download the latest `sweetness.json`.
2. **Internal Clock:** The ESP32 keeps time using a high-precision internal RTC (synchronized via NTP).
3. **Trigger:** When the internal clock matches a `time` entry in the JSON, Chuchu speaks the message using Wit.ai TTS.

---

## 📝 Customizing the Messages

To update Chuchu's schedule, edit the `sweetness.json` file. Each entry follows this format:

```json
{
  "date": "MM-DD", 
  "time": "HH:MM", 
  "msg": "Your sweet message here"
}
