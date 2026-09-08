# Esplayer android - open source IPTV player with support for encrypted streams

2026-09-07-08-42-53

Download apk to install on android

**how to use**

- put URLS to your playlist in Documents/esplayer.txt, or put m3u files in Documents folder (on android, on desktop put it next to appimage/exe file)
- tap: pause
- up on remote/swipe from up to down: prev channel
- down on remote/swipe from down to up/dpad down: next channel
- left on remote/swipe from left to right: rewind
- right on remote/swipe from right to left: fast forward
- double tap: channel list. 


### features
- written in kotlin multiplatform + exoplayer (android)
- supports clearkey (single, multiple keys) encrypted dash streams
- supports widevine
- supports radio channels with screen off
- support for http,sftp,extinfo playlists
- recording
- bookmarks (on pause new bookmark (M in lower left part of screen) is created. To go to previous bookmark, click on m)
- custom auto update time for list
- support for remote epg/xml (#EXTM3U url-tvg="https://example.com")
- support for epg/xml next to m3u file
- support for tmdb info (put tmdb.key in documents folder. inside just put your api key from https://www.themoviedb.org/ )
- browse Documents/media folder using Browse button.
- use double tap or on remote: settings/play/pause key to go to channellist
- use remote button 'aspect ratio' to go to settings screen directly
- custom remote buttons settings ---
- support for (pluto) subtitles
- custom speed, and volume inside app
- custom font color and shading for subtitles
- support m3u(8).gz and xml.gz compression
- playlist filter inside app
- filter url in esplayer.txt, so you can have always fresh favorite list:
  `http://mysite.com/index.html?filtername=one show|another show|third show`
- more filters: sort list: `filtersort=yes`  show just group western: `filtergrouptitle=western`  `filterrandom=yes` (randomize list)
- you can group filters using ? or & `?filtername=sport|news&filtersort=yes`  or with multiple names `?filtername=sport&filtersort=yes`
- support for audio books: mka: opus codec, cover image, chapters - chapter marks in osd, osd menu/goto, seekbar dots ; opus, mkb, mp3, mp4  formats
- support for file/chanel tags, using channellist/osd menu, or remote color buttons (red, green,yellow, blue)
- export import tags and (book)marks from settings screen
- multiple level for loggings off, level 2 only, all.
- 

Documents/esplayer.txt content: 
```
http://mysite1.com/list1.m3u  
http://mysite2.com/list2.m3u  
```


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
on windows, to create portable and setup version of app, use:
```
npm run dist:win
```

  
