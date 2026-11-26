# WG3U FTX-1 Firmware Workshop

**Live page:** https://wg3u.github.io/ftx1-workshop/

**Author: WG3U**

A single-page, browser-only patcher for the Yaesu FTX-1 field head. You load your own original Yaesu **MAIN 01-13** and **DISPLAY 01-10** firmware files. The page checks them, applies the latest WG3U extended build (v11, 25 November 2026), and gives you the two finished `.SFL` files to copy into the `FTX-1` folder on the radio's microSD card. A ZIP bundle with a README is offered as an option.

## Credit: SQ9PD

This build includes **SQ9PD's FTX-1 modification** (soft-key pages, clock, MEM DISPLAY, SWR SCAN, shortcuts, APRS actions and his firmware fixes), used with his permission. All credit for that part goes to SQ9PD:

- https://ftx-1-mod.sq9pd.pl/
- https://github.com/sq9pd/Yaesu-FTX-1-mod

WG3U's additions are the extended TX ranges, 10 W on the internal battery, the 50–4000 Hz SSB/AM TX filters, EQ3 up to 3700 Hz, the wide-SSB passband centre, the AM speech processor, the D-MODE long-press fix, and the scope and waterfall changes. Please report problems with those to WG3U, not SQ9PD.

## Privacy and what this repo contains

- Everything runs in your browser. Your firmware files never leave your computer. There are no analytics, no cookies and no external libraries.
- **Anonymous build counter:** when the page loads, it reads the current MAIN and DISPLAY build totals from `abacus.jasoncameron.dev` (`/get/wg3u-ftx1-workshop/main` and `/display`, falling back to `/info/`) and shows them as a small BUILDS readout. After a build passes its SHA-256 check, and only then, it sends one bare GET to `https://abacus.jasoncameron.dev/hit/wg3u-ftx1-workshop/main` (or `/display`) to add 1. It carries no file data, hashes, filenames, cookies or referrer. Like any web request, it exposes your IP address to that service. If the counter is blocked or down, the readout stays hidden and the patcher works the same. The Content-Security-Policy allows that one host and blocks every other network request.
- This repository does **not** host any Yaesu firmware, original or patched. The page carries only the changed bytes (each with the original value it expects) plus the added code (new MAIN S-records and a DISPLAY appendix), compressed. You must supply Yaesu's files yourself.
- The output is accepted only if its SHA-256 exactly matches the reference build below. Otherwise the download stays disabled.

## Expected hashes (SHA-256), v11

The page delivers firmware only through the patcher; it offers no direct `.SFL` downloads.

| File | Original (input) | Patched (output) | Output tag CRC |
|---|---|---|---|
| `FTX-1_MAIN_V0113.SFL` | `de02ce415b37ca6621ed0bac2f8e7bd63d45f3022a62868598950502ed033f5c` | `83969bd6ed010108fdf72049d70065b2e0a616d62fa648af2bd18d91969db324` | `CDFD6543` |
| `FTX-1_DISPLAY_V0110.SFL` | `962fda27ae2f0a0deedb039b868a545ef0f6736b686c266e19f231dbe3973bba` | `b0ddec36f002a9d86d7971716c850ff5ae93bbb9f5778f444a35d5e583c94e39` | `BC14B8E3` |

## Warnings

This is unofficial firmware, not made, approved or supported by Yaesu, and comes with no warranty. Back up your memories and settings, and keep your original files. The build widens the transmit ranges: transmit only where your licence allows. To go back to stock, flash Yaesu's original MAIN 01-13 and DISPLAY 01-10, then do a factory reset.

Yaesu and FTX-1 are trademarks of Yaesu Musen Co., Ltd. Not affiliated with Yaesu or SQ9PD.
