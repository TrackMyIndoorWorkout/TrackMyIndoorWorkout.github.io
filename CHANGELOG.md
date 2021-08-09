---
layout: page
title: ChangeLog
permalink: /changelog/
---

## 1.1.81

* Adding help overlay to scanning, workout recording, and activity list screens
* Adding a changelog button to the About screen

## 1.1.80

* Correcting Strava sync delay
* Changing data connection check endpoints from Strava's Amazon AWS EC2 server IPs to default, which
  means Google, CloudFlare, and OpenDNS DNS servers
* Fixing Schwinn 510u support, making manufacturer check more lenient (less stringent)

## 1.1.79

* Transforming some colors (on the graph and on the track visualization) opaque for possible
  speedup
* Foundations for Cross Trainer / Elliptical support
* Option to display distance in kilometers or yards by introducing "distance resolution" orthogonal
  switch besides the unit system metric / imperial

## 1.1.78

* Adding back logic to infer sport by connecting to the device and deducting it from the
  FTMS characteristics. Some consoles don't implement Advertisement Data's Service Data which
  normally signals in a bitfield what type of machine it is
* Plugin step version updates
* Increase Schwinn IC4/IC8, BowFlex C6 default calorie factor from 1.4 to 3.6. This will result
  in a closer measurement to the console. Any user who has a calorie tune established should delete
  the tune or adjust it!
* Preparations for upcoming SUUNTO and Training Peaks integration

## 1.1.77

* Adding fix for auto connect error (application not responding)
* Adding fix for auto connect bug when it's impossible to navigate away from the recording screen

## 1.1.76

* Better graph axis and text colors for light theme graphs
* Recording screen Help button would open About screen just as on other screens
* About screen contains separate button for Quick Start, FAQ, Known Issues entries

## 1.1.72

* Adding recording Start / Stop button into the menu (besides it being in the top right corner)
* Small step version plugin updates

## 1.1.71

* Display the sport icon for the fitness machines on the scan screen instead of the transmission
  signal strength dB level
* Making scan result more compact (font size decrease)

## 1.1.70

* Data connection check preferences bug fix (was not reading the right value)
* Recognizing Schwinn 130 / 170 / 510u specifically by name instead of a generic FTMS bike
* Swap the order of Leaderboard and Zone Preferences button in the preferences hub
* Preferences wording change: persist -> record
* Reverting back to official pref plugin after my PR was merged

## 1.1.69

* There was a bug which caused elapsed time to be 0 seconds
* Minor corrections to CSV import
* TCX export will contain 7 precision digits only (no need for more) for space saving
* Adding source code linting, correct some linter findings
* Adding CSV export (proprietary format which is an enriched MPower Echelon2 format)
* Adding support to import the proprietary CSV format
* Adding CSV import type picker since now it can be either MPower Echelon2 or application migration

## 1.1.68

* Fixing GPS track generation algorithm. It left gaps at the end of the straights.
* Adjusting some GPS track factors.
* Sport change is possible for superusers (debug mode)
* Adding track for Elliptical and Star Stepper
* Adjusting the Marymoor field measurements

## 1.1.67

* Better UX when connecting (transitioning from the scanning screen to the recording):
  displaying beating hour glass
* Use FTMS Advertisement Data's Service Data to determine FTMS Machine type, so no pre-connection
  needed any more for generic devices
* Recognizing KayakPro devices also by "KP" bluetooth name prefix, not just "KayakPro"
* Fixing jumping dot color on the HRM management bottom sheet
* Decrease artificial intermittent delay during bluetooth initialization hoping for shorter splash
* Rate limiting small code refactor

## 1.1.66

* Fix bug with Simpler UI turned on while being on light theme. Also happened with old Android
  devices by default.

## 1.1.65

* Running Cadence Sensor support progress
* Preventing the display of extreme high pace (very low speed) on the recording screen (essentially
  utilizing slow speed settings there as well)
* Scan logic change: no more periodic polling of connected devices. We keep track of them
* Increase minimum scanning duration to 6 seconds
* Adding support to NPE Runn treadmill smart device
* Cycling Cadence Sensor logic fix
* Avoid displaying "null" on the recording screen, default is "--"

## 1.1.64

* Moving About from the Preferences hub to stand-alone screen and be invoked by the help button
* Slight font size decrease to accommodate smaller devices
* Lot of code refactoring

## 1.1.63

* White screen ANR (Application Not Responding) error when theme is light. (palette color crashed)

## 1.1.62.

* Supporting heart rate based calorie counting: needs configuration of weight, age, and gender
* Even more precise heart rate based calorie counting if VO2max is supplied (in configuration)

## 1.1.61

* Changes to permission and bluetooth enablement check and help logic during startup
* Remove Exit button (cannot really kill the app due to technical limitations and the app staying
  in the background may keep holding paired devices and preventing them from discovery)
* Step version bump of plugins

## 1.1.60

* Running Cadence Sensor support foundations
* Preventing kicking off simultaneous scanning
* Changing the scan discovery logic

## 1.1.59

* Cycling Cadence Sensor feature flag interpretation fix
* Support 16 bit value Heart Rate Monitors (like Wahoo TICKR)
* Bluetooth connection code related changes and refactorings
* Bluetooth scanning changes (remove stream peeks to not drain the stream)

## 1.1.58

* Bluetooth scan: display text when there's no available device
* Heart Rate Monitor scanning UX enhancements for re-scanning

## 1.1.56

* Upgrading all plugins and the codebase to Sound Null Safety, huge code churn
* Required new preferences library
* Required new charting library

## 1.1.54

* Disconnecting from HRM if already connected
* Move filter devices settings from UX to the Expert settings
* Shrink font a little in some places to support smaller devices better
* Scanning logic changes

## 1.1.53

* Styling the ranking info / pace light feature on the track visualization
* Fix bug for a leaderboard switch combination

## 1.1.50

* Adding pace light / rank visualization to the track
* Using my own version of the circular menu plugin code

## 1.1.49

* Adding Exit button to the Find Devices and Activites screen (unfortunately it does not really
  kill the app all the way)

## 1.1.46

* Weight rememberance option for preserving weight default at Spin Down start
* Workout will be forcefully finished upon connection loss

## 1.1.45

* Android 5 splash screen error fix (blind fix based on Play Store crash report)

## 1.1.44

* Add option to color the measurements by the zone index

## 1.1.43

* First open beta version after many closed beta

## 1.1.42

* Last closed beta before the open beta track
* Generic FTMS machine support enhancements
* There's no more heart rate flicker when connecting HRM directly to the app
* Automatically restart workout when data connection watchdog is triggered
* More contrast in the pie charts
* White text annotation on the graphs in dark theme mode

## 1.1.41

* Fix URL opening problems (like help page) with Android API 30+ devices (Android 11 and up)
* Sport picker, export format picker and battery status bottom sheet should be dismissible
* Bringing back splash screen
* Remove the debug ribbon even in debug mode
* Generic FTMS support foundations
* Dark / light theme support

## 1.1.40

* Zone index display feature and its settings
* 1-based leaderboards instead of 0-based
* Track marker annotation centering and other fixes
* Rank display corrections
* Build number will match the step number starting from that version

## 1.1.30

* Build number 39
* Styling leaderboards
* Pace light visual feedback
* Audio alerting feature adjustments
* Correct speed display on the recording details screen
* Leaderboard and pace light preferences
* HR alerting feature (color / visual, and audio)
* Target heart rate settings
* Dividing preferences into sub pages

## 1.1.29

* Build number 38
* Supporting split screen mode (for landscape split screen, no distinct landscape mode yet)
* Some foundations for Treadmill support
* Extended tune would affect Rower / Kayak / Swim ergometers
* Calorie Tune and Power Tune feature development
* Fixing bug in FIT export

## 1.1.28

* Build number 37
* Remove splash screen
* Remove portrait restriction to prepare for split screen support
* Bluetooth state and location permission handling changes
* Full screen mode during workout measurement to avoid accidental navigation
* Remove compression switch for export. Gzip confused users, only allow uncompressed downloads,
  uploads will still use gzip for Strava

## 1.1.27

* Build number 36
* Introducing permission_handler to help with location permission handling and enablement
* Bluetooth enablement handling changes

## 1.1.26

* Build number 35
* Calorie scale correction for FIT export

## 1.1.25

* Build number 34
* Introduce bluetooth_enable plugin specifically to handle bluetooth enablement condition
* FIT file export is introduced
* TCX sport export bug fix
* Heart rate limiting feature (capping the display and recording), various choices
* Heart rate data gap bridging changes
* Making data connection check endpoints configurable
* Slow speed configuration
* Sport based last used fitness machine rememberance logic
* Per sport based Zone configurations
* Accordion icons are not present when in Simpler UI mode
* Own fork of flutter_blue with one production crash avoidance code (blind fix)

## 1.1.24

* Build number 33, second closed beta release
* Multi sport device support (for example Genesis Port), sport picker UI
* Flipped zone coloring for pace based sports, flipped Y axis

## 1.1.23

* Build number 32
* FTMS Rower Machine support
* Support KayakPro Genesis Port enabled devices like, Compact, SpeedStroke Pro, SwimFast
* Paced based sport support
* Supporting HRM pairing directly to the app (instead of the console)
* Specific tests for supported devices
* FTMS Spin Down (machine calibration) support
* Data connection check test is using Strava's 6 AWS IP addresses

## 1.1.21

* Build number 30
* Plugin version upgrades
* Aerodynamic drag will limit the speed by power calculation
* Speed selection values respect unit preferences

## 1.1.18

* Build number 27
* Don't generate the cycling into the velodrome to avoid Strava KOM takeovers. Placing rides onto
  a running track (no cycling segments there) and similarly the run into the velodrome (no run
  segments)
* Allow resize of the graphs by long press. Saved into the settings
* Adding zone boundary lines
* Remove Y axis labels

## 1.1.17

* Build number 26
* Trying to tackle Plugin Not Found error

## 1.1.16

* Build number 25
* Using File Picker plugin for file imports
* Place running GPS track onto the Hoover track (no run segments)

## 1.1.12

* Build number 21
* Initial version of Schwinn AC Performance Plus support via MPower Echelon2 CSV saves

## 1.1.11

* Build number 20
* Introducing Roboto Mono font as an alternative for 7SEG and 14SEG
* More concise service data and UUID displays: just the 4 hex part which matters

## 1.1.10

* Build number 19
* Automatic activity uploading optional feature, UI configurable switch
* More consistent Strava icons, actions
* Introducing auto scanning and instant workout features

## 1.1.9

* Build number 18
* Device scan result styling
* Don't even bother with non connectable devices, like a Garmin watch
* Trying to fix crash on ancient Samsung S4 tablet seen in the play store reports

## 1.1.6

* Build number 15
* Bugfixes and emergency release due to flutter_blue white screen ANR (Plugin Not Found exception)
* Rolling back flutter_blue from 0.7.3 to 0.7.2, nuking Android port, etc.
* Package upgrades

## 1.1.5

* Build number 14
* Strava upload bug hotfix (feature code interfered with production code)
* Trying to blind fix some errors seen in Play Store reports

## 1.1.3

* Build number 12
* Coloring the Circular FAB icons
* Jumping dots feedback about scanning
* Strava sync bugfix attempt (by using broadcast streams)

## 1.1.2

* Build number 11
* Changing Strava token logic
* Strava sync REST HTTP handling code changes
* Some preferences options for UI enhancement
* Coloring of Pie Charts fixed
* Rounding cosmetic ugliness fixed
* Disable chart animations
* Simplified UI feature fixes
* Bug fixes

## 1.1.0

* Build number 9
* Schwinn IC4, Schwinn IC8, Bowflex C6 support
* Precor distance measurement handling modification
* Still tackling HTTP errors seen in the Play Store reports
* Change action button colors of the circular FAB
* Bug fixes

## 1.0.7

* Build number 8
* Introducing Circular FAB menus
* Being able to switch between imperial and SI units
* Replace histogram charts with pie charts
* Activity list refresh logic (for example after deletion)
* Average and maximum display on the workout details
* Interactive time series graph: selection value is displayed
* Visual feedback about Strava upload result
* Package upgrades

## 1.0.6

* Build number 7
* Fix false error snack bar while upload is actually successful

## 1.0.5

* Build number 6
* Correct distance calculation of the GPS points
* Preparing to support multiple devices (Schwinn IC4 besides Precor Spinner Chrono Power)
* Toggleable device filtering

## 1.0.4

* Build number 5
* Transient error fix during the workout start
* Using unit systems on the Records and the measurement screen
* Enhancing threshold & zone preferences UX
* Correcting histogram percent scaling

## 1.0.3

* Build number 4
* Real time colored graphs during workout measurement!

## 1.0.2

* Build number 3
* Zone bands display on the graphs
* Zone based binning of the histogram
* Fixing issue with Flutter ListUtils
* Adding Workout details screen with graphs

## 1.0.1

* Build number 2
* Add Help button, pops up the browser with the Quick Start page of the app
* Rebranding (Track My Indoor Exercise -> Track My Indoor Workout)
* UX debugging feature
* Display track visualization at the bottom
* DSEG7 and DSEG14 display fonts for retro look
* Also using VT323 font for even more retro look where DSEG7 is not usable
* Activity deletion feature (list doesn't refresh yet)
* GPS calculation corrections
* GPS is only calculated during upload
* TCX export support
* Wake lock on the measurement screen (must avoid device going to sleep)
* Adding wake lock package

## 1.0.0

* Build number 1
* Starting off of Flutter Blue example app
* Precor Spinner Chrono Power support
* GPS calculation logic
* Strava integration
* TCX format export and upload support