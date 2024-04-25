# roothide Bootstrap FAQ

[![GitHub stars](https://img.shields.io/github/stars/dleovl/Bootstrap?style=social)](https://github.com/dleovl/Bootstrap/stargazers)

**Public downloads are officially out!** Grab your `.tipa` [here](https://github.com/roothide/Bootstrap/releases) (and only here to avoid malware)

If you want something added/revised here, make a pull request or message me on Discord (@dleovl).

SpringBoard tweaks *DO NOT WORK* currently by any *OFFICIAL* means. This also includes tweaks that rely on or modify daemons. **Refer to this FAQ for unofficial tools you can use that enable SpringBoard injection.**

**Has this repository helped you out? Give [this repo](https://github.com/dleovl/Bootstrap) a ⭐️ if so!**

[Join the roothide Discord server](https://discord.com/invite/scqCkumAYp)!
If you have an issue that isn't listed here, check the [GitHub issues](https://github.com/roothide/Bootstrap/issues). If your issue isn't mentioned there, and you feel like it isn't good enough to make into a GitHub issue, feel free to ask in the roothide support channels!

## Table of Contents
- [Bootstrap](#bootstrap)
- [Tweaks](#tweaks)
- [Technical](#technical)
- [Other](#other)
- [Credits](#credits)

## Bootstrap
- [Back to Table of Contents](#table-of-contents)
### Do I need TrollStore for this bootstrap?
**Yes.** TrollStore is a requirement.

If you are on a TrollStore supported iOS/iPadOS, use [this guide from ios.cfw.guide](https://ios.cfw.guide/installing-trollstore/) to install TrollStore.

### How do I build the roothide Bootstrap? (No PC/Mac required)
Got a Mac and wanna use Xcode? Check out the `roothide/Bootstrap` README for build instructions.

If not, check [here](https://discord.com/channels/1130859165942829106/1130859166488076331/1190488974528106607) for instructions on building with GitHub actions (must be in the [roothide Discord server](https://discord.com/invite/scqCkumAYp). This `.yml` doesn't automatically update to the latest commit when a new one comes out, so you'll need to sync your fork every time a commit is made (it'll automatically build within 6 minutes). 'Error: Process completed with exit code 8.' means roothide Theos failed to install, manually dispatch the workflow again to fix it.

### How do I update the Bootstrap?
**You don't need to do anything** besides rebooting, installing the new `.tipa`, and bootstrapping for **minor revision changes** past public 1.0.

If you're coming from beta 3 or older, you'll need to uninstall the Bootstrap in its entirety. Refer to this FAQ for proper uninstallation instructions.

If you've updated the Bootstrap before reading this, uninstall the bootstrap from within the app, but make sure to bootstrap **immediately after**. Refer to this FAQ for proper uninstallation instructions.

### Why are apps always asking for permissions?
Check out [issue #2](https://github.com/roothide/Bootstrap/issues/2) for the technical answer.

### How do I uninstall the Bootstrap?
If you're uninstalling because of any bugs, let us know on [GitHub issues](https://github.com/roothide/Bootstrap/issues). Uninstalling will remove all files in `$(jbroot)`, even those that assist with SpringBoard injection.

If you're just reinstalling, you may want to backup your sources and tweaks. You can do this in Sileo by clicking the share button in the top-left corner of both the Sources and Installed tabs. You can copy and paste this list into your Notes app for safe-keeping.

If you're moving to a different jailbreak tool, you can still backup your sources (read last paragraph), but be wary of roothide alternative repositories. For example, the roothide Procursus repository should be removed from your source list before importing it to another jailbreak tool.

Here's how to perform a safe uninstall:
1. Disable EVERYTHING in App List. This is important, as to not break injected applications.
2. **Read this step in it's entirety before doing anything.** Open the roothide application (`com.roothide.manager` in Sileo if it isn't installed, must be bootstrapped), click varClean from the bottom tabs, press 'Select All', and press 'Clean'. This will remove ALL jailbreak related files from `/var`. **You may experience issues with jailbreak detection in the future if you do not remove these files. Unfortunately, this may also remove files utilized by other TrollStore applications. Ensure not to remove those files specifically if you want to continue using them where they were left off.**
4. Reboot your phone.
5. Open Bootstrap settings and press uninstall.

Thank you for staying with us.

## Tweaks
- [Back to Table of Contents](#table-of-contents)
### How do I get SpringBoard tweaks to work?
Currently, only one **unofficial** method for SpringBoard injection is available:
- [Serotonin](https://github.com/mineek/Serotonin): A **safe** semi-jailbreak tool that works on top of roothide Bootstrap to provide partial support for SpringBoard tweaks.

### How do I convert tweaks?
Install roothide Patcher (refresh sources if the roothide repository is blank).

If you're using Sileo:

- When attempting to install a rootful/rootless tweak, press 'Convert'. In the share sheet, press the Patcher app.

If you're using Zebra:

- Zebra only shows roothide tweaks, so you aren't able to install rootful/rootless tweaks without the `.deb` file itself. Download the `.deb` of the tweak you want to use (you can use [PostBox](https://postbox.news/) for rootful repos), and share the `.deb` to the Patcher app.

You'll need to use `Directly Convert Simple Tweaks` for **rootful** tweaks and use `Using Rootless Compat Layer` for **rootless** tweaks.

Once the tweak is converted, press Ok and share the `.deb` with your package manager.

Additionally, this prevents patched tweaks from being updated through Zebra. You will need to use Sileo to update (and patch) your tweaks.

### \*tweak name\* doesn't work, why?
Some tweaks are currently not supported. This can either be due to lack of daemon support, or a poorly written tweak that has hardcoded rootful/rootless paths that cannot be patched.

Here are some examples of known incompatible tweaks and why:
- iCleaner (Pro): Support for daemons is likely required. Install [iCleaner Pro](https://ib-soft.net/cydia/) and run `sudo icleaner` in a terminal.
- Crane (Lite): Crane / Crane Lite does not work, as support for daemons is required, though you can partially manage through Preferences if you are **100%** sure you know what you're doing. Follow [this guide](https://github.com/roothide/Bootstrap/issues/11#issuecomment-1873340249) for instructions on how to use it within Preferences. **Be wary, this method isn't supported by Crane, nor does this method do anything advanced, rather automates the swapping of the actual data of containers on its own.** This is nothing more you can achieve with Filza and does not contain any safeguards and extra features like the fully functioning tweak with `cranehelperd` would provide.
- Aemulo: Support for daemons is required.
- Flex 3 Beta: This application breaks `com.apple.Preferences` when injected if you have it alongside PreferenceLoader. Use the [updated version](https://twitter.com/Dxcool223x/status/1741169030340243520).
- Cask 3: This tweak needs to be properly updated for roothide, and to support sandboxed applications without entitlements like `get-task-allow`. You will need to manually add an unsandboxing entitlement like `get-task-allow` to applications you want to use Cask 3 in.

### How do I change tweak settings?
You have two solutions, either:
1. Enable injection into `com.apple.Preferences`. Nothing will show up if you do not have any tweaks that have preference bundles, or do not have PreferenceLoader installed.
2. Use TweakSettings by CreatureSurvive on the [CreatureCoding repository](https://creaturecoding.com/repo/). You will need to respring for the application to show up on your home screen.

## Technical
- [Back to Table of Contents](#table-of-contents)
### Why do applications claim I'm still jailbroken?
Coming from a previous jailbreak, refer to #2 in the uninstallation guide in this FAQ to remove all jailbreak related files in `/var`. This will wipe some tweak preferences, but *greatly* assists in mitigating jailbreak detection.

**Do not install Filza from roothide's repository in Sileo. Remove any Filza tweaks from Sileo.** If you've installed Filza through TrollStore, replace it with the [no URL scheme version](https://tigisoftware.com/download/Filza_NoURLScheme_4.0.0.ipa). Make sure you don't have Filza enabled in the App List, as this will hinder App Library and Music Library (unless you benefit from injection).

If your application still whines about a jailbreak, disable injection into the application, uninstall it, and reinstall from the App Store.

You can report picky applications in [issue #48](https://github.com/roothide/Bootstrap/issues/48). Please include the link to the App Store landing page and how to reproduce the jailbreak detection warning (do you need to login? do you need to press any buttons?)

### How do I utilize JIT?
JIT by default works with applications specifically made to support JIT provided by TrollStore. Enabling injection into applications that require JIT with App List will allow JIT to be utilized. This is mainly useful for enabling JIT outside of applications installed with TrollStore (as version 2.0.12 of TrollStore includes an 'Open with JIT' button).

## Other
- [Back to Table of Contents](#table-of-contents)
### Why don't my apps say 'Open' in the App Store?
Applications injected in App List will not show up in the App Store. **DO NOT** click the cloud download button unless you **100%** know what you're doing.
To get it to say 'Open' again, disable injection in App List, and refresh icon cache in TrollStore. You will need to do this if you are updating the application.

### How do I disable OTA updates?
Turn off automatic updates in Settings, both iOS updates (installing and downloading) and security responses & system files. Delete any OTA update you have downloaded inside of Settings > General > i(Phone/Pad) Storage.

Install the [OTADisabler app from ichitaso](https://github.com/ichitaso/file/raw/main/OTADisabler_1.0.0.tipa) and disable OTA updates.

If you're hesistant to use a TrollStore app to block updates, follow the [Blocking Updates guide on ios.cfw.guide](https://ios.cfw.guide/blocking-updates/).

### Why don't my package managers have any URL schemes?
URL schemes are **disabled** to mitigate jailbreak detection. You will need to manually copy repository URLs and paste them into the package managers yourself.

### How do I enable developer mode?
TrollStore versions 2.0.9 and later can enable developer mode for applications that require developer mode. Alternatively, you can enable developer mode by sideloading any application, by using software like [Sideloadly](https://sideloadly.io/), [AltStore](https://altstore.io/), or Xcode.

### Why are my apps gone / not opening?
Because of how the bootstrap handles injection, your injected applications may stop working or disappear on their own.

For injected applications, you can either:
1. Disable injection and respring
2. Rebuild apps in Bootstrap

For TrollStore apps, you can either:
1. Refresh app registrations from your persistence helper
2. Refresh icon cache in TrollStore

You will need to open the Bootstrap app and press Restart Server on every userspace reboot. You'll need to respring if this affects SpringBoard injection.

Refreshing icon cache in TrollStore will make injected/Sileo installed applications disappear. Rebuild apps from within the Bootstrap app to make them appear again.

### Archives directory is missing

***Please avoid using unofficial tweak patchers / piracy repositories as these can ruin the integrity of your jailbreak / device. Continuing to use these tweaks will cause the issue to reappear, please remove the tweaks and cease usage to prevent further problems.***
If you get an error saying the following:
```
E: Archives directory /var/cache/apt/archives/partial is missing. - Acquire (2: No such file or directory)
```
... follow these instructions:

#### roothide
If you have a terminal, run the following commands:
```
sudo mkdir -p $(jbroot)var/cache/apt/archives/partial
sudo mkdir $(jbroot)var/cache/locate
sudo touch $(jbroot)var/cache/apt/archives/lock
```
If you do not have a terminal, install [TrollStore Filza](https://tigisoftware.com/download/Filza_NoURLScheme_4.0.0.ipa), and follow these instructions:

1. Enter the directory `/var/containers/Bundle/Application/.jbroot-$(jbrand)/`, where `$(jbrand)` is a random string of hexadecimal characters. This directory will be referred to as `$(jbroot)`, remember it.

2. Recursively make the following folders:
```
$(jbroot)var/cache/apt/archives/partial/
$(jbroot)var/cache/
```
*If a folder is missing, for example `cache` is not in the `var` directory, make it. You need to end up with the directory structure intact.*

3. Enter `$(jbroot)var/cache/apt/archives/` and make a blank file named `lock`.

#### Rootless
While this is extra for a roothide FAQ, the instructions are the same as roothide, though `$(jbroot)` is simply `/var/jb/`. Change all instances of `$(jbroot)` to `/var/jb/` and perform the same steps. You must have a `sudo` password set to perform these commands.

## Credits
- [Back to Table of Contents](#table-of-contents)

Thanks to everyone in the [roothide Discord server](https://discord.com/invite/scqCkumAYp) for making this possible!

Additionally, thanks to the [r/Jailbreak Discord server](https://discord.gg/jb) members for giving useful insight / test results.

♡ dleovl
