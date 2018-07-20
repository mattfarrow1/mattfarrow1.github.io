---
layout: post
title: Sprinkler Upgrades
bigimg: /img/grass.jpeg
tags: [sprinkler, home]
---

Earlier this year I decided to update our old sprinkler controller with something more modern and flexible. The old sprinkler controller came with the house when we bought it almost eight years ago. It functioned, but it always had quirks. The switches often needed a pair of pliers to flip between positions, the timer occasionally lost track of what day it was, and the wiring that connected it to power also made me supremely nervous. 

{% include image.html
            img="img/sprinklers/old-controller.jpg"
            title="Controller"
            caption="Old Controller" %}

When I went looking for a replacement, my greatest desire was to have a smart sprinkler controller that had a companion app for my phone. There were three primary reasons for this decision:

- Intelligent watering based on weather forecasts
- Insight into system status and useage
- Remote monitoring and management

For our house, I ended up choosing the[RainMachine](http://www.rainmachine.com) [Mini-8 2nd generation]( www.rainmachine.com/products/rainmachine-mini-8.html).

{% include image.html
            img="img/sprinklers/rain-machine-outside.jpg"
            title="RainMachine"
            caption="RainMachine Mini-8" %}

### Installation

Installation was a snap. I started by labeling the wires on the old controller. There were three bundles of wires that came into the garage, and each bundle had three wires: one common and two watering zones — for a total of nine wires. Once I'd labeled the wires, I simply removed them from the old controller and unscrewed the controller from the wall.

I mounted the new RainMachine on the wall, trimmed the wires back several inches[^1], and started reconnecting the wires. The Mini-8 has two common wire connection points on either side of the controller that are connected together internally. Since I had three common wires, I made a short pigtail to turn two of the wires into a single wire that I could then insert in the connection point. Inserting the wires was as simple as depressing the orange pin and pushing the wire inside. I then worked my way sequentially through the each of the zones, matching up the numbered wire with the corresponding zone connection point.

{% include image.html
            img="img/sprinklers/rain-machine-inside.jpg"
            title="RainMachine"
            caption="RainMachine Mini-8" %}

Once the wiring was done, I simply connected the included power adapter and waited for the system to boot up.

### Onboarding

Here the experience got a little confusing and clunky. You begin by connecting to the RainMachine's own WiFi signal and then pointing it to your home network. On my first attempt, the web service got stuck and I had to reboot the RainMachine. On the second time through, everything worked flawlessly and I was able to set up an account and connect to my network. 

Once I was connected to my WiFi, I started setting up each of the sprinkler zones. In addition to labeling them in the app, you can also add a photo of the area being watered which I thought was a nice feature. Running each zone manually was as simple as hitting the play button, setting an amount of time, and clicking **ok?** You're also able to start watering from the controller itself by selecting your zone with the arrow buttons and then pressing the watering can. Doing so will activate a 5-minute watering cycle that can be cancelled by pressing the watering can again. 

{% include image.html
            img="img/sprinklers/app-screens.png"
            title="Screens"
            caption="App Screens" %}

### Programs

I started writing this review earlier this summer and I had to put it aside until I felt like I had a better handle on how the RainMachine's programs operated. 

When it came time to build my watering programs, RainMachine can use information about the weather, the type of sprinklers you have, and your soil type to generate suggested watering times. The first time I did this, I was getting suggested times measured in hours of watering, not minutes. Previously, I think the longest cycle time I ever had for a zone was 10 minutes. Maybe I had been under-watering[^2], but something didn't seem right.

There are three different areas that can impact your watering times. The first are your zone-specific settings. Tapping on one of your zones brings up a settings screen for that specific zone, including weather & seasonal adjustments, field capacity (how much water the soil can hold), soil type, sprinkler type, water flow rate, slope, sun exposure and more. My hours of watering was fixed by testing my sprinkler's output, at which point I knew roughly how much water it put out per hour. I could then go into the zone settings and create a custom sprinkler type with the flow rate that matched my test. I then went through the same process with each of my six zones. 

{% include image.html
            img="img/sprinklers/app-zones.png"
            title="Zones"
            caption="Customizing Zones" %}

The second area that you need to consider for your watering times are the options under the Settings tab. Here you can find information about watering restrictions including whether to allow additional watering on hot days, or whether there are certain months, days, or hours you want to restrict watering. This can be useful if you're in an area that only allows watering on certain days of the week and between certain times of day. 

Finally, there are the programs themselves. For each program, you define a start time, frequency (including whether you want use the system's Adaptive Frequency), and the zone(s) you want included in the program. The software will then set a suggested duration for each zone that you can then adjust manually if you prefer. 

{% include image.html
            img="img/sprinklers/app-schedule.png"
            title="Schedule"
            caption="App Schedule" %}

### Day-to-Day Use

Now that I have the system dialed in the way I want, I think that everything runs great. RainMachine offers a number of push notification options that you can use to keep tabs on when the weather has been updated, when programs and zones start and stop, and if there are any detected problems with the system.

I've ended up turning most of those off and keeping only notifications for problems and when a watering program starts and finishes. I liked the zone notifications when I was getting the system tuned, but the way the programs run, using a cycle and soak system to discourage runoff, I was often getting a barrage of notifications each morning. 

### Final Thoughts

The RainMachine hardware is well-made and incredibly simple to install. Software-wise, I have a few quibbles:

- The app could use real estate a little better, especially on larger devices.
- There are too many menus and sub-menus to sort through. Even now, I have trouble remembering if something should be changed in the program's advanced features or the zone specific settings. 
- The Dashboard could use some clarity into what the different charts are showing you. Other than the temperature and forecasted rainfall, I think that most of those charts are useful if you are using the weather-adaptive watering features. Now that I feel like I have a better handle on the system, I may go back and try using those again.
- I wish there was HomeKit support with the app. 

[^1]: The old controller's wiring was pretty poor, so I took the opportunity to cut the wires back so that they fit cleanly inside the housing.

[^2]: Although my lawn certainly always seemed to look fine before. In writing this post, I ended up at my father-in-law's new house getting his sprinkler system tuned up. I discussed watering times with the company's owner and found my times were pretty accurate.