# SMS-Car-Starter

Remote-start your vehicle using an **ESP32 + SIM7600 (LilyGo T-SIM7600)** with SMS commands and optional UDP callbacks through **KORE Wireless**.

This project uses the LilyGo ESP32/SIM7600 board to receive SMS instructions, wake from deep sleep, trigger a car starter, and optionally send a small UDP message back to KORE Wireless, which forwards it to your webhook. The system is optimized for extremely low power usage and reliable 24/7 operation.

---

## Hardware

This project requires the **LilyGo T-SIM7600** board — an ESP32 with an integrated SIM7600 4G/LTE modem.

**Official LilyGo Documentation:**  
https://github.com/Xinyuan-LilyGO/LilyGo-Modem-Series/blob/main/docs/en/esp32/sim7600-esp32/README.MD

---

## Features

- Receive SMS commands using the SIM7600 modem  
- Trigger remote car starter actions via ESP32 GPIO  
- ESP32 deep sleep plus SIM7600 sleep for ultra-low standby power  
- Wake on incoming SMS or periodic timed network checks  
- UDP callback to KORE Wireless, forwarded to your server/webhook  

---

## How It Works

1. ESP32 + SIM7600 remain in deep sleep to minimize power consumption.  
2. An incoming SMS or a scheduled check wakes the modem and ESP32.  
3. The ESP32 parses the SMS contents (e.g., `START`, `LOCK`, `UNLOCK`, `STATUS`).  
4. GPIO pins trigger relays or signals to control your car starter.  
5. A small UDP message is sent to KORE Wireless, which forwards it to your chosen webhook URL.  
6. The system returns to sleep until the next event.

---

## Requirements

- LilyGo T-SIM7600 board (ESP32 + SIM7600 LTE)
- KORE Wireless SIM plan (SMS + minimal data recommended)
- Remote car starter harness or relay interface
- Stable 5V power supply (e.g., vehicle 12V → 5V buck converter)

---

## Useful Links

- LilyGo Modem Series (SIM7600-ESP32 Documentation):  
  https://github.com/Xinyuan-LilyGO/LilyGo-Modem-Series/blob/main/docs/en/esp32/sim7600-esp32/README.MD

---

## Notes

- SMS is the primary communication method, making this system ideal for low-signal or remote locations.
- UDP packets are only a few bytes, keeping KORE pay-per-use data extremely low.
- Designed for reliability and long-term unattended operation.


