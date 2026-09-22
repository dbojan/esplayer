# Esplayer android - open source IPTV player with support for encrypted streams

2026-09-20-19-33-59

Download apk to install on android (click on **esplayer_xx.apk** at the top of the screen, then on the 'arrow pointing down' to download)

#### how to use

- put URLS to your playlist in Documents/esplayer.txt, or put m3u files in Documents folder (on android, on desktop put it next to appimage/exe file)

#### features
- written in kotlin multiplatform + exoplayer
- support for file/channel tagging, buttons on the remote (red, green,yellow, blue), or osd menu
- custom remote buttons settings [more info](android_2.md)
- export import tags and (book)marks from settings screen
- multiple level for logging: off, level 2 only, all.
- restart last played channel on restart
- support for http headers: referrer, user agent, origin

#### encryption
- supports clearkey (single, multiple keys) encrypted dash streams (key icon)
- supports widevine (lock icon)

#### playlists
- support for multiple playlists (either in Documents/esplayer.txt, or m3u/m3u8(.gz) in Documents folder)
- switch to another list using remote keys (rew/ffwd), or two fingers up down swipe, or lists button in channellist screen, or osd menu
- support m3u(8).gz compression of play lists
- custom play speed, and volume levels inside app
- custom font color and shading for subtitles
- support for (pluto) subtitles
- support for recording. recorded files are in Documents/media/recordings. (Use 'Browse' buttons to view them)
- default recording time is 2 hours. you can change it using osd menu
- program does not come with iptv playlists. on the internet you can find: Collection of publicly available IPTV channels

#### playlist types
- support for http, sftp, extinfo playlists, [more info](android_2.md#playlist-examples)
- support for radio channels/audio only files playback with screen off
- custom auto update period for playlists

#### playlist filters
- playlist filter inside app (click on filter button in channellist screen)
- filter url in esplayer.txt, so you can have always fresh favorite list:
  `http://mysite.com/index.html?filtername=one show|another show|third show`
- available filters for urls in esplayer.txt: sort list: `filtersort=yes`  show just group western: `filtergrouptitle=western`  `filterrandom=yes` (randomize list)
- you can group filters using ? or & `http://mysite.com/index.m3u?filtername=sport|news&filtersort=yes`  or with multiple names `?filtername=sport&filtersort=yes`

#### EPG
- support for epg/xml (#EXTM3U url-tvg="https://example.com"), ('remote xml')
- support for mulitple epg/xml lists in url-tvg (#EXTM3U url-tvg="https://example.com/epg1.xml,https://example.com/epg2.xml")
- support for tvg-id: "tvg-id="channel_1.id"
- support for **mutiple ids per one channel**: tvg-id="channel1.id" **tvg-id-multi="channel1_another.id,channel1_some_other_id"** so you can have mulitple epg urls, each using different id for the same channels. tvg-id is checked first, then tvg-id-multi first id, then second id. checking is stopped for a channel on the first match.
- support for gzipped xml epg: https://example.com/epg1.xml.gz
- support for epg/xml next to m3u file ('local xml'), which can also be gzipped
- program also looks up on the device for files: Documents/epg/playlistname.xml(gz) and Documents/epg/all.xml(gz) if files exist. usefull for vod channels, with movies description that hardly ever changes.
- support for tmdb info (put tmdb.key in documents folder. inside just put your api key string, which you can get for free from https://www.themoviedb.org/ )
- you can look up epg guides on https://iptv-org.github.io/ (enter channel name, look for guide icon on the right, looks like calender)

#### media files
- browse local files in Documents/media folder using Browse button.
- support for audio books: mka: opus codec, cover image, chapters - chapter marks in osd, osd menu/goto, seekbar dots; opus, mkb, mp3, mp4  formats
- bookmarks: on pause new bookmark (M in lower left part of screen) is created. To go to previous bookmark, click on m or M
- support for mkv files, and subs inside them. en/eng language is selected by default
- support for srt next to file on say sftp local share, if file is opened through for example cx explorer.
- program also looks for subs in Documents/subs folder if it exists. you can select custom subs using osd (streams menu)
- visualizer: osciloscope and equilizer for audio only files.


| Function | Android | TV remote buttons |
|:--------|:------:|:------:|
|pause|screen tap|ok/space (\|_\|)|
|prev/next channel|swipe up/down|up/down, or channel up/down|
|channel list screen|double tap or clipboard icon on player screen| 'back' on player screen|
|rewind/fast forward|swipe left/right|arrow left/right|
|prev/next list|two fingers swipe up/down|rewind/fast forward|
|osd menu|tap and hold|settings/menu/play/pause|
|epg|osd menu|txt/epg/info|
|settings screen|osd menu, or through channel list screen|aspect ratio|
|exit|x icon on player screen|stop|
|recording | osd menu | rec|
|go to mark|tap on m/M|fav/recall|
|delete mark|osd menu|backspace|
|colors tag|osd menu|color buttons (red, green, yellow, blue)

Documents/esplayer.txt content example: 
```
http://mysite1.com/list1.m3u  
http://mysite2.com/list2.m3u  
```

#### changes

2026-09-20-19-33-59
- fix epg for vod, it does not have to be 'current' if it is just one title per channel

2026-09-13-17-53-39
- fix filtered list name length on save, max 150 + date etc. Max is 250 btw
- fix save filtered list tags: epg url saved, other tags and kodi and vlc opts. note: saved filtered list will always use 'url-tvg=' for ext epg url tag name.
- renamed some internal variables

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

This is basic IPTV player with suport for clearkey and widevine for desktop (linux and windows, and probably mac)

2026-09-20-20-51-32

[linux and windows apps in their folders on google drive](https://drive.google.com/drive/folders/1g1VQJJlJ9GU8jronRg7ZgBzxREPsxAU-?usp=sharing)

- uses electron (unfortunately) + shaka player
- switch channels: use scroll wheel or key up/down, page up/down
- supported clearkey, widevine (although if channels require l1 hardware level, probably wont work)
- supported: epg, tdmb (put tmdb.key with your key inside to Documents, or next to the player), subtitles (pluto).
- put esplayer.txt with links to .m3u/.m3u8, or their gzipped version next to appimage, and start app
- if you use windows 'setup version' copy esplayer.txt or m3u lists to installed .exe file location, probably something like `C:\Users\<username>\AppData\Local\Programs\esplayerdesktop` folder
- you can also drag and drop m3u/m3u/gzipped version on the app window.

- you can use appimage on linux or compile/run from source:

- to install from source, first install nodejs
- then to install needed packages for the app:
```
npm install
```

- to run:
```
npm start
```

to create appimage yourself (delete appimage/binary from dist folder first):
```
npm run dist:linux
```
on windows, to create portable and setup version of app, use:
```
npm run dist:win
```

#### changes 

2026-09-20-20-51-32
- fix for epg (xml/xml.gz) next to dropped/command line argument m3u files.
- fix for vod with expired dates
- added default stream en,eng (with two seconds delay for subtitle check and switch)
- fixed scroll to change channel, so it only works over video/fullscreen part. otherwise it scrolls channellist/log
- switched to https://github.com/castlabs/electron-releases which supports widevine. sintelel widevine test works, but channels requiring hardware level (l1 widevine) might not work.
- run  npm approve-scripts electron, then npm install if npm coplains about new electron. and then npm run
- icons for clearkey/widevine.
  
