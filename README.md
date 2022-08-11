# polypomo - a [polybar](https://polybar.github.io/) [pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique) widget

## Usage

Download or clone this repository, then in polybar add:

```
; In your bar configuration add
modules-right = <other-modules> polypomo <other-modules>

; and add a polypomo module
[module/polypomo]
type = custom/script

exec = /path/to/polypomo
tail = true

label = %output%
click-left = /path/to/polypomo toggle
click-right = /path/to/polypomo end
click-middle = /path/to/polypomo lock
scroll-up = /path/to/polypomo time +60
scroll-down = /path/to/polypomo time -60

font-0 = fixed:pixelsize=10;1
font-1 = Noto Emoji:scale=15:antialias=false;0
```

In order to prevent accidental changes to the timer, polypomo starts in `locked` mode.  
Middle click the widget or run `polypomo lock` to toggle locked state.  
You can then scroll-up/down to change time.

If you wish to permanently change the default times start polypomo with `--worktime seconds` and `--breaktime seconds`.

if you want your work sessions to be logged, start polypomo with `--saveto` followed by the path to your database, polypomo will then create a table called `sessions` and store the date, start and stop time of each work session.

There isn't much else in terms of configuration but if the syntax above is confusing please refer to the [polybar configuration wiki page](https://github.com/polybar/polybar/wiki/Configuration).

### Limitations

polypomo is designed to work as a single widget in your polybar.  
Running multiple polypomo instances is not a supported configuration [but some workarounds are possible](https://github.com/unode/polypomo/issues/3#issuecomment-781288256).

### Fonts

In order to display the icons as shown in the screenshots below,
you need to configure a font that includes the Unicode glyphs U+1F345 (🍅) and U+1F3D6 (🏖).
The example above uses the font [Noto Emoji](https://www.google.com/get/noto/help/emoji/).

### About pomodoro technique

While polypomo implements the `active -> break -> active` pattern it doesn't enforce the longer break after a given number of active sprees.  
This is left at the discretion of the user.

## Optional dependencies

polypomo makes use of `notify-send` to send a notification when the timer reaches zero.

## Screenshots

![pomodoro timer](https://raw.githubusercontent.com/unode/polypomo/master/imgs/tomato-timer.png)  
![break timer](https://raw.githubusercontent.com/unode/polypomo/master/imgs/break-timer.png)

## License

polypomo is licensed under the [MIT](https://github.com/unode/polypomo/blob/master/LICENSE) license
