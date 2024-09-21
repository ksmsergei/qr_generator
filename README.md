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
<img src="https://github.com/user-attachments/assets/67a61bd0-6538-4581-b251-a707ee2ab983" alt="1" width="45%">&nbsp;&nbsp;&nbsp;
<img src="https://github.com/user-attachments/assets/848613b9-10b5-44a1-b80a-a6aa9c278f08" alt="2" width="45%"><br><br>

<details>
  <summary>Encoded:</summary>
  <em>https://www.example.com</em>
</details>
<img src="https://github.com/user-attachments/assets/4f3449bc-193c-49bc-8a3d-94f26451cb5e" alt="3" width="45%"><br><br>

<details>
  <summary>Encoded:</summary>
  <em>Lorem ipsum odor amet, consectetuer adipiscing elit. Natoque commodo augue semper semper justo ullamcorper molestie neque. Velit a viverra sed, quisque consectetur mattis. Non malesuada magna imperdiet leo massa molestie pharetra. Diam feugiat nullam semper velit mi elementum. Sapien vulputate velit eu lacinia rutrum.</em>
</details>
<img src="https://github.com/user-attachments/assets/d46587cb-2a88-4e17-8f82-1631387abfa7" alt="4" width="45%"><br><br>

Used libraries
---
- [qrcodegen](https://github.com/toyobayashi/qrcodegen) - lightweight, dependency-free QR code generation
- [ST7920_lib](https://youtu.be/RuUFxePFrmo?si=xF2E6PhmXEnKz_lW) - to work with graphics on the ST7920
