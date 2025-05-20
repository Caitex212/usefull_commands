Hello, this is my repo for saving commands for my Fedora Hyprland installation I always forget...

# Mobile as Webcam
1. ```sudo v4l2loopback-ctl add -n "Webcam" /dev/video1```
2. connect phone via adb (cable or wifi)
3. ```scrcpy --video-source=camera --camera-size=1920x1080 --camera-facing=front --v4l2-sink=/dev/video1 --no-playback```

# Mobile as second Monitor
1. setup moonlight on the mobile phone
2. set Video Resolution to native
3. create headless screen ```hyprctl output create headless virtual01```
4. install sunshine on pc
5. Set Configuration -> Audio/Video -> Display Number to 1
6. connect your phone and have fun

# Connect adb wireless (wifi)
1. connect phone to pc
2. ```adb tcpip 5555```
3. disconnect phone
4. ```àdb connect [phone ip address]```
