# Figma TV Remote

Use your phone as a TV remote for a Figma prototype. Nothing to install on either device.

Each remote button presses a key inside the prototype, so you design with Figma's normal **Key/Gamepad** triggers. Interactive components, Smart Animate, variables and conditionals all keep working.

## How to use

1. Open the setup page on your computer.
2. Drag the **TV Remote** button to your browser's bookmarks bar.
3. Scan the QR code with your phone. Add it to your home screen for a full-screen remote.
4. Open your prototype in Chrome or Edge, click the bookmark, then click the prototype once.
5. In the prototype's **Options** menu, turn off **Enable Figma shortcuts**.

The bookmarklet works in a browser, not in the Figma desktop app. If your browser blocks it, use **Copy as console snippet** on the setup page and paste it into the prototype tab's DevTools console.

## Key map

| Remote button | Key in Figma |
| --- | --- |
| Up / Down / Left / Right | Arrow keys |
| OK | Enter |
| Back | Backspace |
| Restart | R |
| Main Menu | M |
| Help | H |
| Voice Assistant | V |
| Next Prototype | N |
| Previous Prototype | P |

## How it works

The phone and the prototype tab both connect to a free public MQTT relay (HiveMQ) over secure WebSockets, using a random pairing code as the channel name. Each code is stored in the browser that made it. The prototype side only accepts the 13 keys above, so nothing else can be typed into your prototype. Taps take roughly 100–200 ms to arrive.

Everything is in `index.html`. There's no build step and no server.
