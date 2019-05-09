# AOSUILite.framework
AOSUILite.framework, which is required to run KeyRecoveryAssistant

This is a collection of AOSUILite.framework for all of the different versions of macOS that I could find (10.10-10.14)
As far as I know, this only is needed to run KeyRecoveryAssistant.app

KeyRecoveryAssistant.app is built into Recovery HD, and it's purpose it to help disable the firmware password if you've forgotten the password (I think)

Below this is a guide on how to get and run KeyRecoveryAssistant.app
## SIP has to be disabled to follow this guide, to learn how to disable SIP, visit [here](http://osxdaily.com/2015/10/05/disable-rootless-system-integrity-protection-mac-os-x/)
Run these commands in terminal:

## defaults write com.apple.Finder AppleShowAllFiles YES
## killall Finder
## diskutil mount disk0s3
## cp /Volumes/Recovery\ HD/come.apple.recovery.boot/BaseSystem.dmg ~/Desktop/

Now mount BaseSystem.dmg, which is located on your desktop
Then go back to terminal, and type:

## sudo cp -r /Volumes/OS\ X\ Base\ System/System/Installation/CDIS/KeyRecoveryAssistant.app /Applications/KeyRecoveryAssistant.app

KeyRecoveryAssistant will now be located in your Applications folder. When you try to run it, you'll get a message that looks something like this:

# KeyRecoveryAssistant cannot be opened because of a problem.
## Check with the developer to make sure KeyRecoveryAssistant works with this version of macOS. You may need to reinstall the application. Be sure to install any available updates for the application and macOS.
## Click Report to see more detailed information and send a report to Apple.

This is perfectly normal. To run KeyRecoveryAssistant, you need AOSUILite.framework
Download the AOSUILite.framework.zip file from the folder that matches your macOS version
## This next part is asuming that AOSUILite.framework.zip has been downloaded to your ~/Downloads/ folder, and has been unziped

Run this command:

## sudo mv -r ~/Downloads/AOSUILite.framework /System/Library/PrivateFrameworks/AOSUILite.framework

## After you push enter, terminal will ask for your password. Enter it, and then push enter.
