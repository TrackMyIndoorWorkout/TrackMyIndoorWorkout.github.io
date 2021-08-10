---
layout: post
title: Frequently Asked Questions
date: 2020-09-22 12:00:00
---
##### Q: I cannot upload the downloaded files to my choice of workout portal. Why is that?

A: The application compresses the files when uploading them to Strava to shorten the upload time and save bandwidth. Your downloaded files might be compressed too: you can recognize that if the file extension is ending with '.gz', like '.TCX.gz' or '.FIT.gz.'. Although workout portals may accept compressed uploads programmatically, for manual uploads they require uncompressed files. On Windows operating system [7-Zip](https://www.7-zip.org/) or [Total Commander](https://www.ghisler.com/) is able to help you with GZIP decompression.

##### Q: The CSV download has weird numbers in the date/time cells. How can I convert those to a human readable form?

A: The CSV file's main purpose is to migrate data between application installations and what you see is how the app stores the time stamps in the database: in millisecond precision 'UNIX Epoch time' format. It tells how many milliseconds passed since midnight 1/1/1970. The best way to convert those is to transform them into a so called 'OADate' (OLE Automation Date) format by applying a formula '=(E19/1000/86400)+25569' where 'E19' is the cell we would like to convert. This will still be a number, however if you switch the cell formatting to date you'll see the date portion of it and similarly if you switch the formatting to time you'll see the time portion.

##### Q: I put the application in the background / locked my phone during workout measurement. The application slowed down, became unresponsive for some time and the resulting recording seems off. What happened?

A: For [technical reasons the data acquisition pauses when the application is not in the foreground](https://stackoverflow.com/questions/64831910/how-to-make-my-app-keep-receiving-and-processing-bluetooth-data-while-the-phone) (either being in the background or the phone getting locked). This is the reason why the measurement screen has a wake lock which prevents the phone from going to sleep during workout. When this issue happens the information piles up and once the application gets back into the foreground it is flooded with all of that at once. The Precor Spinner Chrono Power attaches time stamps to their data packets but the Schwinn IC4 for example does not and that makes it impossible to reconstruct a workout forensically when this flooding happens. So the resulting workout will be skewed and the processing of many packets makes the app unresponsive. The future versions will have a rate limiting which will help to drop the packages, but that won't help with the core problem. If you are a software engineer proficient in Flutter feel free to help me with advice to tackle this.

##### Q: My phone is very sluggish, the application lags behind. Can that be improved?

A: I'm aware that the application is not performant enough for older or slower devices. A partial fix I can offer is a settings switch called "Simplify Measurement UI". It is off by default, but when turned on the graphs won't be available during measurement - thus decreasing the complexity of that screen. You'll still be able to look at the graphs when you examine activities in the activity list screen post-workout.

![Simplify Measurement UI switch](/img/simplify_measurement_ui.jpg)

If you are a software engineer proficient in Flutter feel free to help me: my goal is to refactor the application to utilize Provider and BLoC design patterns and eradicate any setState calls.

##### Q: I see a blank white screen after I start the app. How can I fix that?

A: The application has many moving parts and if the underlying engine experiences any glitches during the starting phase then the initialization might stop: effectively the app presents a blank white screen and doesn't advance. Some users experienced such phenomena during the first application start after a fresh install. As a workaround try closing the app and then starting it again - this can help if the white screen only comes for the very first start after installation. If that doesn't help (and even if it helps) please contact me by email and tell me what phone / tablet you have and how you experience the white screen.

##### Q: The graphs are too tall on the workout measurement screen, can I change that?

A: There's a feature for that: long press the graph you wish to change the height of. The app will rotate between 1/2, 1/3, and 1/4 screen height versions. Your choice should be preserved between application runs similarly as the status of which graph is visible or not.

##### Q: The calorie counting doesn't match the console display or my expectations. What could be the reason?

A: Certain fitness machines don't report the calorie reading or distance reading they display on their console. Therefore Track My Indoor Workout needs to estimate those values on its own. In case of calories the app uses the power reading (Watts) to integrate those values over time to come up with a calorie value. However the human body has about 20%-25% efficiency, so when a machine measures 75 Watts the human body actually expends four or five times that energy. With these heuristics the number the application comes up with could be very well different than the console reading. Similarly distance sometimes has to be integrated over time using the speed readings. The upcoming release will provide a way to manually tune such situations. In extreme cases (Schwinn AC Performance Plus) the app computes speed from the Watt readings in which case even wind resistance is taken into account, and the outcome will yet again differ from what the console reports, but in this case it would be certainly more realistic.

##### Q: The Strava upload claims I don't have a data connection although I know the wifi is connected. In other networks I can successfully upload my workouts. How can I fix that?

A: When determining the data connection status the app doesn't only look if the wifi is connected but it tries to perform DNS requests to three servers: 1.1.1.1 (CloudFlare), 8.8.4.4 (Google), and 208.67.222.222 (OpenDNS). If the wifi access point you connect to is configured in a special way it may not let these DNS requests go through and the application will deem off-line conditions. The set of servers for this data connection test will change and will be configurable in the upcoming release of the application.

##### Q: You mention the upcoming version several times. Is there any way to try that?

A: There's an open beta version which may contain new features, you can opt-in to beta in Google Play Store. Email me your Gmail or GSuite email address and I can add you to the closed beta version. The closed beta version can frequently change and could potentially contain bugs. The open beta release is more stable.

##### Q: All of my workouts show up in Fresno. Is there a way to change that?

A: It's a unique feature of the application that it is able to generate a GPS track for your indoor workouts, so your workouts can count against
challenges which require GPS. However with great power comes great responsibility. Early versions generated the ride routes into the Jerry Baker Memorial / Marymoore Velodrome in Redmond Washington. However it soon revealed that the workouts would interfere with real velodrome rider's results. Combine this with the fact that indoor bikes can be miscalibrated (not to mention the applications power tuning feature) it'd be unfair and unethical to take down KOMs. Similar thinking goes to indoor runs. Therefore I picked a running track for the bike rides, because this ensured there wouldn't be any KOM segments on the generated route. Similarly the run is done in a position where there aren't any running segments to CR. It's a low priority ticket to allow picking tracks per timezone (or even per country).

##### Q: I have trouble with Strava uploads. How can I fix that?

A: For a successful Strava authentication the system has to jump a gap between the application into the browser and then jump the gap again backwards with the authentication result. The easiest to identify an unsuccessful authentication is when the app repeatedly brings you to the Strava login screen. A simplest trick which may help is to start the default browser (that's the same browser the application starts for you) on your device and login to Strava in advance before you'll try the upload. It's very crucial to do that in the same type of browser the application uses, otherwise it won't be able to take advantage of your logged in status. If that doesn't help there can be many reasons for a failure. If you use another browser as the default than the usual system default browser it may help to temporarily revert back the default status to the system's browser. In the following screenshots I show you how to check the list of your supported apps on a desktop browser. If 'Track My Indoor Workout' is listed then it means you've successfully authenticated the application in the past sometimes. Uninstallation of the application will require another authentication though, so the presence of the app in this list may not mean that your current installation is authenticated as well.

![Strava My Apps 1](/img/strava_my_apps1.jpg)
![Strava My Apps with Track My Indoor Workout](/img/strava_my_apps2.jpg)
