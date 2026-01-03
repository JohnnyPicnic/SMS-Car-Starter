# SMS-Car-Starter
Use a ESP32 with SIM7600 to interact with a remote car starter
KORE wireless provides a SIM plan with pay per use data and SMS
The ESP32 and modem are normally sleeping and wake up when a SMS is received or at timed intervals to check the network.
Depending on the received message the ESP32 send a UDP message back to KORE wireless which is then forwarded to a webhook of your choosing.
