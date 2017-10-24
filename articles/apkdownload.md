---
layout: article
title: Dev Trick - Downloading APK to your laptop
permalink: /downloadapk/
comments: true
published: true
---

Quick 3 Step Process to download a 3rd party APK to your Mac or PC for Quick Analysis or sharing outside of the App store.

# Step 1: Find the path for the APK
* Easiest method is search for the App in the Appstore via your Chrome or Safari on ypur Mac/PC.
* The Package name will be in the URL of the App Detail page.

# Step 2: Find the path for the APK in your Android Device
*Note: This assumes you have an Android Device. There are Chrome plugin based or browser based downloaders if this is not an option. Be careful since some of these extensions can be malware.*

```
adb shell pm path <package-name>

```
# Step 3: Download the APK using the path identified in step 1
```
adb pull <path>
```

# For example let's try this with Facebook APK.

**Step 1:** Search facebook on Play Store and click the icon. The URL of the page loaded will have the package name.

```
https://play.google.com/store/apps/details?id=**com.facebook.katana**
```

**Step 2**: Get the path

```
terminal>adb shell pm path com.facebook.katana
package:/data/app/com.facebook.katana-1/base.apk
```
**Step 3**: Get the APK file
```
terminal>adb pull /data/app/com.facebook.katana-1/base.apk
/data/app/com.facebook.katana-1/base.apk: 1 file pulled. 5.0 MB/s (86909009 bytes in 16.531s)
```

Enjoy!
