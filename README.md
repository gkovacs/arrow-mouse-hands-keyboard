# arrow-mouse-hands-keyboard

## About

xkb layout that makes the left hand be arrow keys and the right hand be mouse, when a modifier is held down. Behaves like a standard US English layout otherwise. Tested on ubuntu 16.04

This was designed for the typematrix 2030 usb in colemak mode but can be used in regular qwerty keyboards as well

You will have to check the mouse keys option under keyboard/accessibility settings for the mouse keys to work, otherwise the right hand will behave like a numpad when the modifier is held down

## Mappings

If on a qwerty keyboard, when left win/command is held left hand becomes arrow keys and right hand becomes mouse

If on a colemak keyboard, when left alt is held left hand becomes arrow keys and right hand becomes mouse

Described in terms of a qwerty layout, `asdf` are the arrow keys, `wg` are home/end, `jil,uom.` are the mouse direction buttons, `k` is left click, `h` is middle click, `;` is right click

To hit alt, use right control or right win/command instead

Right alt becomes the compose key

Caps lock becomes backspace

If you would like to modify the mappings just edit the file `typematrix`

## Installing

Note this will overwrite `evdev.xml` so you may want to edit that file manually to add the `typematrix` layout. You will need root priviledges to run this command, if you don't have root priviledges I believe `xkbcomp` will work (a pull request documenting this would be appreciated)

```
./install_layout
```

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
