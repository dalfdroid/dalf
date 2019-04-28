# DALF: Permissions Plugins as Android Apps

DALF proposes a new flexible permissions architecture for Android. In DALF, users may install plugins to control how apps may access on-device data. For example, a user may install a plugin to prevent apps from accessing the device location at night. The key difference between DALF and related work, such as [Xposed](https://github.com/rovo89/Xposed), is that in DALF, plugins are regular, standalone apps. Plugins do not run with elevated privileges in the OS nor do they run within the address spaces of each app. For more information, please wait for the publication of our [MobiSys 2019](https://www.sigmobile.org/mobisys/2019/) paper.

At the moment, DALF is a research prototype that demonstrates the feasibility of our approach. Further work is required to integrate it with open-source Android ROMs and to expand the capabilities of plugins.

## Repo organization

This repository centrally tracks all project issues. Visit the main [dalfdroid](https://github.com/dalfdroid) organization page to view all project repositories.

## Building

DALF is built on top of AOSP (Android Open-Source Project), branch `android-8.1.0_r1`. This branch supports the following devices: Pixel 2 XL, Pixel 2, Pixel XL, Pixel, Pixel C, Nexus 6P, Nexus 5X. However, we have tested DALF only on the Pixel 2 XL device. If you test it on other devices, please feel free to open an issue to let us know your experience.

Please visit the [wiki](https://github.com/dalfdroid/dalf/wiki) for the complete build instructions.

## Writing plugins

Please visit the [wiki](https://github.com/dalfdroid/dalf/wiki) to view a guide on writing DALF plugins. We have also published some sample plugins:

- [GeoInd](https://github.com/dalfdroid/plugin_geoind): Uses [geo-indistinguishability](http://www.lix.polytechnique.fr/~catuscia/papers/Geolocation/geo.pdf), a differentially-private technique, to hide the user's current location.

- [ImageGuard](https://github.com/dalfdroid/plugin_imageguard): Uses techniques from [PrivateEye](https://users.cs.duke.edu/~animeshs/project/privateeye/privateeye.pdf) to hide sensitive content in image frames.

- [EmailGuard](https://github.com/dalfdroid/plugin_perturbemail): Hides email addresses of contacts when apps access the contacts book.
