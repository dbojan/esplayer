# Esplayer android - open source IPTV player with support for encrypted streams

2026-09-07-08-42-53

Download apk from esplayer_android folder to install on android

- supports clearkey 1 and multiple keys encrypted dash streams
- written in kotlin multiplatform + exoplayer

**how to use**

- tap: pause, show playlist, and icons for: prev channel, channels list, settings, next channel
- up on remote/swipe from up to down: prev channel
- down on remote/swipe from down to up/dpad down: next channel
- left on remote/swipe from left to right: show channel list
- right on remote/swipe from right to left: show settings

- you can put URLS to your playlist in Documents/esplayer.txt, so you do not have to type them in manually: 

Documents/esplayer.txt content: 
```
http://mysite1.com/list1.m3u  
http://mysite2.com/list2.m3u  
```

- you can search playlist, and save the result to new playlist
- you can put local playlists files in Documents folder, and esplayer will add them. 
(this is also used for saving search to new playlist)  

local_playlist_example.m3u:
```
#EXTM3U
#EXTINF:-1,stream 1
http://website.com/list.m3u
#EXTINF:-1,stream 2
http://website2/list.m3u
```
- you can add playlist(s): http://www.something.../play.m3u from settings screen

- from the channellist you can switch playlists or update them
- added support for subtitles, more settings.

- when you tap on screen bookmark is added, (letter m or M (New) in bottom left). to go to bookmark tap on that letter

- sftp, http lists are also supported
- list.xml(.gz) near list.m3u(.gz) also supported (local xml), for epg, just make sure they are accessible, like on local web server

**ver**

2026-09-07-08-42-53
fixes and new features

2026-03-28-1
- working on improving android tv ui.

2026-03-22-1  
- added support for subtitles
- more settings
- remote support (to test)

2026-03-17-1
- first version

<hr>

# Esplayer desktop - open source IPTV player with support for encrypted streams

2026-09-07-08-42-53

[windows and linux programs on google drive](https://drive.google.com/drive/folders/1g1VQJJlJ9GU8jronRg7ZgBzxREPsxAU-?usp=sharing)

- uses electron (unfortunately) + shaka player
- source code is in esplayer_desktop folder, here in github page.
- use scroll wheel or key up/down, page up/down to switch channels
- supported clearkey, widevine (although if channels require l1 hardware level, probably wont work)
- supported: epg, subtitles (pluto).
- put esplayer.txt with links to .m3u/.m3u8, or their gzipped version next to appimage, and start app
- if you use windows 'setup version' copy esplayer.txt or m3u lists to installed .exe file location, probably something like `C:\Users\<username>\AppData\Local\Programs\esplayerdesktop` folder
- you can also drag and drop m3u/m3u/gzipped version on the app window.

- you can use appimage on linux or compile/run from source:

- to install from source:
install nodejs, then:
```
npm install
npm start
```

to create appimage yourself (delete dist folder first):
```
npm run dist:linux
```

  
