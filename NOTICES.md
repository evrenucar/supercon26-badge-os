# Notices and corresponding source

This is the evrenucar fork's explicitly selected signed app channel, not an upstream default signing authority. Original per-file notices remain authoritative.

The Badge OS project and these adapters use the repository GPL-2.0 license, retained in `licenses/GPL-2.0.txt` and each package's LICENSE. Exact project source and documented builders: https://github.com/evrenucar/supercon26-badge-os/tree/e901877daa4ba6caaa987096df67fec0e6f41329 . Each package NOTICE links to its corresponding source. Doom also uses `components/doomgeneric` and the original `apps/doom/doom.c` controls from that source tree; no Doom IWAD or user save data is distributed here.

Codex Board retains ml-sudocode / upstream PR #5 attribution. Hackaday retains Badge OS/Hackaday source attribution. The QR implementation carries Project Nayuki's MIT copyright/license notice in its C/H headers, retained in `licenses/qrcodegen-MIT.txt`; the source's accompanying vendor LICENSE is also retained verbatim as `licenses/upstream-vendor-LICENSE.txt`. The public-domain font8x8 attribution is retained in `licenses/font8x8-Public-Domain.txt`.

Where linked, GCC runtime support and picolibc/newlib code carry their upstream notices. Copies are in `licenses/GCC-Runtime-Exception.txt`, `licenses/GCC-GPL-3.0.txt`, `licenses/picolibc-NOTICES.txt` and `licenses/newlib-NOTICES.txt`. The pinned ESP32-S3 compiler is Espressif esp-15.2.0_20251204 (GCC 15.2.0); toolchain sources/release are at https://github.com/espressif/crosstool-NG/releases/tag/esp-15.2.0_20251204 .

Video's clip is the exact unchanged stock `apps/video/rickroll.vid` shipped in the upstream Badge OS repository; upstream artifact: https://github.com/yigitabi5444/supercon26-badge-os/blob/b43e45087abb0604263d3edc84d0c0fcdd47f6dc/apps/video/rickroll.vid . Its converter is `apps/video/tools/make_video.py`. The 819646-byte clip SHA256 is c804c2cbb5df2830f17a814d65be2fab229b0825d6e89d089a64551d5d6d6df7. This preserves upstream stock-video attribution and does not label the underlying music/footage as GPL software.

Doom1.0.1 corresponding source, including the relative-filename builder and unchanged engine/controls: https://github.com/evrenucar/supercon26-badge-os/tree/09fac423d2943334a09a2731310f530d284d0a3f . All other package source references remain pinned to e901877daa4ba6caaa987096df67fec0e6f41329.
