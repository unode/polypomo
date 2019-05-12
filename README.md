# polypomo - a polybar pomodoro widget

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
scroll-up = /path/to/polypomo time +1
scroll-down = /path/to/polypomo time -1
```
