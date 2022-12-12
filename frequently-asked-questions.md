---
layout: page
title: FAQ
short_title: FAQ
permalink: /faq/
redirect_from:
  - /frequently-asked-questions/
---

<h1 class="page-title">{{ page.title | escape }}</h1>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: Why only the active / moving time is displayed during the workout? Can I change that?
        </div>
        <div class="col s12">
            A: The application by default displays the so-called moving time and does not count those seconds when the workout is stopped. After the workout is over both the moving (or active) and the total elapsed time are displayed (separately) on the activity list screen's detail cards. Fortunately this behavior is configurable: under the "Workout" configuration section the "TIme Display Mode" is "Moving" by default. If you switch that to "Elapsed" then the total time (which includes pauses as well) will be displayed.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: Why does the application ask for location permission?
        </div>
        <div class="col s12">
            A: The application DOES NOT COLLECT any location data. Location permission is required because of technical quirks for communication with Bluetooth Low Energy Fitness Machines. In the future on Android 12 and later this won't be needed. Your privacy is very important to me, which is one reason why the app does not have a back-end / "mothership". Everything what the app does is in response to an action you gave, you are in total control.  The application is also open source so you can check exactly what it is doing if you are in doubt.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: Why does the application ask for storage (file) permissions?
        </div>
        <div class="col s12">
            A: So the app does not have its own back-end / "mothership" (server where your data would be stored). All data is stored only locally on the specific device you recorded an activity with. Therefore it's an essential feature to upload the workouts to fitness portals or download them in various formats (like TCX, FIT), but of course only if you wish to. The target location of your download is chosen by you, but it can be a cloud storage (Google Drive, OneDrive, etc.) or your local device's storage so you can forward it to wherever you want to, it's all up to you. But because it can be your local storage, the app asks for storage permissions. The app does not care and never touches any of your files except what you explicitly instructed it to. Your privacy is very important to me, which is one reason why the app does not have a back-end / "mothership". Everything what the app does is in response to an action you gave, you are in total control. The application is also open source so you can check exactly what it is doing if you are in doubt.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I cannot upload the downloaded files to my choice of workout portal. Why is that?
        </div>
        <div class="col s12">
            A: The application compresses the files when uploading them to Strava to shorten the upload time and save bandwidth. Your downloaded files might be compressed too: you can recognize that if the file extension is ending with '.gz', like '.TCX.gz' or '.FIT.gz.'. Although workout portals may accept compressed uploads programmatically, for manual uploads they require uncompressed files. On Windows operating system <a href="https://www.7-zip.org/">7-Zip</a> or <a href="https://www.ghisler.com/">Total Commander</a> is able to help you with GZIP decompression.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: The CSV download has weird numbers in the date/time cells. How can I convert those to a human readable form?
        </div>
        <div class="col s12">
            A: The CSV file's main purpose is to migrate data between application installations and what you see is how the app stores the time stamps in the database: in millisecond precision 'UNIX Epoch time' format. It tells how many milliseconds passed since midnight 1/1/1970. The best way to convert those is to transform them into a so called 'OADate' (OLE Automation Date) format by applying a formula '=(E19/1000/86400)+25569' where 'E19' is the cell we would like to convert. This will still be a number, however if you switch the cell formatting to date you'll see the date portion of it and similarly if you switch the formatting to time you'll see the time portion.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I put the application in the background / locked my phone during workout measurement. The application slowed down, became unresponsive for some time and the resulting recording seems off. What happened?
        </div>
        <div class="col s12">
            A: For <a href="https://stackoverflow.com/questions/64831910/how-to-make-my-app-keep-receiving-and-processing-bluetooth-data-while-the-phone">technical reasons the data acquisition pauses when the application is not in the foreground</a> (either being in the background or the phone getting locked). This is the reason why the measurement screen has a wake lock which prevents the phone from going to sleep during workout. When this issue happens the information piles up and once the application gets back into the foreground it is flooded with all of that at once. The Precor Spinner Chrono Power attaches time stamps to their data packets but the Schwinn IC4 for example does not and that makes it impossible to reconstruct a workout forensically when this flooding happens. So the resulting workout will be skewed and the processing of many packets makes the app unresponsive. The future versions will have a rate limiting which will help to drop the packages, but that won't help with the core problem. If you are a software engineer proficient in Flutter feel free to help me with advice to tackle this.
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
            <img class="responsive-img" src="/img/simplify_measurement_ui.jpg" alt="Simplify Measurement UI switch">
        </div>
        <div class="col s12">
            If you are a software engineer proficient in Flutter feel free to help me: my goal is to refactor the application to utilize Provider and BLoC design patterns and eradicate any setState calls.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I see a blank white screen after I start the app. How can I fix that?
        </div>
        <div class="col s12">
            A: The application has many moving parts and if the underlying engine experiences any glitches during the starting phase then the initialization might stop: effectively the app presents a blank white screen and doesn't advance. Some users experienced such phenomena during the first application start after a fresh install. As a workaround try closing the app and then starting it again - this can help if the white screen only comes for the very first start after installation. If that doesn't help (and even if it helps) please contact me by email and tell me what phone / tablet you have and how you experience the white screen.
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
            A: Certain fitness machines don't report the calorie reading or distance reading they display on their console. Therefore {{ site.application_name }} needs to estimate those values on its own. In case of calories the app uses the power reading (Watts) to integrate those values over time to come up with a calorie value. However the human body has about 20%-25% efficiency, so when a machine measures 75 Watts the human body actually expends four or five times that energy. With these heuristics the number the application comes up with could be very well different than the console reading. Similarly distance sometimes has to be integrated over time using the speed readings. The upcoming release will provide a way to manually tune such situations. In extreme cases (Schwinn AC Performance Plus) the app computes speed from the Watt readings in which case even wind resistance is taken into account, and the outcome will yet again differ from what the console reports, but in this case it would be certainly more realistic.
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
            A: There is an open beta version that may contain new features, one can opt-in to beta visiting the app's page in Google Play Store. You must visit that page with your handheld device because the button saying "Join the beta" does not appear when you view it with a desktop browser. Since beta versions have new features and code changes there is more chance to encounter a bug than in the stable/final releases.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: All of my workouts show up in Fresno. Is there a way to change that?
        </div>
        <div class="col s12">
            A: It's a unique feature of the application that it is able to generate a GPS track for your indoor workouts, so your workouts can count against challenges which require GPS. However with great power comes great responsibility. Early versions generated the ride routes into the Jerry Baker Memorial / Marymoore Velodrome in Redmond Washington. However it soon revealed that the workouts would interfere with real velodrome rider's results. Combine this with the fact that indoor bikes can be miscalibrated (not to mention the applications power tuning feature) it'd be unfair and unethical to take down KOMs. Similar thinking goes to indoor runs. Therefore I picked a running track for the bike rides, because this ensured there wouldn't be any KOM segments on the generated route. Similarly the run is done in a position where there aren't any running segments to CR. It's a low priority ticket to allow picking tracks per timezone (or even per country).
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: Strava claims "The upload appears to be malformed and we are unable to process it" when I try to upload an exported FIT file. What could be the reason?
        </div>
        <div class="col s12">
            A: While TCX files are human-readable XML-type text files, FIT files are binary files. A reason for a malformed FIT file could be if any software interferes with the file. FIT files sometimes can be recognized as image files by computer operating systems, in this case, that would be a misinterpretation. I can imagine maybe some anti-virus or corporate defense programs may tamper with the file. Never open the FIT file with any text editor (like Notepad or Word). Try to keep it as intact as possible until you manually upload it.
        </div>
    </div>
</div>

<div class="section">
    <div class="row">
        <div class="col s12">
            Q: I have trouble with Strava uploads. How can I fix that?
        </div>
        <div class="col s12">
            A: For a successful Strava authentication the system has to jump a gap between the application into the browser and then jump the gap again backwards with the authentication result. The easiest to identify an unsuccessful authentication is when the app repeatedly brings you to the Strava login screen. A simplest trick which may help is to start the default browser (that's the same browser the application starts for you) on your device and login to Strava in advance before you'll try the upload. It's very crucial to do that in the same type of browser the application uses, otherwise it won't be able to take advantage of your logged in status. If that doesn't help there can be many reasons for a failure. If you use another browser as the default than the usual system default browser it may help to temporarily revert back the default status to the system's browser. In the following screenshots I show you how to check the list of your supported apps on a desktop browser. If '{{ site.application_name }}' is listed then it means you've successfully authenticated the application in the past sometimes. Uninstallation of the application will require another authentication though, so the presence of the app in this list may not mean that your current installation is authenticated as well.
        </div>
        <div class="col s12">
            <img class="responsive-img" src="/img/strava_my_apps1.jpg" alt="Strava My Apps 1">
        </div>
        <div class="col s12">
            <img class="responsive-img" src="/img/strava_my_apps2.jpg" alt="Strava My Apps with {{ site.application_name }}">
        </div>
    </div>
</div>

<div class="divider"></div>
