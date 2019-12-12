---
layout: post
title: Johnny "Castawine" Up
date: '2019-12-12 08:33:24'
---


It's been about a year since I threw Johnny Castaway up on the web, and I thought it might be time for an update.  

TLDR; http://www.hunterdavis.com/johnnycastawaywine/ is up and running via Wine in JS, but it's slower than the DosBox version.

Seeing as how my previous version of Johnny is running a full version of Windows 3.1, the obvious improvement would be remove the need for a full Windows installation within the page. 

If we were running this in a *nix environment, I'd fire up Wine and run the Johnny castaway install directly, then execute from within Wine.  As we're running in page, I set about searching for an emscript version of Wine.  I found one in the boxwine project https://sourceforge.net/projects/boxedwine/

As with any project of this nature, it took just a bit of wrangling to get it working.  For those looking to roll something similar, I ended up doing the following

1. Install johnny castaway (the original windows 3.1 install) via wine on linux. 
2. Copy the installed files from the ~/home/.wine/drive_c/windows and ~/home/.wine/drive_c/SIERRA folders into the boxedwine.zip root directory file system. 
3. Write a batch file to execute the johnny.scr file with the required /S parameter
4. Zip the johnny.scr and batch file into one zip file
5. Edit the boxwine.html to hard-code parameters and remove mouse input events (as they'll kill the screensaver)

As you can see from the below screenshots, here's the original Javascript->Dosbox (Dos)->Windows->Johnny stack using 20% CPU

And here's the new Javascript->Wine(Windows)->Johnny stack using 25+% CPU

The interesting thing about these projects is that with additional work the Wine version would end up being the fastest, but that is very unlikely to occur.  Not due to purely technical reasons, but due to the relative (un)popularity of the boxwine project compared to the massively popular DosBox project.  

Here's a screenshot for good measure.

See it live:
http://www.hunterdavis.com/johnnycastawayweb/