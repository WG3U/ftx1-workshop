# WG3U FTX-1 Firmware Workshop

**Live page:** https://wg3u.github.io/ftx1-workshop/

**Author: WG3U**

A single-page, browser-only patcher for the Yaesu FTX-1 field head. You load your own original Yaesu **MAIN 01-13** and **DISPLAY 01-10** firmware files. The page checks them, applies the WG3U extended build, and gives you a ZIP ready to copy to the radio's microSD card.

## Credit: SQ9PD

This build includes **SQ9PD's FTX-1 modification** (soft-key pages, clock, MEM DISPLAY, SWR SCAN, shortcuts, APRS actions and his firmware fixes), used with his permission. All credit for that part goes to SQ9PD:

- https://ftx-1-mod.sq9pd.pl/
- https://github.com/sq9pd/Yaesu-FTX-1-mod

WG3U's additions are the extended TX ranges, 10 W on the internal battery, the 50–4000 Hz SSB/AM TX filters, EQ3 up to 3700 Hz, the wide-SSB passband centre, the AM speech processor, the D-MODE long-press fix, and the scope and waterfall changes. Please report problems with those to WG3U, not SQ9PD.

## Privacy and what this repo contains

- Everything runs in your browser. Your files are never uploaded, and the page's Content-Security-Policy blocks all network requests. There are no analytics and no external libraries.
- This repository does **not** host any Yaesu firmware, original or patched. The page carries only the changed bytes (each with the original value it expects) plus SQ9PD's own added code block, compressed. You must supply Yaesu's files yourself.
- The output is accepted only if its SHA-256 exactly matches the reference build below. Otherwise the download stays disabled.

## Expected hashes (SHA-256)

| File | Original (input) | Patched (output) | Output tag CRC |
|---|---|---|---|
| `FTX-1_MAIN_V0113.SFL` | `de02ce415b37ca6621ed0bac2f8e7bd63d45f3022a62868598950502ed033f5c` | `8bb5ca1da35b0fba29aab5de959936858a151e38fb818dc271f13e794e20c59f` | `4C0EED48` |
| `FTX-1_DISPLAY_V0110.SFL` | `962fda27ae2f0a0deedb039b868a545ef0f6736b686c266e19f231dbe3973bba` | `ad976746852223dbc989b559e2fc6e95c4a4333540ce47b7054e733f77f260fa` | `BA528420` |

## Warnings

This is unofficial firmware, not made, approved or supported by Yaesu, and comes with no warranty. Back up your memories and settings, and keep your original files. The build widens the transmit ranges: transmit only where your licence allows. To go back to stock, flash Yaesu's original MAIN 01-13 and DISPLAY 01-10, then do a factory reset.

Yaesu and FTX-1 are trademarks of Yaesu Musen Co., Ltd. Not affiliated with Yaesu or SQ9PD.
