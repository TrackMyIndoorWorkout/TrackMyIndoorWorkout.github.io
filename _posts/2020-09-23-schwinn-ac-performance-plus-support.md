---
layout: post
title: Schwinn AC Performance Plus Support
date: 2020-09-23 12:00:00
---
The [Schwinn AC Performance Plus bike](https://www.amazon.com/AC-Performance-Plus-Indoor-Cycle/dp/B002KV942W) has an [MPower Echelon2 console](https://www.amazon.com/Schwinn-MPower-Echelon2-Console-Upgrade/dp/B074TK4NQ2) which only supports ANT+ protocol and not Bluetooth, therefore your tablet or phone cannot directly connect to it. For the same reason Track My Indoor Workout cannot directly measure the workouts, but fortunately the console supports the save of your workout to a USB thumb drive and the application is capable of importing that:

0. Obtain a USB thumb drive and make sure it is formatted to the FAT32 file system (99% of the time that's the case).
1. [Watch this video about how you can save your workout onto the pen drive](https://www.youtube.com/watch?v=ENkHdcV_E70)
1. Connect the thumb drive to the console before the workout.
1. Start pedaling and press the top button to turn on the console.
1. If you wear an ANT+ compatible heart rate monitor then press the bottom right AVG button so the console picks up the heart rate measurements.
1. Proceed with your workout as usual.
1. After the workout - possibly during the stretching phase - long press the AVG button until an USB connectivity icon appears and starts blinking on the console display [as the video referenced earlier shows](https://www.youtube.com/watch?v=ENkHdcV_E70).
1. Release the AVG button and wait until the USB icon stops blinking and disappears.
1. Disconnect the thumb drive.
1. Upload the resulting CSV file onto a file sharing service which is capable of providing a direct RAW link to the CSV file. The raw link is extremely important: Google Drive, Microsoft OneDrive, and majority of the file sharing services are unable to give you a direct link! You can either use the ['?dl=2' DropBox trick](https://www.youtube.com/watch?v=zM919plLAtk) or use GitHub or similar Git hosting services to conclude to a RAW link.
1. Navigate to the Activity list screen in the Track My Indoor Workout app.
1. Click on the Upload arrow in the header (next to the question mark button).
1. On the Import form paste the RAW URL onto the first edit field.
1. Specify the date and time of your workout.
1. Click the import button.
1. The import process needs to populate several thousands of records into the local database of the app, which can sometimes take ten seconds or more depending on the speed of your phone and the length of the workout.
1. Navigate back to the activity list and refresh the list, your newly imported workout should appear now. Study the workout if it matches your expectations.
