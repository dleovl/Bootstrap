# roothide Bootstrap FAQ

**Public downloads are officially out!** Grab your `.tipa` [here](https://github.com/roothide/Bootstrap/releases) (and only here to avoid malware)!

If you want something added/revised here, make a pull request or message me on Discord (@dleovl).

DO NOT UPDATE YOUR PHONE NO MATTER WHAT!
SpringBoard tweaks *DO NOT WORK* currently by any *OFFICIAL* means. This also includes tweaks that rely on daemons. Refer to this FAQ for tools you can use that enable SpringBoard support.

**Has this repository helped you out? Give [this repo](https://github.com/dleovl/Bootstrap) a ⭐️ if so!**

[Join the roothide Discord server](https://discord.com/invite/scqCkumAYp)!
If you have an issue that isn't listed here, check the [issues](https://github.com/roothide/Bootstrap/issues). If it's still not there, ask in the [roothide Discord server](https://discord.com/invite/scqCkumAYp).

## Table of Contents
- [Bootstrap](#bootstrap)
- [Tweaks](#tweaks)
- [Technical](#technical)
- [Other](#other)
- [Credits](#credits)

## Bootstrap
- [Back to Table of Contents](#table-of-contents)
#### Do I need TrollStore for this bootstrap?
YES! No TrollStore = Unsupported. No ifs, ands, or buts.
If you are on a supported version to install TrollStore, use [this guide](https://ios.cfw.guide/installing-trollstore/) to install TrollStore.

### How do I build the roothide Bootstrap? (No PC/Mac required)
Got a Mac and wanna use Xcode? [Use this README](https://github.com/dleovl/Bootstrap/blob/readme/README.md).

If not, check [here](https://discord.com/channels/1130859165942829106/1130859166488076331/1190488974528106607) for instructions on building with GitHub actions (must be in the [roothide Discord server](https://discord.com/invite/scqCkumAYp), this is also good for getting really crucial information). This `.yml` doesn't automatically update to the latest commit when a new one comes out, so you'll need to sync your fork every time a commit is made (it'll automatically build within 6 minutes). 'Error: Process completed with exit code 8.' means roothide Theos failed to install, manually dispatch the workflow again.

### How do I update the Bootstrap?
**You don't need to do anything** besides rebooting, installing the new `.tipa`, and bootstrapping for **minor revision changes** past public 1.0.

For updating between major beta versions, you may have to uninstall your bootstrap before updating. This isn't always a requirement for minor version revisions, but ensure you decrypt Bootstrap with [TrollDecryptor](https://github.com/wh1te4ever/TrollDecryptor) if you want to backup your build without cloning a commit.

You can export sources and tweaks in Sileo, preferences outside of $(jbroot) should be saved through uninstallation.

Disable everything in App List, reboot, uninstall the bootstrap in the app, install your new `.tipa`, and bootstrap.

If you updated the Bootstrap before reading this, uninstall from within the app, but make sure to Bootstrap **immediately after**. Refer to this FAQ for proper uninstallation instructions, you'll need to enable (if nothing is enabled) then disable every application you had injected and do a *proper* uninstall. Your injected applications may cease to function if you update the bootstrap while a major revision was made behind the scenes without first disabling them.

### Why are notifications broken / apps always asking for permissions?
Check out [issue #2](https://github.com/roothide/Bootstrap/issues/2) for the technical answer. This issue should have been fixed as of 1.1.0, but if it persists, make an issue on the `roothide/Bootstrap` repository. As of 1.1.0, notifications are programmatically fixed.

### How do I uninstall the Bootstrap?
If you're uninstalling because of any bugs, let us know in the [GitHub issues](https://github.com/roothide/Bootstrap/issues). This will revert any SpringBoard injection tools.

You may want to backup your sources and tweaks. You can do this in Sileo by clicking the share button in the top-left corner of both the Sources and Installed tabs. You can copy and paste this list into your Notes app for safe-keeping.
1. Disable EVERYTHING in App List.
2. `(Optional, *please read in its entirety*)` If you're forever leaving the Bootstrap, open the roothide application (`com.roothide.manager` in Sileo if it isn't installed, must be bootstrapped), click varClean from the bottom tabs, press 'Select All', and press 'Clean'. This will remove ALL jailbreak related files from `/var`. **You may experience issues with jailbreak detection in the future if you do not remove these files. Unfortunately, this may also remove files utilized by other TrollStore applications. Ensure not to remove these if you want to continue using them where they were left off.**
4. Reboot your phone.
5. Open Bootstrap and press uninstall.

Thank you for staying with us.

## Tweaks
- [Back to Table of Contents](#table-of-contents)
### How do I get SpringBoard tweaks to work?
Currently, only one unofficial method for SpringBoard injection is available:
- [Serotonin](https://github.com/mineek/Serotonin): A semi-non-ish-jailbreak tool that works on top of roothide Bootstrap to provide partial support for SpringBoard tweaks

Refer to this FAQ for proper uninstallation instructions (reverting Serotonin / switching from kfdmineek).

### How do I convert tweaks?

## Install tweaks
When installing a tweak, you might see a message saying 'Not Updated'. This tweak will need to be updated to support the roothide Bootstrap.

Install roothide Patcher (https://roothide.github.io/, refresh sources if it's blank).

If you're using Sileo:

- When attempting to install a rootful/rootless tweak, press 'Convert'. In the share sheet, press the Patcher app.

If you're using Zebra:

- Zebra only shows roothide tweaks, so you aren't able to install rootful/rootless tweaks without the deb file. Download the deb of the tweak you want to use (you can use [PostBox](https://postbox.news/) for rootful repos), export the deb to the Patcher, and install with Zebra.

When you convert a tweak, you'll need to directly convert simple tweaks for **rootful** tweaks and use the **rootless compat layer** for **rootless** tweaks (install rootless-compat as a dependancy).

Once the tweak is converted, press Ok and press your package manager from the share sheet. Add the tweak to your queue and run the queue.

### Cask 3 doesn't save settings!
Install [this fixed .deb](https://cdn.discordapp.com/attachments/1153426136802529280/1190903773606973470/com.ryannair05.cask3_1.0.2_iphoneos-arm64e.deb) with Sileo (pre-converted) (you may need to be in the [roothide Discord server](https://discord.com/invite/scqCkumAYp) for it to load)

### Cask 3 doesn't work in Discord / other apps
These apps will need to be decrypted and have an unsandbox entitlement like `get-task-allow` to allow the tweaks like Cask 3 to work. If this is too technical, ask in the [roothide Discord](https://discord.com/invite/scqCkumAYp).

### '**tweakname** tweak doesn't work, why?'
Some tweaks are currently not supported. This can either be due to lack of daemon support, or a poorly written tweak that has manual paths.
These are some examples of incompatible tweaks:
- iCleaner (Pro): Support for daemons is required.
- Crane (Lite): Support for daemons is required, though you can manage through Preferences if you are **100%** sure you know what you're doing. Follow [this guide](https://github.com/roothide/Bootstrap/issues/11#issuecomment-1873340249) for instructions on how to use it within Preferences.
- Aemulo: Support for daemons is required.
- Flex 3 Beta: This application breaks `com.apple.Preferences` when injected if you have it alongside PreferenceLoader. Use the [updated version](https://twitter.com/Dxcool223x/status/1741169030340243520).
- iGameGod: Installing this tweak as an application (through Sileo) doesn't work because iGameGod only supports injection into 'User' applications. Use tweaks from [iOSGods](https://iosgods.com/) instead.

### How do I change tweak settings?
You have two solutions:
1. Enable injection into `com.apple.Preferences` (please be wary that you are injecting into a system application, do this at your own risk) and install PreferenceLoader along with a tweak that has a preference bundle (ex. ShowTouch).
2. Use TweakSettings by CreatureSurvive on the [CreatureCoding repository](https://creaturecoding.com/repo/) and respring for it to show up. **This is the safest alternative to people who DO NOT want to inject into system applications. While nothing bad will happen when injection system applications, you may use this as a safe fallback option.**

## Technical
- [Back to Table of Contents](#table-of-contents)
### Why do applications claim I'm still jailbroken?
Coming from a previous jailbreak, refer to #2 in the uninstallation guide in this FAQ to remove all jailbreak related files in `/var`.

**Do not install Filza from roothide's repository in Sileo.** If you installed Filza through TrollStore, replace it with the [no URL scheme version](https://tigisoftware.com/download/Filza_NoURLScheme_4.0.0.ipa). Make sure you don't have Filza enabled in the App List (unless you benefit from this, please test if injection into Filza helps with detection for you specifically).

If your application still persists, attempt to uninstall it completely (disable injection first) and reinstall from the App Store.

You can report bad applications in [issue #48](https://github.com/roothide/Bootstrap/issues/48), please comment the link to the App Store landing page and how to reproduce the jailbreak detection warning (do you need to login?)

### Can I use JIT?
JIT by default works with applications specifically made to support JIT provided by TrollStore, but you can enable JIT for outdated applications by using the bootstrap if you don't want to inject with [TrollStoreJitEnabler](https://github.com/Rednick16/TrollStoreJitEnabler). Enabling injection into applications that require JIT with App List will allow JIT to be utilized.

## Other
- [Back to Table of Contents](#table-of-contents)
### Why don't my apps say 'Open' in the App Store?
Applications injected in App List will not show up in the App Store. **DO NOT** click the cloud download button unless you **100%** know what you're doing.
To get it to say 'Open' again, disable injection in App List, and refresh icon cache in TrollStore.

### How do I disable OTA updates?
Turn off automatic updates in Settings, both iOS updates (installing and downloading) and security responses & system files. Delete any OTA update you have downloaded inside of Settings > General > i(Phone/Pad) Storage.

Install the [OTADisabler app from ichitaso](https://github.com/ichitaso/file/raw/main/OTADisabler_1.0.0.tipa) and disable OTA updates.

### Why don't my package managers have any URL schemes?
URL schemes are currently **disabled** to mitigate jailbreak detection. You will need to manually copy repository URLs and paste them into the package managers yourself.

### How do I enable developer mode?

TrollStore versions 2.0.9 and later can enable developer mode for applications that require developer mode. Alternatively, you can enable developer mode by sideloading any application, by using software like [Sideloadly](https://sideloadly.io/), [AltStore](https://altstore.io/), or Xcode.

### Why are my apps gone / not opening?
Because of how the bootstrap works, your injected applications may stop working or disappear.

For injected applications, you can either:
1. Disable injection and respring
2. Rebuild apps in Bootstrap

For TrollStore apps, you can either:
1. Refresh app registrations from your persistence helper
2. Refresh icon cache in TrollStore

Refreshing icon cache in TrollStore will make injected/Sileo installed applications disappear. Rebuild apps from within the Bootstrap app to make them appear again.

## Credits
- [Back to Table of Contents](#table-of-contents)

Thanks to everyone in the [roothide Discord server](https://discord.com/invite/scqCkumAYp) for making this possible!

♡ dleovl
