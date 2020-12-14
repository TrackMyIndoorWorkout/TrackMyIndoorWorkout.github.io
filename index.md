---
layout: home
---
Track My Indoor Workout is an application to record virtual workouts including all the important metrics (power meter reading, cadence sensor, spent calories, heart rate, speed, distance) while also adding emulated GPS routes. Workouts can be synced to [Strava](https://www.strava.com/) for persistence, or [TCX files](https://en.wikipedia.org/wiki/Training_Center_XML) can be downloaded for ingestion into other ecosystems. One major motivation for the app was that some cycling oriented fitness challenges wouldn't count virtual rides without GPS data plus the Wahoo app didn't pick up the power meter and cadence readings.

The app calculates the GPS route based on the speed data and emulates circling laps in the [Jerry Baker Memorial Velodrome](https://velodrome.org/) in [Marymoor Park](https://www.kingcounty.gov/services/parks-recreation/parks/parks-and-natural-lands/popular-parks/marymoor/velodrome.aspx) in [Redmond, Washington](https://www.google.com/maps/place/Jerry+Baker+Memorial+Velodrome/@47.6659161,-122.1125076,96m/data=!3m1!1e3!4m5!3m4!1s0x0:0x7d3c1ebef878f4c!8m2!3d47.665894!4d-122.1126097). The current code will be able to handle any 400m tracks (and possibly even other length) in the future once that becomes configurable.

Currently the app supports the following fitness equipment:

1. [Precor Spinner® Chrono™ Power](https://www.precor.com/en-us/commercial/cardio/indoor-cycling/spinner-chrono-power)
1. [Schwinn IC4](https://www.schwinnfitness.com/ic4/100873.html)
1. [Schwinn IC8](https://global.schwinnfitness.com/en/ic8/100893.html)
1. [Bowflex C6](https://www.bowflex.com/bikes/c6/100894.html)
1. [CyclBar spinning](https://www.cyclebar.com/) studio's [Schwinn AC Performance Plus](https://www.amazon.com/AC-Performance-Plus-Indoor-Cycle/dp/B002KV942W) through the [MPower Echelon2 console's CSV workout file's import]({% post_url 2020-09-23-schwinn-ac-performance-plus-support %}).

Any other fitness equipment that users request and is accessible to the developer for integration analysis could possibly be targeted in the future. The fitness equipment has to support [Bluetooth Low Energy](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy) protocols and either supply speed reading or distance data for the GPS emulation feature. The IC4 support is based on standard BLE GATT protocol so potentially any equipment which follows that can be easily integrated. Wahoo devices are good candidates as well since [detailed specification is available](https://pdftoword-converter.online/amp/converted/f081c419/wahoo-fitness-equipment-profile/kh3srp96arydxyn0kvv0yzu7rdvvqqhigou38rxhpdf.pdf).

[For more technical details about the app and motivation behind it please see my personal blog](https://csaba.page/blog/track-my-indoor-exercise.html).
