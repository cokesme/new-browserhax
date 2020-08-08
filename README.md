# new-browserhax

## Thanks 
- Big thanks to @ChampionLeake for the bug tip!
- The devs who developed JsTypeHax for the WiiU https://github.com/WiiUTest/JsTypeHax . This sploit is loosely modeled after it.
- Yellows8 for the hbmenu loader code: https://github.com/yellows8/3ds_browserhax_common

## Intro

This is a new homebrew menu loading userland exploit for the new3ds browser, Skater. 

## What's needed

A new3ds (or new2ds) on firmwares:<br>
```
11.9.0-42 -> 11.13.0-45 for USA or JAPAN
11.10.0-43 -> 11.13.0-45 for EUROPE
```
Note: The last number on the firmware version matters. If you updated from a cartridge to your current firmware, you will need to update to latest firmware as your browser would have been erased by the cart update.

## Directions 

1) In the release folder, find your region (USA, EUROPE, JAPAN) and take the two files *inside* that folder and put them on the root of your sd card. Do not copy the entire folder over.
2) Place the homebrew launcher boot.3dsx from [here](https://github.com/fincs/new-hbmenu/releases/tag/v2.2.0) also on the root of your sd card.
3) With wifi on and working, scan [this QR](http://api.qrserver.com/v1/create-qr-code/?color=000000&bgcolor=FFFFFF&data=https%3A%2F%2Fzoogie.github.io%2Fweb%2Fnbhax&qzone=1&margin=0&size=400x400&ecc=L) after pressing L+R should buttons together and tapping the QR button on the bottom screen. The link to the sploit page is https://zoogie.github.io/web/nbhax if you want to type it in manually and/or bookmark it.
4) The exploit should then load homebrew menu. Make sure to add homebrews to the sdmc:/3ds folder first in order to have something to run. See other guides online about what you can do with homebrew.

## Exploit details

This is the same Use-After-Free bug exploited in the WiiU version, with some changes. The input.type="image" -> "radio" is changed to input.type="image" -> "hidden" in this one to achieve compatibility, for instance.

## Troubleshooting

- Problem: The 3ds freezes on a yellow screen.<br>
Solution: Try again. Boot rate is about 75-80%. This has always been an issue with *hax homebrew and not specific to this implementation.

- Problem: The 3ds freezes on some other color screen or "An error has occured" prompt shows up.<br>
Solution: Make sure you have *all* the correct files. Check your region is correct.<br>
At minimum, make sure to have those 3 files in those same locations.<br>
```
sdmc:/arm11code.bin
sdmc:/browserhax_hblauncher_ropbin_payload.bin
sdmc:/boot.3dsx
```

## FAQ
Q: Will you support old3ds, old2ds?<br>
A: I tried for a bit getting this to work but had no success. Can't even get the bug to crash old3ds. Might try again but the odds of old3ds support are slim at best.

Q: Can I install [unSAFE_MODE](https://github.com/zoogie/unSAFE_MODE) with this to get cfw?<br>
A: Absolutely, be my guest : ) You can boot slotTool.3dsx and install the hacked wifi slots, then run the unSAFE_MODE exploit. No explicit directions will be given for that here, but guides should pop up soon with directions.

Q: Where did this browser exploit come from originally?<br>
A: CVE-2013-2857 https://bugs.chromium.org/p/chromium/issues/detail?id=240124 . It was ported to the WiiU a couple of years ago and I think it's still the main userland entrypoint for that homebrew scene.

Q: Will this exploit be fixed in a firmware update?<br>
A: Don't know, but it's definitely possible. N has never fixed one of my exploits but they've always been proactive about fixing browser exploits. I give it 50/50 odds.

