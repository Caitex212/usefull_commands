# Fedora Hyprland Setup Notes
This repository contains personal notes and command references for setting up and configuring my Fedora Hyprland installation.

Content:
* 📷 [Mobile as Webcam](#mobile-as-webcam)
* 🖥️ [Mobile as Second Monitor](#mobile-as-second-monitor)
* 📶 [Connect ADB Wirelessly](#connect-adb-wirelessly)

---

## 📷 Mobile as Webcam

1. Add a virtual webcam:

   ```bash
   sudo v4l2loopback-ctl add -n "Webcam" /dev/video1
   ```

2. Connect your phone via ADB (USB or Wi-Fi).

3. Start scrcpy with camera stream:

   ```bash
   scrcpy --video-source=camera --camera-size=1920x1080 --camera-facing=front --v4l2-sink=/dev/video1 --no-playback
   ```

---

## 🖥️ Mobile as Second Monitor

1. Install Moonlight on your mobile device.

2. Set video resolution to the native resolution of your device.

3. Create a headless screen:

   ```bash
   hyprctl output create headless virtual01
   ```

4. Install Sunshine on your PC.

5. In Sunshine, go to Configuration → Audio/Video → set Display Number to 1.

6. Connect from your phone and enjoy your second screen.

Optional: To remove the virtual monitor:

```bash
hyprctl output remove virtual01
```

---

## 📶 Connect ADB Wirelessly

1. Connect your phone to the PC via USB.

2. Enable ADB over TCP/IP:

   ```bash
   adb tcpip 5555
   ```

3. Disconnect the USB cable.

4. Connect to your phone via IP address:

   ```bash
   adb connect [phone-ip-address]
   ```
