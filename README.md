# vertical-bezels-4-3-batocera
Vertical arcade game overlays created for Batocera

What is this?
I’ve built a little Bartop for myself, on a budget. Thus it uses an old 1280x1080 display (5:4) instead of the currently “normal” 16:9 displays. It runs Batocera.

While something close to 4:3 (in most cases 1024x768) is pretty cool, especially for vertically oriented games, I wanted to use bezels for these vertical games. Without any “CRT-effect” built in them. And those 4:3 (or in my case 5:4) - Bezels are somewhat hard to find.

So really, what is this?
Bezels from various sources for 4:3-Monitors for vertical games only. Without any “CRT-effect”. The PNG-files as well as INFO-Files which Batocera needs.

The INFO-Files were generated automatically using https://github.com/TvsIan/bezeltools. I’ve reviewed most of the games, but there may still be some errors concerning the viewport. Please report any error (as well as how you fixed it).

Concerning the 1280x1024 – versions I resized the bezels I had using https://www.highmotionsoftware.com/download-center/imbatch. I used 1600x1200 versions as a basis, if I had access to them. And created the INFOs automatically, again.

My sources are mainly https://github.com/svera/vertical-bezels-4-3, https://retropie.org.uk/forum/topic/19896/arcade-overlays-4-3-1600x1200 and also https://www.screenscraper.fr/. You’ll find all bezels collected here on screenscraper.fr as 1024x768 files (I uploaded the missing ones), but spread across all kind of countries / regions, which makes it difficult to collect them using simply scraping.


How do I get this to work?
Assuming you are using Batocera v35 or above (I simply haven’t tested these with older versions):
1. Create a folder “XXXXXX” (or “YYYYY” if using the samba network share).
2. If you want these bezels to work in fbneo, too, create a second folder “ZZZZZ”.
3. Copy the desired PNGs as well as INFOs into these folder(s).
4. Edit
- - - - - - - - - -
usr/lib/python3.11/site-packages/configgen/generators/libretro/libretroConfig.py
- - - - - - - - - -
(or //usr/lib/python3.10/site-packages/configgen/generators/libretro/libretroConfig.py when using v35 for example)
using ssh and nano. You’re searching for the line
- - - - - - - - - -
if gameRatio < 1.6 and gunsBordersSize is None: # let's use bezels only for 16:10, 5:3, 16:9 and wider aspect ratios ; don't skip if gun borders are needed
- - - - - - - - - -
(line 1219 on v41 or line 905 on v35, for example)
Change the “1.6” to “1” to activate bezels for non-16:9 – displays.
5. In Batocera itself, select “Decorations” → “Mybezel_43”
6. Especially when using 1280x1024- Bezels, select “Aspect Ratio” → “Custom” for the games using these bezels. Yes, this distorts the games a little bit, but I didn’t want so crop all those bezels.

You should be ready to go, enjoy!
