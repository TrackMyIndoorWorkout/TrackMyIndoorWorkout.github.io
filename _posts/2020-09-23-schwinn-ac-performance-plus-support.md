---
layout: post
title: Schwinn AC Performance Plus Support
date: 2020-09-23 12:00:00
---
The [Schwinn AC Performance Plus bike](https://www.amazon.com/AC-Performance-Plus-Indoor-Cycle/dp/B002KV942W) has an [MPower Echelon2 console](https://www.amazon.com/Schwinn-MPower-Echelon2-Console-Upgrade/dp/B074TK4NQ2) which only supports ANT+ protocol and not Bluetooth, therefore your tablet or phone cannot directly connect to it. For the same reason Track My Indoor Workout application cannot measure the workouts, but fortunately the console allows saving of your workout to a USB thumb drive and the application is capable of importing it:

0. Obtain a USB thumb drive and make sure it is formatted to the FAT32 file system (99% of the time that is the case).
1. [Watch this video about how you can save your workout onto the pen drive](https://www.youtube.com/watch?v=ENkHdcV_E70)
1. Connect the thumb drive to the console before the workout.
1. If you wear an ANT+ compatible heart rate monitor then put it in pairing mode because the console will scan for that right after it is turned on.
1. Start pedaling and press the top button to turn on the console.
1. Proceed with your workout as usual.
1. After the workout - possibly during the stretching phase - long press (very long, 10+ seconds) the AVG button until a USB connectivity icon appears and starts blinking on the console display ([as on the video referenced earlier shows](https://www.youtube.com/watch?v=ENkHdcV_E70)).
1. Release the AVG button and wait until the USB icon stops blinking, becomes solid, and then disappears.
1. Disconnect the thumb drive.
1. Upload the resulting CSV file onto your preferred file sharing service which is installed on your phone as well.
1. Install and start the Track My Indoor Workout application. In case you'd only use it to import workouts you'd still need to give bluetooth permissions because the bluetooth module core part of application.
1. Navigate to the Activity list screen in the Track My Indoor Workout application by selecting the list icon in the start screen menu.
1. On the activity list screen click the Upload arrow in the header (next to the question mark button).
1. On the Import form click on the three dots (...) and pick the file you uploaded in the earlier step.
1. Specify the date and time of your workout.
1. Click the import button.
1. The import process needs to populate several thousands of records into the local database of the app, which can sometimes take a good while depending on the speed of your phone and the length of the workout.
1. Navigate back to the activity list and refresh the list. Your newly imported workout should appear now. Study the workout if it matches your expectations.
