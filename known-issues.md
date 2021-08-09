---
layout: page
title: Known Issues
permalink: /known-issues/
---

<h1 class="page-title">{{ page.title | escape }}</h1>

<div class="section">
    <div class="row">
        <div class="col s12">
            Some handheld devices might present a blank white screen after the app start and don't advance to the actual scanning page. There can be multiple reasons for this, some of which I couldn't solve yet. In some cases that happens only for the first start after a fresh install. Although not elegant, but in such case it helps to simply kill the app and start it again, and this behavior won't re-occur. Otherwise please email me your configuration: phone model, Android version, do you have bluetooth enabled and if the app has permissions.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            During workout measurement the application has to be in the foreground. For <a href="https://stackoverflow.com/questions/64831910/how-to-make-my-app-keep-receiving-and-processing-bluetooth-data-while-the-phone">technical reasons the data acquisition pauses when the application is not in the foreground</a> (either being in the background or the phone getting locked). This is the reason why the measurement screen has a wake lock which prevents the phone from going to sleep during workout. See the <a href="faq/">FAQ for more details</a>. If you are software engineer proficient in Flutter feel free to help me with advice to tackle this.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            The application is not performant enough for older or slower devices. A partial fix I can offer is a settings switch called "Simplify Measurement UI". It is off by default, but when turned on the graphs won't be available during measurement - thus decreasing the complexity of that screen. You'll still be able to look at the graphs when you examine activities in the activity list screen post-workout. If you are software engineer proficient in Flutter feel free to help me: my goal is to refactor the application to utilize Provider and BLoC design patterns and eradicate any setState calls.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Up until app version 1.0.30 (build 30) the downloaded exercise files have to be un-gzipped if their extension ends with '.gz', because workout portals only accept uncompressed versions. On Windows operating system <a href="https://www.7-zip.org/">7-Zip</a> or <a href="https://www.ghisler.com/">Total Commander</a> is able to help you with GZIP decompression.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Rarely on certain managed networks Strava upload may falsely claim no internet connection. This is an interference between the network configuration and how the application determines connection. <a href="faq/">For more details please check out the FAQ page entry</a>. Newer than the #30 builds will have a configurable behavior in this respect.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Calorie counting (or some other aspect) might not match the console's display or expectations. Certain fitness machines don't report the calorie reading or distance reading they display on their console. Therefore Track My Indoor Workout needs to estimate those values on its own and that can result in sometimes even significant difference. <a href="faq/">The FAQ contains more details</a> and the future release will provide detailed configuration for the behavior to manually counteract any drift.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Strava authentication procedure can fail in some cases. The Android ecosystem is extremely versatile and I wasn't able to track down the reason yet. A simplest trick which may help is to start the default browser (that's the same browser the application starts for you) on your device and login to Strava in advance before you'll try the upload. It's very crucial to do that in the same type of browser the application uses, otherwise it won't be able to take advantage of your logged in status. If that doesn't help there can be many reasons for a failure. If you use another browser as the default than the usual system default browser it may help to temporarily revert back the default status to the system's browser.
        </div>
    </div>
</div>

<div class="divider"></div>
