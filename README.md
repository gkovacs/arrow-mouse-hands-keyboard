# arrow-mouse-hands-keyboard

## About

xkb layout that makes the left hand be arrow keys and the right hand be mouse, when a modifier is held down. Behaves like a standard US English layout otherwise. Tested on ubuntu 16.04

This was designed for the typematrix 2030 usb in colemak mode but can be used in regular qwerty keyboards as well

You will have to check the mouse keys option under keyboard/accessibility settings for the mouse keys to work, otherwise the right hand will behave like a numpad when the modifier is held down

## Mappings

If on a qwerty keyboard, when left win/command is held left hand becomes arrow keys and right hand becomes mouse

If on a colemak keyboard, when alt (either left or right) is held left hand becomes arrow keys and right hand becomes mouse

Described in terms of a qwerty layout, `sdfe` are the arrow keys, `ag` are home/end, `jil,uom.` are the mouse direction buttons, `k` is left click, `h` is middle click, `;` is right click

To hit alt, use right control or right win/command instead

Delete (above backspace on typematrix, fn+backspace on macs) becomes the compose key. Use Shift-Delete to input Delete

Caps lock becomes backspace

If you would like to modify the mappings just edit the file `typematrix`

## Installing

Note this will overwrite `/usr/share/X11/xkb/rules/evdev.xml` so you may want to backup that file or edit that file manually to add the `typematrix` layout. You will need root priviledges to run this command, if you don't have root priviledges I believe `xkbcomp` will work (a pull request documenting this would be appreciated)

```
./install_layout
```

If you would like to have this be the system default, edit `/usr/share/console-setup/KeyboardNames.pl` and add the following under the variants section:

```
    'English (Typematrix)' => 'typematrix',
```

Now edit `/usr/share/doc/keyboard-configuration/xorg.lst` and add the following to the layout section:

```
  typematrix      English (Typematrix)
```

Now run the command `sudo dpkg-reconfigure xkb-data`

Then you can edit `/etc/default/keyboard` and add the line:

```
XKBLAYOUT="typematrix"
```

You can also set the keyboard layout in GNOME as well. Note that this doesn't appear amoung the selections via `sudo dpkg-reconfigure keyboard-configuration`

## Using

```
setxkbmap -layout typematrix
```

If you want to make it permanent you can do so in the keyboard layout configuration page (it is called `typematrix` and should be listed under US English layouts). Note that if you are using fcitx, ibus, or another input method you will have to configure the keyboard layout there as well

## License

MIT

## Credits

By [Geza Kovacs](https://github.com/gkovacs)

I based this off my own [left-handed-keyboard](https://github.com/gkovacs/left-handed-keyboard) which is in turn based off [xkb-halfqwerty](https://github.com/jorissteyn/xkb-halfqwerty)
