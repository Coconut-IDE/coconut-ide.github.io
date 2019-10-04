---
layout: default
---
# Coconut

Coconut is an Android Studio plugin that can help developers handle privacy.

The initial release of Coconut is described in the following paper:
>Tianshi Li, Yuvraj Agarwal, Jason I. Hong.
>"[**Coconut: An IDE Plugin for Developing Privacy-Friendly Apps**](/assets/pdf/coconut_paper.pdf)".
>In _Proceedings of the ACM on Interactive, Mobile, Wearable and Ubiquitous Technologies_, Volume 2 Issue 4, December 2018.

Check out our [UbiComp talk slides](/assets/pdf/Coconut-Ubicomp.pdf)

Pre-release alpha version download
----------------------------------
You can directly install the plugin in Android Studio using the pre-built jar: [0.0.1](https://github.com/Coconut-IDE/Coconut/releases/tag/0.0.1). It has been tested and worked fine for the latest Android Studio version (3.5)

Please refer to the "Install plugin from disk" section in the [official guide](https://www.jetbrains.com/help/idea/managing-plugins.html) for installing the plugin in IntelliJ IDEA/Android Studio.


How to build the source code
----------------------------

### Prerequisite
1. Install
- 1) Android Studio (for Android development and plugin testing, **recommended version: Android Studio AI-182.5107.16.33.5314842**, see [Android Studio download archives](https://developer.android.com/studio/archive))
- 2) IntelliJ IDEA (for plugin development)
2. Install the "Groovy" plugin in IntelliJ IDEA or Android Studio

### Steps to build and run the plugin
1. open the privacyhelperplugin project with IntelliJ IDEA
2. setup the IntelliJ Platform SDK. Go to File -> Project Structure -> SDKs, use the "+" button to add an IntelliJ Platform Plugin SDK and then select the right path in your Android Studio folder. See the screenshot below for details.

**Note:**
1. You need to manually add the Groovy plugin jars (in Groovy/libs) to the classpath of the SDK. See the last four jars in the screenshot below as an example.
2. Make sure you name the SDK: Android Studio AI-182.5107.16.33.5314842, otherwise you will need to modify ``PrivacyHelperPlugin.iml`` accordingly
3. Make sure you use the Jetbrains Java Runtime (JDK), which should be bundled with the Android Studio application (See [this post](https://intellij-support.jetbrains.com/hc/en-us/articles/206544879) for more information). You will need to create a new JDK with this path, then specify it for the "Internal Java Platform" in the SDK config (See the screenshot).

![How to set up Android Studio SDK](/assets/img/androidstudiosdks.png)
3. setup run/debug configuration. Go to Run -> Edit Configurations. Add a new configuration under the Plugin category. Make sure you select the right JRE. See the screenshot below.
![How to set up run/build configuration](/assets/img/runconfigurations.png)
4. select the configuration that you just created, and run/debug it (just as how you do that in Android Studio)

If done correctly, you should be able to see Coconut in your plugin list (Android Studio -> Preferences -> Plugins).

For a more comprehensive instruction, please refer to: https://www.jetbrains.org/intellij/sdk/docs/basics/getting_started/running_and_debugging_a_plugin.html 

Test Coconut on an example Android app
--------------------------------------
1. Download the [CoconutTest](https://github.com/Coconut-IDE/CoconutTest) project
2. Open the project with an Android Studio that has Coconut installed. Coconut will automatically initiate privacy inspection at the project start time.
3. If the project has incomplete annotations, the plugin will pop up a notification like this:
![privacy error notification](/assets/img/privacyerrornotifications.png)
4. Then you can use the PrivacyChecker tool window and quickfixes to add annotations to address these errors. You also need to import the annotation library jar to use these annotaions (available at [this repo](https://github.com/Coconut-IDE/CoconutAnnotationLib)).
![quickfix](/assets/img/quickfix.png)

Contributors
------------
* [Tianshi Li](https://tianshili.me) (Carnegie Mellon University)
* Mike Czapik (Carnegie Mellon University)
* Tiffany Yu (Carnegie Mellon University)
* Elijah Neundorfer (Columbus State University)

Faculty advisors
----------------
* [Jason Hong](http://www.cs.cmu.edu/~jasonh/) (Carnegie Mellon University)
* [Yuvraj Agarwal](https://www.synergylabs.org/yuvraj/) (Carnegie Mellon University)
