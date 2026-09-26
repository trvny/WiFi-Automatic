# WiFi Automatic
=============

[![license](https://img.shields.io/github/license/trvny/WiFi-Automatic)](LICENSE.md)
[![CI](https://github.com/trvny/WiFi-Automatic/actions/workflows/ci.yml/badge.svg)](https://github.com/trvny/WiFi-Automatic/actions/workflows/ci.yml)

This is a maintained fork of [j4velin/WiFi-Automatic](https://github.com/j4velin/WiFi-Automatic).
Upstream authorship and the fork's modifications are documented in [NOTICE](NOTICE).

This simple app can help you increase the standby time of your device: <b>WiFi Automatic</b> automatically disable your WiFi radio when you don't need it and thereby lowers the battery consumption.
It is designed to be used with WiFi-only* tablets - these devices normally don't require a constant internet connection if you're not using them and turning WiFi off can save a lot of battery power.

You can also specify to automatically turn on WiFi again, if you turn on your device. Also, the app can regularly scan for available networks to connect to and re-disable WiFi if no suitable network is found. This way, you are always connected to your WiFi network when using the device.

This app has a similiar effect like setting the "WiFi sleep policy" in Android to "always", except that you can now exactly define the timeout between turning the screen off and actually turning off WiFi.


*if your device has a cell radio, it might switch to 2G/3G which may consume more power then staying on WiFi


## Distribution

This maintained fork is built for F-Droid/source distribution and keeps `targetSdk 28` intentionally. Android 10 (API 29) stopped allowing apps targeting API 29+ to toggle Wi-Fi through `WifiManager.setWifiEnabled()`, while Google Play requires a much newer target SDK. Those requirements are incompatible with the app's core purpose, so there is no Google Play build.

The old location-triggered Wi-Fi feature has also been removed. It depended on Google Play Services geofencing and Maps, while the maintained build no longer carries a Play flavor.

## Application ID

This fork ships as `trvny.wifiautomatic`, not upstream's `de.j4velin.wifiAutoOff`.
It therefore installs **alongside** the original app instead of updating it, and settings from
an existing install are not carried over — uninstall the old one once you are happy with this
build. The Java package is still `de.j4velin.wifiAutoOff`, so this only affects the installed
package name, not the code.

## License and third-party materials

The project is distributed under [Apache-2.0](LICENSE.md). Third-party names,
logos, store listings and hosted images remain the property of their respective
owners. See [THIRD_PARTY_NOTICES.md](docs/THIRD_PARTY_NOTICES.md).

## Other stuff

[![feeds](https://github-stats-extended.vercel.app/api/pin?username=trvny&repo=trvny%2Ffeedseek&theme=great-gatsby)](https://github.com/trvny/feedseek)
