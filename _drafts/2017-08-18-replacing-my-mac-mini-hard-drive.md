---
layout: post
title:  Replacing My Mac mini Hard Drive
bigimg: /img/mac-mini-press.jpg
tags: [macOS, repair]
---
Before we went on vacation, our late-2012 Mac mini gave me an error as I was trying to complete a backup using [Carbon Copy Cloner][1], a program I use to duplicate both the Mac's hard drive as well as our external media drive that contains our Photos and iTunes libraries. 

The hard drive in the computer was original and was definitely in need of replacement based on how slow the computer had gotten over the years. This error was just the excuse I needed to upgrade it to an SSD. Since I had multiple backups[^1], I wasn't worried about data loss, so I shut the machine down and decided to deal with it when we returned from vacation.

I was inspired by [Jason Snell][2] and [Katie Floyd's][3] attempts at this upgrade, so this week I ordered an [SSD][4] from Amazon along with a [few specific tools][5] that I needed from [iFixit][6]. If you've never used iFixit, they are a tremendous resource for fixing a wide variety devices. 

Last night, after the kids went to bed, I sat down at the kitchen table with my Mac, iPad to follow the instructions, and tools and dove in.

{: .center}
![Ready to Go]({{ site.url }}/img/mac-mini-hd-replacement.jpg)

iFixit's guides walk you through the repair step-by-step, with clear, concise instructions. They also include notes from other people who've attempted the repair which I found incredibly helpful as I was trying to re-seat the antenna plate at the end and it just wouldn't line up correctly. 

{% include image.html
            img="img/ifixit-mac-mini-hd-repair.png"
            title="iFixit Guide"
            caption="iFixit" %}

All told, the repair took me about 40 minutes from start to finish. I took the machine up to my desk where I booted it up and formatted the new SSD using [macOS Recovery][7]. I was a little surprised at first to see the old [OS X Mountain Lion][8] logo staring back at me. 

{: .center}
![Mountain Lion]({{ site.url }}/img/osx-mountain-lion-install.jpg)

I guess that was the version that was out at the time the computer was released back in 2012. Since that time, Apple has moved on from the great cats onto iconic California locations: Mavericks, Yosemite, El Capitan, and Sierra (and soon High Sierra).

The first thing that hit me when I started opening up menus and programs was how _fast_ everything was! I knew my system was slow, and I'm pretty sure my work machine has an SSD, but after working on this Mac for the last five years, it truly felt like a brand new machine.

I spent a couple of additional hours last night updating from Mountain Lion to Sierra, and signing into iCloud, Dropbox, and 1Password. Then I went to bed while everything downloaded from the cloud. This morning I loaded up some of the remaining pieces of software and re-enabled iCloud Photo Library which has spent the rest of the day re-syncing with the cloud database.

Was it worth it? You bet. My only regret is that I didn't take advantage of the fact that my machine has an empty space above the hard drive (or below as you're taking it apart) where a second drive can be placed. I also didn't upgrade the RAM, although that's a really easy fix on the Mac mini.

[^1]:	I back up my computer three ways. First, I have a Time Machine backup running continuously backing up both the Mac mini as well as the external media drive. I do the same thing online using BackBlaze. Finally, I also create bootable backups using Carbon Copy Cloner that I keep in our safe deposit box and refresh quarterly.

[1]:	https://bombich.com
[2]:	https://sixcolors.com/post/2016/01/puzzle-solved-a-faster-mac-mini-server/
[3]:	https://katiefloyd.com/blog/mac-mini-upgrade-adventures
[4]:	https://www.amazon.com/dp/B00OBRE5UE/ref=cm_sw_r_cp_tai_Jm2LzbDG9K5KX
[5]:	https://www.ifixit.com/Guide/Mac+Mini+Late+2012+Hard+Drive+Replacement/11716
[6]:	https://www.ifixit.com
[7]:	https://support.apple.com/en-us/HT201314
[8]:	https://en.m.wikipedia.org/wiki/OS_X_Mountain_Lion