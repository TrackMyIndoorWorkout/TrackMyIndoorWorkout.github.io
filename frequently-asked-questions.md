---
layout: page
title: FAQ
permalink: /faq/
redirect_from:
  - /frequently-asked-questions/
---

<h1 class="page-title">{{ page.title | escape }}</h1>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I cannot upload the downloaded files to my choice of sport portal. Why is that?
        </div>
        <div class="col s12">
            A: The application compresses the files when uploading them to Strava to shorten the upload time and save bandwidth. Your downloaded files might be compressed too: you can recognize that if the file extension is ending with '.gz', like '.TCX.gz' or '.FIT.gz.'. Although sport portals may accept compressed uploads programmatically, for manual uploads they require uncompressed files. On Windows operating system <a href="https://www.7-zip.org/">7-Zip</a> or <a href="https://www.ghisler.com/">Total Commander</a> is able to help you with GZIP decompression.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I put the application in the background / locked my phone during workout measurement. The application slowed down, became unresponsive for some time and the resulting recording seems off. What happened?
        </div>
        <div class="col s12">
            A: For <a href="https://stackoverflow.com/questions/64831910/how-to-make-my-app-keep-receiving-and-processing-bluetooth-data-while-the-phone">technical reasons the data acquisition pauses when the application is not in the foreground</a> (either being in the background or the phone getting locked). This is the reason why the measurement screen has a wake lock which prevents the phone from going to sleep during workout. When this issue happens the information piles up and once the application gets back into the foreground it is flooded with all of that at once. The Precor Spinner Chrono Power attaches time stamps to their data packets but the Schwinn IC4 for example does not and that makes it impossible to reconstruct a workout forensically when this flooding happens. So the resulting workout will be skewed and the processing of many packets makes the app unresponsive. The future versions will have a rate limiting which will help to drop the packages, but that won't help with the core problem. If you are software engineer proficient in Flutter feel free to help me with advice to tackle this.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: My phone is very sluggish, the application lags behind. Can that be improved?
        </div>
        <div class="col s12">
            A: I'm aware that the application is not performant enough for older or slower devices. A partial fix I can offer is a settings switch called "Simplify Measurement UI". It is off by default, but when turned on the graphs won't be available during measurement - thus decreasing the complexity of that screen. You'll still be able to look at the graphs when you examine activities in the activity list screen post-workout.
        </div>
        <div class="col s12">
            <img src="/img/simplify_measurement_ui.jpg" alt="Simplify Measurement UI switch">
        </div>
        <div class="col s12">
            If you are software engineer proficient in Flutter feel free to help me: my goal is to refactor the application to utilize Provider and BLoC design patterns and eradicate any setState calls.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I see a blank white screen after I start the app. How can I fix that?
        </div>
        <div class="col s12">
            A: The application has many moving parts and if the underlying engine experiences any glitches during the starting phase then the initialization might stop: effectively the app presents a blank white screen and doesn't advance. Some users experienced such phenomena during the first application start after a fresh install. As a workaround try closing the app and then starting it again - this can help if the white screen only comes for the very first start after installation. If that doesn't help (and even if it helps) please contact me by email and tell me what phone / tablet do you have and how did you experience the white screen.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: The graphs are too tall on the workout measurement screen, can I change that?
        </div>
        <div class="col s12">
            A: There's a feature for that: long press the graph you wish to change the height of. The app will rotate between 1/2, 1/3, and 1/4 screen height versions. Your choice should be preserved between application runs similarly as the status of which graph is visible or not.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: The calorie counting doesn't match the console display or my expectations. What could be the reason?
        </div>
        <div class="col s12">
            A: Certain fitness equipment doesn't report the calorie reading or distance reading it displays on its console. Therefore Track My Indoor Workout needs to estimate those values on its own. In case of calories the app uses the power reading (Watts) to integrate those values over time to come up with a calorie value. However the human body has about 20%-25% efficiency, so when an equipment measures 75 Watts the human body actually expends four or five times that energy. With these heuristics the number the application comes up with could be very well different than the console reading. Similarly distance sometimes has to be integrated over time using the speed readings. The upcoming release will provide a way to manually tune such situations. In extreme cases (Schwinn AC Performance Plus) the app computes speed from the Watt readings in which case even wind resistance is taken into account, and the outcome will yet again differ from what the console reports, but in this case it would be certainly more realistic.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: The Strava upload claims I don't have a data connection although I know the wifi is connected. In other networks I can successfully upload my workouts. How can I fix that?
        </div>
        <div class="col s12">
            A: When determining the data connection status the app doesn't only look if the wifi is connected but it tries to perform DNS requests to three servers: 1.1.1.1 (CloudFlare), 8.8.4.4 (Google), and 208.67.222.222 (OpenDNS). If the wifi access point you connect to is configured in a special way it may not let these DNS requests go through and the application will deem off-line conditions. The set of servers for this data connection test will change and will be configurable in the upcoming release of the application.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: You mention the upcoming version several times. Is there any way to try that?
        </div>
        <div class="col s12">
            A: Email me your Gmail or GSuite email address and I can add you to the closed beta version. The closed beta version can frequently change and could potentially contains bugs. The open beta release is more stable.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I have trouble with Strava uploads. How can I fix that?
        </div>
        <div class="col s12">
            A: For a successful Strava authentication the system has to jump a gap between the application into the browser and then jump the gap again backwards with the authentication result. The easiest to identify an unsuccessful authentication is when the app repeatedly brings you to the Strava login screen. A simplest trick you can try to help is to start the default browser (that's the same browser the application starts for you) on your device and login to Strava in advance before you'll try the upload. It's very crucial to do that in the same type of browser the application uses, otherwise it won't be able to take advantage of your logged in status. If that doesn't help there can be many reasons for a failure. If you use another browser as the default than the usual system default browser it may help to temporarily revert back the default status to the system's browser. In the following screenshots I show you how to check the list of your supported apps on a desktop browser. If 'Track My Indoor Workout' is listed then it means you've successfully authenticated the application in the past sometimes. Uninstallation of the application will require another authentication though, so the presence of the app in this list may not mean that your current installation is authenticated as well.
        </div>
        <div class="col s12">
            <img src="/img/strava_my_apps1.jpg" alt="Strava My Apps 1">
        </div>
        <div class="col s12">
            <img src="/img/strava_my_apps2.jpg" alt="Strava My Apps with Track My Indoor Workout">
        </div>
    </div>
</div>

<div class="divider"></div>
