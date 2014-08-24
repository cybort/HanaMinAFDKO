Hanazono Mincho AFDKO version
=============================

## Overview

This is an [AFDKO](http://www.adobe.com/devnet/opentype/afdko.html)
version of [Hanazono Mincho](https://fonts.jp/) Fonts, covering *ALL*
CJK Unified and Compatibility Idegraphs up to Extension E (ISO/IEC
10646:2014).

## Description

This prototypical version of Hanazono Mincho is created from
[GlyphWiki](http://glyphwiki.org/) data. This font is created by
AFDKO, and covers entire CJK Unified Ideographs, Compatibility
Ideographs, Kanji and Kana characters, and other CJK Related
ideographs and related characters.

1. CJK Unified Ideograph URO (U+4E00 to U+9FFF)
2. CJK Unified Ideograph Extension-A (U+3400 to U+4DFF)
3. CJK Unified Ideograph Extension-B,C,D,E (U+20000 to U+2CAE1)
4. CJK Compabilitiy Ideographs (U+F900 to U+FAD9)
5. CJK Compabilitiy Ideographs Supplement (U+2F800 to U+2FA1D)
6. Ideographic Variations (Adobe-Japan1 and Hanyo-Denshi)
7. Standard Variations
8. Kana, Kanbun, related punctuations and their vertical forms.
9. Localized glyphs for specific Asian regions.
10. Ligatures, etc.

It consists of two fonts, HanaMinA and HanaMinB, which covers BMP and
SIP respectively. For details of supported features, you can use "spot
-Proof" command in AFDKO toolkit.

### Font Families

There are currently four font families. Among them, AX and BX fonts
are not recommended for casual use.

1. Hanazono Mincho A :: This mainly covers BMP Ideographs.
2. Hanazono Mincho B :: This mainly covers SIP Ideographs.
3. Hanazono Mincho AX :: This is an extended version of Hanazono
   Mincho A, supporting GlyphWiki *uXXXX-itaiji-YYY*, *uXXXX-YY* and
   *kumimoji-XXXX* glyphs by using OpenType GSUB features "trad",
   "ssXX" and "ccmp" features.
4. Hanazono Mincho BX :: This is an extended version of Hanazono
   Mincho B.

## Sample Screenshot

![sample](https://cloud.githubusercontent.com/assets/217020/3786962/fa5527bc-19ef-11e4-83b2-bf14a32602e2.png)

## VS.

### Hanazono Mincho (original version)

Original Hanazono Mincho Font is generated by
[FontForge](http://fontforge.org/), and is TrueType-based. On the
other hand, this font is created by AFDKO, and is CFF-based.

## Supported Systems

Included fonts have been confirmed to work properly with Windows,
Macintosh and Linux.

## Install

Pre-built fonts can be download from
[releases page](http://github.com/cjkvi/HanaMinAFDKO/releases).

This repository provides pre-built data for the font. Glyph data is
provided as compressed
[Type-1](https://partners.adobe.com/public/developer/en/font/T1_SPEC.PDF)
format. This is due to the limitation of GitHub to accept only less
than 100M byte file size. (Uncompressed glyph data will exceed 120M
bytes.) To examine actual glyph data, you can convert the data to
[UFO](http://unifiedfontobject.org/), PDF or
[SVG Font](http://www.w3.org/TR/SVG/fonts.html) format by AFDKO *tx*
command.

To build the fonts, you need to install AFDKO and put their command
directory to $PATH. Suppose $AFDKO is
"/FDK/Tools/SharedData/FDKScripts" directory, run the following
commands to create the fonts. (Please keep in mind that it may take
long time to build the fonts.)

    mergeFonts -cid HanaMinA.cidinfo HanaMinA.raw HanaMinA.cidmap HanaMinA.pfa
    perl $AFDKO/hintcidfont.pl hintparam.txt < HanaMinA.raw > HanaMinA.hinted.raw
    autohint -r -q HanaMinA.hinted.raw
    makeotf -newNameID4 -mf HanaMinA.fmndb -cs 1 -ci HanaMinA.ivs -ch HanaMinA.cmap \
        -f HanaMinA.hinted.raw -ff HanaMinA.features -o HanaMinA.otf

    mergeFonts -cid HanaMinB.cidinfo HanaMinB.raw HanaMinB.cidmap HanaMinB.pfa
    perl $AFDKO/hintcidfont.pl hintparam.txt < HanaMinB.raw > HanaMinB.hinted.raw
    autohint -r -q HanaMinB.hinted.raw
    makeotf -newNameID4 -mf HanaMinB.fmndb -cs 1 -ci HanaMinB.ivs -ch HanaMinB.cmap \
        -f HanaMinB.hinted.raw -ff HanaMinB.features -o HanaMinB.otf

HanaMinAX, HanaMinBX can also be created like the above operations.

## Contribution

These data are created by
[glyphwiki-afdko](http://github.com/kawabata/glyphwiki-afdko) tools.
If you have any problems, please post issues there.

## Licence

License follows [GlyphWiki license](http://glyphwiki.org/license.html).

## Author

- [kawabata](https://github.com/kawabata)
