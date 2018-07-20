---
layout: post
title: Sprinkler Upgrades
tags: [sprinkler, home]
---

Earlier this year I decided to update our old sprinkler controller with something more modern and flexible. The old controller came with the house when we bought it almost eight years ago. It functioned, but it always had quirks. The switches often needed a pair of pliers to flip between positions, the timer occasionally lost track of what day it was, and the wiring that connected it to power also made me supremely nervous. 

{% include image.html
            img="img/sprinklers/old-controller.jpg"
            title="Controller"
            caption="Old Controller" %}

When I went looking for a replacement, my greatest desire was to have a smart sprinkler controller that had a companion app for my phone. There were three primary reasons for this decision:

- Intelligent watering based on weather forecasts
- Insight into system status and useage
- Remote monitoring and management

For our house, I ended up choosing the [RainMachine Mini-8 2nd generation](https://www.rainmachine.com/products/rainmachine-mini-8.html).

{% include image.html
            img="img/sprinklers/rain-machine-outside.jpg"
            title="RainMachine"
            caption="RainMachine Mini-8" %}

### Installation

Installation was a breeze. I unplugged the controller, labeled the existing wires, disconnected them, and finally removed the old controller from the wall. After mounting the RainMachine, I worked my way through the wires, connecting them to the clearly labeled points on the new controller. Inserting the wires was as simple as depressing the orange pin and pushing the wire inside. 

{% include image.html
            img="img/sprinklers/rain-machine-inside.jpg"
            title="RainMachine"
            caption="RainMachine Mini-8" %}

Once the wiring was done, I simply connected the included power adapter and waited for the system to boot up.

### Onboarding

Here the experience became a little confusing and clunky. You begin by connecting to the RainMachine's own WiFi signal and then pointing it to your home network. On my first attempt, the web service got stuck and I had to reboot the RainMachine. The second time everything worked flawlessly and I was able to set up an account and connect to my network. 

Once I was connected to my home's WiFi, I started setting up each of the sprinkler zones. In addition to labeling them in the app, you can also add a photo of the area being watered which I thought was a nice feature. Running each zone manually was as simple as hitting the play button, setting an amount of time, and clicking **ok?** You're also able to start watering from the controller itself by selecting your zone with the arrow buttons and then pressing the watering can. Doing so will activate a 5-minute watering cycle that can be cancelled by pressing the watering can again. 

{% include image.html
            img="img/sprinklers/app-screens.png"
            title="Screens"
            caption="App Screens" %}

### Programs

RainMachine's ability connect to the internet to pull down information about the weather means it can use that data, along with information about the types of sprinklers you have and your soil information, to generate suggested watering times for your programs. 

The first time I set up a program, I specified which zones I wanted to come on and on which days of the week. The system returned suggested watering times measures in hours of watering, not minutes. Previously, I think the longest cycle time I ever had for a zone was 10 minutes. Maybe I had been under-watering[^1], but something didn't seem right.

As I spent more time with the system, I realized that there are three different areas that can impact your watering times. The first are your zone-specific settings. Tapping on one of your zones brings up a settings screen for that specific zone, including weather & seasonal adjustments, field capacity (how much water the soil can hold), soil type, sprinkler type, water flow rate, slope, sun exposure and more. 

My hours of watering was fixed by [testing my sprinkler's output](http://ipm.ucanr.edu/TOOLS/TURF/MAINTAIN/output.html), at which point I knew roughly how much water it put out per hour. I could then go into the zone settings and create a custom sprinkler type with the flow rate that matched my test. I then went through the same process with each of my six zones. 

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

I've ended up turning most of those off and keeping only notifications for problems and when a watering program starts and finishes. I liked the zone notifications when I was getting the system tuned, but the way the programs run, using a cycle and soak system to discourage runoff, I was getting a barrage of notifications each morning. 

During my testing, I also ran into two situations where our internet was out for an extended period of time[^2]. The system appears to store your program information on the RainMachine controller so that, even without an internet connection, your sprinklers will continue to run on their regular schedule. 

### Final Thoughts

The RainMachine hardware is well-made and incredibly simple to install. Software-wise, I have a few quibbles:

- The app could use real estate a little better, especially on larger devices.
- There are too many menus and sub-menus to sort through. Even now, I have trouble remembering if something should be changed in the program's advanced features or the zone specific settings. 
- I wish there was HomeKit support with the app. While certainly not a deal-breaker, with more an more home automation equipment in my life, I appreciate having everything in one place as much as possible. 

[^1]: Although my lawn certainly always seemed to look fine before. In writing this post, I ended up at my father-in-law's new house getting his sprinkler system tuned up. I discussed watering times with the company's owner and found my times were pretty accurate.
[^2]: I realized very quickly how dependent our family is on the internet.