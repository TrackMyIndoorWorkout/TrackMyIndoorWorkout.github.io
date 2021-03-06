---
layout: home
---
Track My Indoor Workout is a free application to record virtual workouts including all the important metrics (power meter reading, cadence sensor, spent calories, heart rate, speed, distance) while also adding emulated GPS routes. Workouts can be synced to [Strava](https://www.strava.com/) for persistence, or [TCX files](https://en.wikipedia.org/wiki/Training_Center_XML) can be downloaded for ingestion into other workout portals. One major motivation for the app was that some cycling oriented fitness challenges wouldn't count virtual rides without GPS data plus the Wahoo app didn't pick up the power meter and cadence readings.

The app calculates the GPS route based on the speed data and emulates circling laps on a running track (Hoover High School, to avoid any interference with Strava cycling segments and KOMs - running activities will be in a velodrome for the same reason). Currently the app supports the following fitness equipment:

1. [Precor Spinner® Chrono™ Power](https://www.precor.com/en-us/commercial/cardio/indoor-cycling/spinner-chrono-power)
1. [Schwinn IC4](https://www.schwinnfitness.com/ic4/100873.html)
1. [Schwinn IC8](https://global.schwinnfitness.com/en/ic8/100893.html)
1. [Bowflex C6](https://www.bowflex.com/bikes/c6/100894.html)
1. [CyclBar spinning](https://www.cyclebar.com/) studio's [Schwinn AC Performance Plus](https://www.amazon.com/AC-Performance-Plus-Indoor-Cycle/dp/B002KV942W) through the [MPower Echelon2 console's CSV workout file's import]({% post_url 2020-09-23-schwinn-ac-performance-plus-support %}).

Any other fitness equipment that users request and is accessible to the developer for integration analysis could possibly be targeted in the future. The fitness equipment has to support [Bluetooth Low Energy](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy) protocols and either supply speed reading or distance data for the GPS emulation feature.

For more technical details about the app and motivation behind it [see my personal blog post series](https://csaba.page/blog/track-my-indoor-exercise.html).
