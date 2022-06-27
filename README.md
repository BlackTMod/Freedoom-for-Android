# SDoom for Android
<img src="icon.png" width="200" hspace="10" vspace="10"></br>

A fork of nvllsvm's GZDoom-Android port.
My idea for this fork was to upgrade nvllsvn's GZDoom-Android port, fix the C/C++ engine bugs and the java app bugs, and combine it with the open-source Freedoom (freedoom1.wad and freedoom2.wad) assets to publish a completely open source android game running on the doom engine.

This "bundling" has allowed it to reach a more diverse audience of users whom either don't own Doom or are averse to having to find and copy their legally-owned Doom resource files onto their phones. It has reached over 1,200,000 downloads on the Play store.


Due to changes with the Google Play store, I have been unable to distribute my last update for this app on the Play store. The update contained a newer version of the Freedoom wad(s) and some language fixes, and is available on GitHub.

Due to the deprecation of the build tools for this app, I have stopped active development. Please check out the GitHub and let me know if you are interested in taking over this project. 

While this app will remain free and highly functional for most users, please also check out Beloko's 'DeltaTouch' as an alternative.


### Help translate!
https://www.transifex.com/krupczakorg/freedoom-gzdoom/dashboard/


## Download
Play store link of the original app:
https://play.google.com/store/apps/details?id=net.nullsum.freedoom

APK release:
https://github.com/mkrupczak3/GZDoom-Android/releases

Ember's Unofficial F-Droid Repo:
https://fdroid.heartshine.xyz/

(I have not verified this repo myself for security. At the time of writing, my latest release [v0.4.3] should have a [sha256](https://en.wikipedia.org/wiki/SHA-2) hash of [43c94079d78ed2dffb90e521ffcc74364706fb8e334ba55f15b43168450625c6](https://twitter.com/Matts_Bytes/status/1273065495961513985?s=20))


## Why Freedoom?
While the Doom engine and its many spin-offs are open-sourced, most of the Doom's "assets" such as textures, sounds, and game levels are copyrighted and not legal to redistribute.
The Freedoom project offers an alternative set of assets and game levels that are open-source and can be used with most Doom engines in place of the originals.
In addition, Freedoom is compatible with much of the vast library of fan-made "WADs" (i.e. game levels) as indexed in the idgames archive.

## Dev Blog (how I made this):
https://matthew.krupczak.org/2019/10/20/hawking-my-projects-ii-500000-installs-with-freedoom-for-android/

## Links to the freedoom community:
[Freedoom official Github](https://github.com/freedoom/freedoom)


[Freedoom forums (for the Freedoom project, not Freedoom for android)](https://www.doomworld.com/forum/17-freedoom/)

## "Third-party" library versions used (update this whenever they are updated)
- [GZDoom Engine](https://github.com/coelckers/gzdoom): [2.0.02/2.0.03](https://github.com/coelckers/gzdoom/tree/df1364e2d7bc3f23a1a3b7afb4c0be731fe080f8) (super ancient)
- [Fluidsynth](https://github.com/FluidSynth/fluidsynth): 1.0.9
- [SDL](https://www.libsdl.org/): 1.3(?)


## Roadmap (not in order)
- [ ] Add arm64 support to satisfy August 2019 Google Play requirements
- [ ] Add a simple download wad from URL fragment like so: https://github.com/mkrupczak3/Freedoom-for-Android/blob/master/Notes8_1.png
- [ ] Integrate an idgames level browser/downloader
- [ ] Update FluidSynth from 1.x.x to 2.x.x
- [ ] Update SDL (and SDLActivity.java) from 1.x to 2.x.x
- [ ] Update [OpenGL ES](https://developer.android.com/guide/topics/graphics/opengl) from 1.0/1.1 to 3.1 (supported by Android 5.0 (API level 21) and higher)
- [ ] Switch from using [nvllsvm's MobileTouchControls](https://github.com/nvllsvm/MobileTouchControls) (which is archived, and also a fork of beloko's) to [beloko's](https://github.com/emileb/MobileTouchControls)

## Notes before building
A large portion of this project relies on the Android Native Development Kit (NDK) to compile C++ and C code from GZDoom and other sources for use with this app.
You may need to install additional tools in your development environment before being able to build these portions successfully.
For more information, please read the "Getting Started with the NDK" article from Google.
To my knowledge the environment only compiles towards the ARMV7 architecture as found in smartphones and not towards x86 as found in most traditional computers.
You may need to add support for x86 compilation or emulate the ARMV7 architecture to get this app working on a virtual device.


## Building
If you are running Windows, you may need to execute some of these commands using the Cygwin environment to avoid unexpected behavior.
If you install Cygwin on Windows, you should make sure that the "patch" command is installed with the environment.

You may also need to add your NDK folder to your PATH or add/remove a .bat extension from a command in build.sh depending on your platform.


### Building (cont.)
    git submodule update --init
    ./build.sh
    ./gradlew assemble


### Credits
Thanks to:
- Andrew Rabert (nvllsvm) for your amazing work on the GZDoom-Android fork.
- Emile Belanger (Beloko Games) for his work on D-Touch and the rest of the OpenGames suite.
- The Freedoom authors for an excellent set of open-source assets. Please also look at /doom/src/main/assets/CREDITS.txt for a more complete list of these contributors.
- Anyone else I haven't mentioned


### Disclaimer
This project is not affiliated with Doom or its publishers, Id Software or parent companies, or Bethesda.
This project is not officially endorsed by the Freedoom project or GZDoom project.


## License
Freedoom is released under a BSD-like license which can be found under /doom/src/main/assets/COPYING.txt. Most other code is GPL'd.
