---
---
# Installing node-webrtc on a Raspberry Pi with npm
I needed to install node-webrtc on a Rasbperry Pi running Raspbian Strech. I found that the following Raspbian packages needed to be added with:
```
    sudo apt-get install libpixman-1-dev libcairo-5c0 libcairo2-dev libpango1.0-devlibjpeg-dev
    npm install --save wrtc
```

Project page: <https://github.com/node-webrtc/node-webrtc>

This was accomplished with:
* node version 10.15.2
* npm version 6.4.1
* Raspbian Strech
