## Discord-Waitingroom-Bot

A basic, easy to setup Waiting Room Bot to play an audiofile on your pc / a stream!

## Installation | How to use the Bot

 **1.** Install [node.js v12](https://nodejs.org/api/cli.html#cli_unhandled_rejections_mode) or higher

 **2.** Install [ffmpeg@latest](https://ffmpeg.org) 

 **3.** Download this repo and unzip it    |    or git clone it
 
 **4.** Install all of the packages with **`npm install`**     |  the packages are   **`npm install node.js discord.js @discordjs/opus`**
 
 **5.** start the bot with **`node index.js`**

## Usage - config.json

```javascript
{
  "token": "",        // Fill in your Bot token
  "voicechannel": "", // Voice Channel Id for your Bot Channel
  "guildid": ""       // Guild Id of your Server
}
```

## Usage - index.js  | function radioexecute()  | Line 26-34

```javascript
async function radioexecuteadmin() {
    const voiceChannel = client.guilds.cache.get(config.guildid).channels.cache.get(config.voicechannel); //define the Voice Channel
    await voiceChannel.leave(); // leave the channel
    await delay(300); // wait 300ms to provent a bug
    var connection = await voiceChannel.join();//join the channel and
    await connection.voice.setSelfDeaf(true); await connection.voice.setDeaf(true); //selfdeaf
    const dispatcher = connection.play('./audiofile.mp3'); //You can replace the './audiofile.mp3' with any sort of Radio stream for example: 'https://streams.ilovemusic.de/iloveradio17.mp3'
    dispatcher.on("end", end => { radioexecuteadmin() });
}
```

## **NOTE:**

*Make sure that you have install [FFmpeg](https://ffmpeg.org), and added it to Systemenvironment variables (PATH)*

*If you are having errors/problems with starting delete the package.json file and do, before you install the packages `npm init`*

## SUPPORT ME

<div align="center">
            <a href="https://www.buymeacoffee.com/navaneethkm" target="_blank" style="display: inline-block;">
                <img
                    src="https://img.shields.io/badge/Donate-Buy%20Me%20A%20Coffee-orange.svg?style=flat-square" 
                    align="center"
                />
            </a></div>
