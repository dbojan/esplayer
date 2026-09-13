
Android version:

### Custom actions for buttons on the remote:

You can set up custom action for buttons on the remote

One key can only have one function.

put file `remote.txt` in the Documents folder, `<numerical code>=<screen>.<customaction>`

blank lines are ignored, additive-only (a matching line adds a trigger, never removes defaults). 

you can add multiple lines, 1 line per button.

format is `<code>=<screen>.<action>` or 
`<code>=<screen>.blank` (remove action from code)

to see code, enable 'show code' in settins screen, and go back to player screen. press remote button to see its numerical code, like 222

example:

`222=player.osdmenu`

which would open osd menu when you click on button which remote code is 222.

There are 3 screens: `player`, `channellist`, and `settings` and `global` which works on all screens, if not already taken by screen key.

<hr>
`player` screen functions available for remapping:

```
channellist
epg
marks_delete
marks_seek
nextplaylist
osdmenu
prevplaylist
record
refresh
settings
tag_red/tag_green/tag_yellow/tag_blue
```
Not remappable: 
digit0-digit9, nextchannel, prevchannel, playpause

<hr>

`channellist` screen functions available for remapping':

```
back
settings
prevplaylist
nextplaylist
channelup
channeldown
tag_red/tag_green/tag_yellow/tag_blue. 
```

Not remappable: `digit0`-`digit9`.

<hr>

`settings` screen functions available for remapping:
`back only.`

<hr>
'global' screen functions available for remapping':

`exit` (fallback, checked when the current screen's own map misses).

you can also use exit on other screens, but exit currently works on all screens, so it is considered best choice for global screen.

<hr>

### Playlist examples:

note: http and sftp list auto advance to the next item, when current file ends

you can use various file types: mp4, mkv, flv...

Mkv subtitle will be auto played.

For external subtitles, best is to put them in Documents/subs and name them as file, or open file from cx explorer on remote share.

#### sftp

sftp (recommended for local shares only, useful if you already have sftp server.)

esplayer.txt:

`sftp://user:pass@192.168.1.10:22/sftp/media/sftplist.m3u`

sftplist.m3u create using bash/batch script:
```
sftp://user:pass@192.168.1.10:22/sftp/media/series/series01/name.s01e01.mkv
sftp://user:pass@192.168.1.10:22/sftp/media/series/series01/name.s01e02.mkv
```

#### http
files have to be web server (like nginx, start it as sudo nginx, and server on port 80, another port like http://192.168.1.10:8081 should probably work too)

esplayer.txt:

`http://192.168.1.10/httplist.m3u`

httplist.m3u:
```
http://192.168.1.10:22/series/series01/name.s01e01.mkv
http://192.168.1.10:22/series/series01/name.s01e02.mkv
```

#### ext m3u list
same as http list, just each item also has extinfo tag. unlike sftp and http, they dont auto advance to the next item ,when current item finishes playing. you have to click on button down, or swipe down.

files have to be web server, too.

esplayer.txt:

`http://192.168.1.10/extlist.m3u`

extlist.m3u:
```
#EXTM3U
#EXTINF:-1,name.s01e01.mkv
http://192.168.1.10:22/series/series01/name.s01e01.mkv
#EXTINF:-1,name.s01e02.mkv
http://192.168.1.10:22/series/series01/name.s01e02.mkv
```

<hr>

### Examples of m3u files syntax with clearkey and widevine:  

From issues posted to various media players dev pages here: https://github.com/dbojan/encrypted-stream-test

More info here: https://github.com/sharkiller/Reproductor-MPD-M3U8/wiki/M3U-format

#### clearkey 1 key

user agent, referrer and origin are sometimes required, which can be inspected by dev tools/network/*.m3u in firefox/chrome. sometimes they require / at the end (after .com), sometimes they do not.

another way is to use kodi prop for same headers (agent, ref., origin)

```
#EXTINF:-1 tvg-logo="", name1
#EXTVLCOPT:http-user-agent=Android
#EXTVLCOPT:http-referrer=https://www.somesite.com/
#EXTVLCOPT:http-origin=https://www.somesite.com
#KODIPROP:inputstreamaddon=inputstream.adaptive
#KODIPROP:inputstream.adaptive.manifest_type=dash
#KODIPROP:inputstream.adaptive.license_type=clearkey
#KODIPROP:inputstream.adaptive.license_key=a18b6aa739be4c0b114605fcfb5d6b68:b41c3a6f7511b2e3a828d9580124c89d
https://.../index.mpd
```

#### clearkey multple keys, 3 or 5 keys:  

```
#EXTINF:-1 tvg-logo="", name2
#EXTVLCOPT:http-user-agent=Android
#KODIPROP:inputstreamaddon=inputstream.adaptive
#KODIPROP:inputstream.adaptive.manifest_type=dash
#KODIPROP:inputstream.adaptive.license_type=clearkey
#KODIPROP:inputstream.adaptive.license_key={15965a6dbafd12c4af6aca127b271d5b:23dd40b93306de23ec667fb17a61f322,3decf356cc9351019fb1b627b089446d:4f7e516d3253d964e55b5c36f7f65d4a,511e929c12e0596bab59b11452de49a8:6f17d11eb6e069f4165bf48b425f9ea3}
https://.../index.mpd
```


#### widevine:

```
#EXTINF:-1 ,name3
#EXTVLCOPT:http-user-agent=Android
#KODIPROP:inputstream.adaptive.license_type=com.widevine.alpha
#KODIPROP:inputstream.adaptive.license_key=https://....?drm-type=widevine
https://something....
```

Numbers are changed obviously








