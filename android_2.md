
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





