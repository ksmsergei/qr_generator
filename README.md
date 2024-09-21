# qr_generator
A program for **STM32 Blue Pill** board, which receives text via **UART** protocol and generates QR code by it, displaying it on **ST7920** LCD display.

Usage
---
Generating a QR code requires sending an encoded string over the UART protocol. It is important that the last byte of this string should be a null character - <code>'\0'</code>.

After receiving it, QR Code generation will start and after drawing it will wait for a new string to be received.

Limitations
---
Due to the screen size of 128x64 pixels, the maximum version of the QR code that can be used is 11 (61x61 pixels). At the minimum correlation level, this QR code can encrypt
- **772** numeric characters
- **468** alphanumeric characters
- **321** bytes

A small demonstration
---

<img src="https://github.com/user-attachments/assets/9de2db33-34fb-489d-b26d-45896245ca7c" alt="1" width="50%"><br><br>
<img src="https://github.com/user-attachments/assets/30e87446-cdf0-4ca2-a535-281cb2975c3f" alt="2" width="50%"><br><br>

<details>
  <summary>Encoded:</summary>
  <em>https://www.example.com</em>
</details>
<img src="https://github.com/user-attachments/assets/52b5fdb8-9b3b-47b8-840b-807a67cd8908" alt="3" width="50%"><br><br>

<details>
  <summary>Encoded:</summary>
  <em>Lorem ipsum odor amet, consectetuer adipiscing elit. Natoque commodo augue semper semper justo ullamcorper molestie neque. Velit a viverra sed, quisque consectetur mattis. Non malesuada magna imperdiet leo massa molestie pharetra. Diam feugiat nullam semper velit mi elementum. Sapien vulputate velit eu lacinia rutrum.</em>
</details>
<img src="https://github.com/user-attachments/assets/6257cbc2-d2d9-463e-9036-7176a71ce6b2" alt="4" width="50%"><br><br>

Used libraries
---
- [qrcodegen](https://github.com/toyobayashi/qrcodegen) - lightweight, dependency-free QR code generation
- [ST7920_lib](https://youtu.be/RuUFxePFrmo?si=xF2E6PhmXEnKz_lW) - to work with graphics on the ST7920
