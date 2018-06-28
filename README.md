Raspberry Pi OPC-UA Server
=========

Installation
---------
Download the latest release from https://github.com/kevinherron/pi-server/releases or package it from the latest source:
```
git clone --recurse-submodules <this-repo>
cd pi-server
mvn package
```

Copy that to your Raspberry Pi then unzip it:
```
unzip pi-server-1.1.0.zip 
cd pi-server-1.1.0/
chmod +x bin/pi-server.sh
```

GPIO
---------
GPIO configuration is in `config/gpio-config.json`. Use `config/gpio-config.json.example` as a template.

**IMPORTANT**: The pin numbering scheme is NOT the same as what you see on the Pi. It's based on the pi4j and wiringpi abstract pin numbering scheme. 

- Model A Pins: http://pi4j.com/pins/model-a-rev2.html
- Model B r1 Pins: http://pi4j.com/pins/model-b-rev1.html
- Model B r2 Pins: http://pi4j.com/pins/model-b-rev2.html
- Model B+ Pins: http://pi4j.com/pins/model-b-plus.html
- Model 2B Pins: http://pi4j.com/pins/model-2b-rev1.html
- Model 3B Pins: http://pi4j.com/pins/model-3b-rev1.html

Running PiServer
---------
With the above done and in place, simply invoke `sudo bin/pi-server.sh start` and wait.

You can tail the logs with `tail -f logs/wrapper.log | cut -d '|' -f 4` and watch for a message about binding endpoints to know when it's started.
