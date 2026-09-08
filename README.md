# Esplayer android - open source IPTV player with support for encrypted streams

2026-09-07-08-42-53

Download apk to install on android

**how to use**

- put URLS to your playlist in Documents/esplayer.txt, or put m3u files in Documents folder (on android, on desktop put it next to appimage/exe file)

### features
- written in kotlin multiplatform + exoplayer (android)
- supports clearkey (single, multiple keys) encrypted dash streams
- supports widevine
- supports radio channels with screen off
- support for http,sftp,extinfo playlists
- bookmarks (on pause new bookmark (M in lower left part of screen) is created. To go to previous bookmark, click on m)
- custom auto update time for list
- support for epg/xml (#EXTM3U url-tvg="https://example.com"), ('remote xml')
- support for epg/xml next to m3u file ('local xml')
- support for tmdb info (put tmdb.key in documents folder. inside just put your api key from https://www.themoviedb.org/ )
- browse Documents/media folder using Browse button.
- custom remote buttons settings more info: [android_2](android_2.md)
- support for (pluto) subtitles
- custom speed, and volume inside app
- custom font color and shading for subtitles
- support m3u(8).gz and xml.gz compression
- playlist filter inside app
- filter url in esplayer.txt, so you can have always fresh favorite list:
  `http://mysite.com/index.html?filtername=one show|another show|third show`
- more filters for urls in esplayer.txt: sort list: `filtersort=yes`  show just group western: `filtergrouptitle=western`  `filterrandom=yes` (randomize list)
- you can group filters using ? or & `?filtername=sport|news&filtersort=yes`  or with multiple names `?filtername=sport&filtersort=yes`
- support for audio books: mka: opus codec, cover image, chapters - chapter marks in osd, osd menu/goto, seekbar dots ; opus, mkb, mp3, mp4  formats
- support for file/chanel tags, using channellist/osd menu, or remote color buttons (red, green,yellow, blue)
- export import tags and (book)marks from settings screen
- multiple level for logging: off, level 2 only, all.


| Function | Android | TV remote buttons |
|:--------|:------:|:------:|
|pause|screen tap|ok|
|prev/next channel|swipe up/down|up/down, or channel up/down|
|channel list screen|double tap or clipboard icon on player screen| 'back' on player screen|
|rewind/fast forward|swipe left/right|arrow left/right|
|prev/next list|two fingers swipe up/down|rewind/fast forward|
|osd menu|tap and hold|settings/menu/play/pause|
|epg|osd menu|txt/epg|
|settings screen|osd menu, or through channel list screen|aspect ratio|
|exit|x icon on player screen|stop|
|recording | osd menu | rec|
|go to mark|tap on m/M|fav/recall|
|delete mark|osd menu|backspace|
|tag colors|osd menu|color buttons (red, green, yellow, blue)

Documents/esplayer.txt content example: 
```
http://mysite1.com/list1.m3u  
http://mysite2.com/list2.m3u  
```


**ver**

2026-09-07-08-42-53
- fixes and new features

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
- switch channels: use scroll wheel or key up/down, page up/down
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

  
