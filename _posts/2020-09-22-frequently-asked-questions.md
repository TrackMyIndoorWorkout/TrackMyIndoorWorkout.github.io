---
layout: post
title: Frequently Asked Questions
date: 2020-09-22 12:00:00
---
##### Q: The Strava upload claims I don't have a data connection although I know the wifi is connected. In other networks I can successfully upload my workouts. How can I fix that?

A: When determining the data connection status the app doesn't only look if the wifi is connected but it tries to perform DNS requests to three servers: 1.1.1.1 (CloudFlare), 8.8.4.4 (Google), and 208.67.222.222 (OpenDNS). If the wifi access point you connect to is configured in a special way it may not let these DNS requests go through and the application will deem off-line conditions.

##### Q: I see a blank white screen after I start the app. How can I that?

A: The application has many moving parts and if the underlying engine experiences any glitches during the starting phase then the initialization might stop: effectively the app presents a black white screen and doesn't advance. Some users experienced such phenomena during the first application start after a fresh install. As a workaround try closing the app and then starting it again. If that doesn't help (and even if it helps) please contact me by email and tell me what phone / tablet do you have and how did you experience the white screen.

##### Q: The graphs are too tall on the workout measurement screen, can I change that?

A: There's a feature for that: long press the graph you wish to change the height of. The app will rotate between 1/2, 1/3, and 1/4 screen height versions. Your choice should be preserved between application runs similarly as the status of which graph is visible or not.

##### Q: The calorie counting doesn't match the console display or my expectations. What could be the reason?

A: Certain fitness equipment doesn't report the calorie reading or distance reading it displays on its console. Therefore Track My Indoor Workout needs to estimate those values on its own. In case of calories the app uses the power reading (Watts) to integrate those values over time to come up with a calorie value. However the human body has about 20%-25% efficiency, so when an equipment measures 75 Watts the human body actually expends four or five times that energy. With these heuristics the number the application comes up with could be very well different than the console reading. Similarly distance sometimes has to be integrated over time using the speed readings. The upcoming release will provide a way to manually tune such situations. In extreme cases (Schwinn AC Performance Plus) the app computes speed from the Watt readings in which case even wind resistance is taken into account.
