# MCFORT9669 v11.0 — firmware routes

The main page detects the PS4 firmware from the console User-Agent. Unsupported
versions stop without starting a kernel chain. Existing 13.02/13.04/13.50/13.52
and 14.00 modules remain unchanged.

| Firmware | Local module | Source |
| --- | --- | --- |
| 5.05, 6.70–6.72, 7.00–10.71, 11.02 | webkitty/ | ArabPixel/WebKitty, AGPL-3.0-or-later |
| 11.00, 11.50, 12.00, 12.02 | rawgame4/ Lapse | rawgame4/rawgame4.github.io, MIT port plus third-party components |
| 12.50, 12.52, 13.00 | rawgame4/ Poops | rawgame4/rawgame4.github.io |
| 13.02, 13.04, 13.50, 13.52 | engine/ | Original host / raw13g |
| 14.00 | afterglow/ | well0nez/afterglow-web, AGPL-3.0-or-later |

Firmware support is based on each upstream project's published support table;
the new routes have not been verified on hardware in this package. 10.01 in
RawGame4 is explicitly untested, so it routes to WebKitty. The early WebKitty
module maintains its own firmware-specific offline cache after opening. Root
statistics do not count launches in separate modules because their success
cannot be confirmed by the root page. Keep upstream license and attribution
files when redistributing this archive.

Upstreams:
https://github.com/ArabPixel/WebKitty
https://github.com/rawgame4/rawgame4.github.io
https://github.com/raw13g/raw13g.github.io
https://github.com/well0nez/afterglow-web

## Error reports in v11.1

The shared error-report.js shows firmware, module, last stage, and error text.
The last active stage is stored on the console and presented on the next main-page
visit if the browser or console exits before a result. This is a diagnostic clue,
not a kernel crash log or proof of the crash cause. The RawGame4 launch pages
consume a one-time session token to prevent a restored page rerunning the exploit.

