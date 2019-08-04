<p align="center"><img src="img/pupadoo.svg"></p>

|   |   |
|---|---|
|<img src="img/vai-ports.png">|<img src="img/vai-specs.png">|

# Setup

[Quick Start](https://azure.github.io/Vision-AI-DevKit-Pages/docs/Get_Started/#configure-your-camera-to-connect-to-azure-as-an-iot-edge-device) then [Custom Vision Service](https://azure.github.io/Vision-AI-DevKit-Pages/docs/Tutorial-HOL_Using_the_VisionSample/#). [Take pictures](https://azure.github.io/Vision-AI-DevKit-Pages/docs/train/#take-pictures-with-the-camera) with the camera.

Managing the device with the Android Debug Bridge, `./adb.exe devices` to confirm device is connected to your machine, `./adb.exe shell ifconfig wlan0` to view the devices ip.

[Stream](https://azure.github.io/Vision-AI-DevKit-Pages/docs/RTSP_stream/) only one per browser session
```
rtsp://<IP address>:8900/live
^ VLC broken?

http://<IP address>:3000/
^ works in browser
```

# Models I've used

MyMXCHIP Model

AIVisionDevKitGetStartedModule
```
Name - AIVisionDevKitGetStartedModule
Image URI - mcr.microsoft.com/aivision/visionsamplemodule:1.1.0-arm32v7
```
use `visionsamplemodule:latest` for latest

Container create default options

```
{
  "HostConfig": {
    "Binds": [
      "/data/misc/camera:/app/vam_model_folder",
      "/run/systemd:/run/systemd"
    ]
  }
}
```

Default twin's desired properties
```
{
  "properties.desired": {
    "ModelZipUrl": "<blob SAS URL>",
    "TimeBetweenMessagesInSeconds": "12",
    "ObjectsOfInterest": "ALL",
    "ShowVideoOverlay": "true",
    "Bitrate": "1.5Mbps",
    "Resolution": "1080P",
    "VideoOverlayConfig": "inference",
    "FrameRate": "30",
    "FreqToSendMsg":12,
    "HdmiDisplayActive": "true",
    "VideoAnalyticsEnabled": "true",
    "ShowVideoPreview": "true",
    "Codec": "AVC/H.264"
  }
}
```

|   |   |
|---|---|
|<img src="img/sonic-jin.png" height="512">|<img src="img/reidoko.png" height="512">|


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

# References
* [Custom Model](https://www.customvision.ai/)
* [Custom Model Guide](https://azure.github.io/Vision-AI-DevKit-Pages/docs/Tutorial-HOL_Using_the_VisionSample/)
* [Custom Vision Service](https://www.customvision.ai/)
* [Gitter](https://gitter.im/Microsoft/vision-ai-developer-kit)
* Join the Microsoft AI Developer Tech Community for support, conversations with other Microsoft Vision AI developers and more at https://aka.ms/VisionAITechComm
* Microsoft Vision AI Developer kit docs https://aka.ms/VisionAIDocs
* Samples and more in [Microsoft Vision AI repo](https://github.com/Microsoft/vision-ai-developer-kit)
