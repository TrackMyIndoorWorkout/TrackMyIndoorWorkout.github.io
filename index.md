---
layout: home
---
Track My Indoor Workout is an application created so I can record virtual workouts including all the important metrics (power meter, cadence sensor, spent calories, heart rate, speed, distance) along with GPS track. One major motivation is that some cycling oriented Strava challenges won't count such virtual rides which don't have GPS data recorded.

For GPS route generation I selected a simple solution: I calculate that based on the current speed and emulate circling laps in the [Jerry Baker Memorial Velodrome](https://velodrome.org/) in [Redmond, Washington](https://www.google.com/maps/place/Jerry+Baker+Memorial+Velodrome/@47.6659161,-122.1125076,96m/data=!3m1!1e3!4m5!3m4!1s0x0:0x7d3c1ebef878f4c!8m2!3d47.665894!4d-122.1126097). The current code will be able to handle any 400m tracks (and possibly even other length), so in the future that can be configurable. Especially for BLE pairable treadmills this can be handy to position the GPS to a running track.

Currently the app supports the [Precor Spinner Chrono Power](https://www.precor.com/en-us/commercial/cardio/indoor-cycling/spinner-chrono-power) bike. I'm planning Schwinn IC4 support in the future, or any other device that users will request and I can get hold of them to reverse engineer the BLE protocol. The Wahoo application is unofficially capable of recording the Spinner Chrono Power workouts but it does not pick up the power meter and the cadence readings. My application has those and through Strava integration the workouts can be synced up or the generated TCX file can be downloaded.
