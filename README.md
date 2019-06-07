|   |   |
|---|---|
|<img src="img/vai-ports.png">|<img src="img/vai-specs.png">|

# Setup

[Quick Start](https://azure.github.io/Vision-AI-DevKit-Pages/docs/Get_Started/#configure-your-camera-to-connect-to-azure-as-an-iot-edge-device)

[Stream](https://azure.github.io/Vision-AI-DevKit-Pages/docs/RTSP_stream/)
```
rtsp://<IP address>:8900/live
^ VLC broken?

http://<IP address>:3000/
^ works in browser
```

# Models I've used

AIVisionDevKitGetStartedModule
```
Name - AIVisionDevKitGetStartedModule
Image URI - mcr.microsoft.com/aivision/visionsamplemodule:1.1.0-arm32v7
```

|   |   |
|---|---|
|<img src="img/sonic-jin.png" height="512">|<img src="img/reidoko.png" height="512">|

[VisionSample](https://azure.github.io/Vision-AI-DevKit-Pages/docs/Deploy_Model_IoT_Hub/#)
```
Name - VisionSample
Image URI - mcr.microsoft.com/aivision/visionsamplemodule:latest
```

WebStreamModule
```
Name - WebStreamModule
Image URI - drwedgecr.azurecr.io/webstreammodule:0.0.12-arm32v7
```

# LOGS

https://azure.github.io/Vision-AI-DevKit-Pages/docs/Review_logs/

```
adb shell docker logs -f edgeAgent
After you see a “Start module (your module name)” message, you can use

adb shell docker logs -f <your module name>
to review logs for your module(s).
```

# SSH
commands on board `curl`, `docker`,  `sftp`, `vi`

directories
```
/
    /.
    /..
    /WEBSERVER
    /bin
    /boot
    /bt_firmware
    /build.prop
    /cache
    /data
    /dev
    /dsp
    /etc
    /firmware
        /firmware/image
        /firmware/verinfo
            ver_info.txt
    /home
        /home/{usrname}
        /home/root
        /home/peadbody
    /lib
    /lost+found
    /media
    /mnt
    /persist
    /proc
    /run
    /sbin
    /sdcard -> /mnt/sdcard
    /share
    /sys
    /system
    /systemrw
    /target
    /tmp -> /var/tmp
    /usr
    /var
    /vendor
```


# References
* Microsoft Vision AI Developer kit docs https://aka.ms/VisionAIDocs
* [Gitter](https://gitter.im/Microsoft/vision-ai-developer-kit)
* Join the Microsoft AI Developer Tech Community for support, conversations with other Microsoft Vision AI developers and more at https://aka.ms/VisionAITechComm