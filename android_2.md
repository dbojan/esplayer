
Android version:

### Custom actions for buttons on the remote:

You can set up custom action for buttons on the remote

put file `remote.txt` in the Documents folder, <numerical code>=<screen>.<customaction>

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

