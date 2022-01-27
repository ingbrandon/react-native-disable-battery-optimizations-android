# react-native-disable-battery-optimizations-android

The act of requesting **REQUEST_IGNORE_BATTERY_OPTIMIZATIONS** in the manifest
is what may get you
[banned](https://commonsware.com/blog/2015/11/11/google-anti-trust-issues.html),
so it was remove.

# 🔥🔥 Upgraded and merged some fixes from other forked repos 🔥🔥

this is a fork of
https://github.com/IronTony/react-native-disable-battery-optimizations-android.

## Getting started

`$ npm i @dominicvonk/react-native-disable-battery-optimizations-android --save`

### Mostly automatic installation for react native >= v 0.60

Manual linking not required for above versions

For manual linking :
`$ react-native link @dominicvonk/react-native-disable-battery-optimizations-android`

### Manual installation

#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`

- Add `import com.reactlibrary.RNDisableBatteryOptimizationsandroidPackage;` to
  the imports at the top of the file
- Add `new RNDisableBatteryOptimizationsPackage()` to the list returned by the
  `getPackages()` method

2. Append the following lines to `android/settings.gradle`:
   ```
   include ':@dominicvonk/react-native-disable-battery-optimizations-android'
   project(':@dominicvonk/react-native-disable-battery-optimizations-android').projectDir = new File(rootProject.projectDir, 	'../node_modules/@dominicvonk/react-native-disable-battery-optimizations-android/android')
   ```
3. Insert the following lines inside the dependencies block in
   `android/app/build.gradle`:
   ```
   compile project(':@dominicvonk/react-native-disable-battery-optimizations-android')
   ```

## Usage

```javascript
import RNDisableBatteryOptimizationsAndroid from "@dominicvonk/react-native-disable-battery-optimizations-android";

RNDisableBatteryOptimizationsAndroid.isBatteryOptimizationEnabled().then(
  (isEnabled) => {
    if (isEnabled) {
      RNDisableBatteryOptimizationsAndroid.openBatteryModal();
    }
  },
);

// for direct whitelisting app with Instant Dialogue
// The user will be taken to a screen where they can indicate that they are willing to suspend portions of Doze mode effects on your app.
// Note: Play store will not allow using this method, and will allow only as an exception

RNDisableBatteryOptimizationsAndroid.enableBackgroundServicesDialogue();
```
