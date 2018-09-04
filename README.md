# Adaptive Icons for Android
This project shows how to use [adaptive icons for Android](https://developer.android.com/guide/practices/ui_guidelines/icon_design_adaptive) builds. The Defold bundler doesn't yet support adaptive icons in game.project, but it's quite easy to configure the Android build to use adaptive icons anyway thanks to the fact that resources can be bundles "as-is" directly into the APK. This is achieved by adding a new entry `bundle_resources` to the `project` setting of game.project:

```
[project]
title = Adaptive Icon
bundle_resources = /assets/bundle
```

This will copy any files under `/asset/bundle/android` into the folder structure of the APK. The android manifest used by Defold expects the icon to exist as `@drawable/icon` and we use this fact to provide an `icon.xml` for all resolutions on Android API level 26 and above. The `icon.xml` is an adaptive icon resources which in turn references background and foreground images for the adaptive icon.

## Creating launcher icons
Useful tool for generating launcher icons in various sizes: https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html
