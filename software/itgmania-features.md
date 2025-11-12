---
title: ITGMania Feature Cheatsheet
description: 
published: 1
date: 2025-11-12T22:55:35.464Z
tags: 
editor: markdown
dateCreated: 2025-11-12T22:53:58.032Z
---

# ITGMania / Simply Love Feature Cheatsheet

ITGMania is the game engine officially supported by the ITG community for events such as ITL Online and Stamina RPG, and Simply Love is the officially supported theme included with it. On top of all the legacy StepMania features, there are a ton of options and shortcuts available, so it can be difficult to be aware of or find all the most useful ones. Some of the important/popular ones are outlined here.

## Main Menu Options

**Configure Keyboard/Pad Mappings**
- In addition to the things you'd expect in any dance game software, as of ITGMania 1.0, there is a bindable restart button, which works both during gameplay and on the evaluation screen.

**Input Options**
- Menu Buttons: Option to turn off pad navigation so you don't accidentally scroll standing around.
- Input Debounce Time: Can mitigate misfires by having a small window in which retriggers of a panel are ignored.

**Graphics/Sound Options**
- Global Offset: This is where your "sync" of the audio to the steps is set. If you're accurately timing to the beat but your timing is looking negative on the evaluation screen (hitting the beat is registering as early), you want to make this proportionately more positive (delaying the audio playback to bring it in line), and vice versa. It can also be adjusted during gameplay (detailed later).

**Visual Options => Appearance Options**
 - Center 1 Player: Puts your arrows in the middle of the screen if you're alone.
 - Translate Song Titles: If you can't read Japanese/Korean/etc. characters, this will transliterate them to Latin characters.

**Advanced Options**
- Default fail type: ImmediateContinue lets you keep playing the chart (without further opportunity to pass or score) after you fail.
- Profile Sort Order: Can make the profile select screen less inconvenient based on your needs.

**Simply Love Options**
- Visual Style/Rainbow Mode: Theme aesthetic adjustments.
- MusicWheel Scroll Speed: Scroll the songwheel faster.
- MusicWheel Style: IIDX lets you loop an open pack when you scroll past the end instead of scrolling to other packs.
- Preferred Style: Lets you skip the gameplay style select screen.
- Default Game Mode: If you want standard play, you probably want to set this to ITG.
- Allow Screen (various): Lets you disable a lot of the screens you have to press through between the main menu and the songwheel. If you disable the game mode select screen, you'll boot into the Default Game Mode you set.
- Keyboard Features: This enables things like song search and practice mode. You want to turn this on if you have a keyboard.
- Preview music loops: You can disable the preview music on the songwheel from replaying when you leave it alone.

**GrooveStats Options**
- Enable GrooveStats: Needs to be turned on to submit to and retrieve from online leaderboards and events, etc. You will also need to register for an account and either login with a QR code (below) or register your API key with your local profile by hand (see https://github.com/GrooveStats/gslauncher#setting-up-your-groovestats-api-key)
- Auto-Download Unlocks: Events like ITL or Stamina RPG allow you to unlock new charts through certain accomplishments. This will allow them to automatically download when unlocked rather than having to manually download them from the website.
- Separate Unlocks By Player: Option to keep track of what you unlock separately from what others who play on your setup unlock.
- Display GrooveStats QR Login: Option for people to be able to log into GrooveStats with a QR code instead of setting the API key in a text file for a profile. Be aware you need to keep the select profile screen enabled for this feature to work.

## Songwheel

Left + Right: Activates songwheel options. This includes a ton of useful stuff:
- Sorting and searching
- Practice mode
- Favorites
- Input test
- Loading new songs
- Checking unlock downloads
- Changing modes or profiles

Ctrl + Shift + R: Hard reload - useful if the chart has changed from when it was first loaded (i.e. if you edited it or downloaded an updated copy), as sometimes the old cache will interfere if you only use "load new songs".

Spin (e.g. Left, Down, Right, Up, Left): Add/remove chart to favorites

## Gameplay

F7: Assist tick
F8: Autoplay
Hold enter: fail to evaluation screen
Hold esc: back to songwheel

F6 twice: AutoSync Machine - this has the game automatically your global offset (audio) while you step as accurately to the timing of the beat as you can. It's important to press F6 TWICE if you use this feature, as pressing it only once will sync the specific chart you're playing, taking it away from its intended sync and rendering it useless for syncing to everything else. Make sure it says 'AutoSync Machine' on the screen when you're using this.
(Alt + ) Shift + F11/F12: Manually adjust your global offset. Using alt enables smaller changes. You can manually put in changes based on your average results or feel this way, which can be easier for some people to fine tune than using the automatic sync.

## Evaluation screen

F3 (held) => F6 => 2: Refreshes the evaluation screen, which will attempt to resubmit your score if the first attempt to submit failed.
Spin (e.g. Left, Down, Right, Up, Left): Add/remove chart to favorites

## Files and Folders

If you install the game normally, your saves, songs and various folders of things you might add to will be stored separately from the installation. This is convenient for persisting all your stuff when upgrading your ITGMania version.

 - Windows: `%APPDATA%/ITGmania` (shortcut for `{drive}:/Users/{username}/AppData/Roaming/ITGmania`)
 - Linux: `~/.itgmania`
 - Mac (ITGmania 1.2.0 and newer): `~/Library/Application Support/ITGmania`
 - Mac (ITGmania 1.1.0 and older): `~/Library/Application Support/ITGmania, ~/Library/Preferences/ITGmania, ~/Library/Logs/ITGmania, ~/Library/Caches/ITGmania, ~/Pictures/ITGmania Screenshots`

If you choose the portable install, everything will be stored together in the game installation directory. You can change any standard install into a portable install by adding a blank file called `Portable.ini`. On Mac and Linux, you can use the terminal command `touch Portable.ini` in the ITGmania directory to create a `Portable.ini`. To continue using your existing data, you will need to move your saved content into the ITGmania directory.

Within that main directory, you can find your profile in Save/LocalProfile/, probably associated with a long number. You can figure out if it's your profile by checking the DisplayName near the top of Editable.ini or Stats.xml. Here, you can find your scores (Stats.xml) and your in-game favorites file (favorites.txt).

### Favorites and Playlists

You can edit your favorites.txt to have extra subfolders in game by adding a line with the folder heading prefixed with ---. There is no functionality to edit within these in-game at the moment, adding a song to favorites just tacks it onto the end of the file, and removing a song from favorites removes it from everywhere in the file.

You can also have additional playlists, which have the same format as the favorites.txt, by storing other text files in a Playlists folder.