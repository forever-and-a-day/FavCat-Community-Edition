# ❗ ---- Notice! ---- ❗
Someone who is better at coding than me (knows c# rather than me just coying lines of code based on what they look like they are doing) and made a fully patched, working FavCat here: https://github.com/anon54914/FavCat-Unlocked. This one won't be updated by VRCModUpdater.loader (the one I modded but hadn't uploaded yet won't update either, but it also won't load properly and breaks UIExpansionKit, which is required). I've skimmed though it very quickly after decompiling the binary dll and looking through the new commits, it and it looked okay to me, but I would *strongly caution* anyone to look through the code, make sure nothing creepy sneaked in, and build it yourself in Visual Studio. You may need to add a definition file and any missing structure folders like Libs and LibAlts from the original repo in order to build anon54914's version. Assuming all goes well, I will be archiving this repository soon. I would also like to reiterate, that, if you decide to use anon54914's mod, please, *please* consider supporting VRChat though a plus subscription. It will help ensure that VRChat survives, and maybe even improves! <3 

# FavCat Community Edition 

## Purpose of this fork - What it is
This repository is a fork of https://github.com/knah/VRCMods. It is created with the intention of separating the last version of FavCat that has functioning avatar favorites from the rest of the mods in the source repository, and, as of the first commit in this repository, was last updated to be compatible with build 1088 of VRChat. My hope is that, with the creation of this fork, that this mod can be maintained by open source means, rather than shady dll files flying around that, with modification, could compromise your account, your PC, and all the personal information you hold dear. In my opinion, if favcat continues to exist (it likely will in some form), the safest way is to make that existence open-source. I would encourage users to contribute to this project, I will accept contributions that are clearly not obfuscated or malicious. 

## What this is not
This fork isn't an attempt to make a jab at the choices of the VRChat Modding Group, EMMVRC, or the VRChat Team. I understand that VRChat Plus is required to ensure the sustainability of the platform - That's why I continue to subscribe to it. I also understand VRCMG's desire to not step on VRC's monetization toes – favorite mod obsolescence may be what's needed to help VRChat understand and work with modders. However, I firstly don't believe that favorite mods should be removed when alternatives are poorer - examples include the 4 rows of 25 limitation, the inability to create and name categories, and the ability to have fast, local search, just within your favorites. I would consider this mod obsolete when either EMMVRC with VRC+ has feature parity, or when the base game with VRC+ does. Second, I don't agree with letting ordinary - and often inexperienced users - be left to search for malicious mods in malicious communities. Many users will download favorite mods no matter what in whatever source is easiest - and it harms both the modding community's reputation and VRChat at large when users unknowingly use malicious or maliciously modified mods because VRCMG could or would not provide them with a safe and usable alternative. 

## IMPORTANT NOTICE!
I would like to clarify that I cannot, at the moment, maintain this mod by myself. I have no experience in C#, nor reverse engineering Unity. I need to rely on any willing contributors to maintain compatibility, fix bugs, and, if wanted, add new features. Otherwise, this mod will likely die after multiple VRChat updates. If it does, I'll keep it up as a separate repo for informational purposes, but once enough game updates roll out, I'll have to archive it. I would strongly encourage anyone experienced with VRChat modification to help me in this preservation effort. Please only submit code that's non-obfuscated - while I don't have the knowledge to do this myself, I've seen obfuscated code from decompiled malicious mods, and will not accept commits that contain it. I would recommend **against** forking this repository, and instead submitting pull requests. If you have another way you want to help, feel free to message me! (@camazing.me on Kik - no discord for privacy reasons)

# Documentation
*copied from the original readme*
*Please note that ILRepack was not removed, as it looked important to me. Feel free to create a github issue if it is not.*

## FavCat
An all-in-one local favorites mod. Unlimited favorite lists with unlimited favorites in them and a searchable local database of content and players.  
**Requires UI Expansion Kit 0.2.0 or newer**  
#### Features:
* Unlimited lists (categories) for favorites, each of unlimited size
* Lag-free even with large lists
* Freely changeable list height
* Avatar, world, and player favorites supported
* Modifiable list order and multiple list sorting options
* Fully searchable database of everything you have ever seen
* Changeable database location (**it's recommended to store the database in a directory backed up to cloud storage, such as Dropbox or OneDrive**, see below for setup)
* Local image cache for even better performance
* Categorize your own private avatars
* Import avatar favorites from other local favorite mods (read below)
* Exchange search database with friends (read below)
* Many more small things

#### Known limitations
* Player favorites don't show online status
* Lists with over a thousand elements can take a bit of time on game startup/list creation

#### Changing database location
Steps to change database location:
1. Run VRChat with the mod at least once
2. Make sure that VRChat is closed
3. Navigate to VRChat install directory (i.e. by clicking "Browse Local Files" in Steam)
4. Navigate to `UserData` folder and open `MelonPreferenes.cfg` with Notepad or other text editor
5. Find the line with `[FavCat]`
6. Find the line with `DatabasePath` under it
7. Change the value to absolute path to new storage folder. The new line should look like this: `DatabasePath = "C:/Users/username/OneDrive"` (with your own path, naturally; make sure to use forward clashes `/` instead of backslashes `\\`)
8. Save and close the text file
9. Copy the two (or four) database files (`favcat-favs.db` and `favacat-store.db`, and `favcat-favs-log.db` and `favcat-store-log.db` if they exist) from the old location (they are in `UserData` by default) to the new one.

If you want to move the image cache, use the same steps as above, but modify the line with `ImageCachePath` and copy `favcat-images.db` instead. It's not recommended to store the image cache in cloud storage due to its big size.

#### Importing avatar favorites from other local favorite mods
You can import favorites from other local favorite mods that use text files for storage.
1. Run VRChat with the mod at least once
2. Navigate to VRChat install directory (i.e. by clicking "Browse Local Files" in Steam)
3. Find the avatar list of the mod you want to import from. Places to look like are `UserData` folder, game folder, or a mod-specific folder, such as `404Mods`. The avatar list would usually be a plain text file or a JSON file - both are supported.
4. **Copy** the file to `UserData/FavCatImport` folder
5. In-game, click "More FavCat" on any big menu page, then click "Import databases and text files"
6. Import process can take some time. Once it is done, a new list will appear in the menu. It's safe to close the game and reopen it - import will continue from where it left off (you'll need to click the button again though). Once it is done, the corresponding list will be deleted from `UserData/FavCatImport` folder.

#### Sharing search database with friends
You can exchange the search database with friends to be able to find things they have seen. **Only accept databases from friends you trust - an intentionally malformed database can overwrite parts of yours with garbage**  
How to send database to a friend:
1. Run VRChat with the mod at least once (duh)
2. Make sure that VRChat is closed
3. Navigate to where your database is stored (see "Changing database location")
4. Make sure that there is no file named `favcat-store-log.db`. If there is one, it means that the game was not closed properly. In that case, run the game again, and use "Exit VRChat" button in settings menu to close it.
5. Send `favcat-store.db` to your friend.

How to receive database from a friend:
1. Run VRChat with the mod at least once
2. Navigate to VRChat install directory (i.e. by clicking "Browse Local Files" in Steam)
3. Put the database your friend sent you into `UserData/FavCatImport` folder. If you want to import multiple databases at once, you can rename them, as long as .db extension is kept.
4. In-game, click "More FavCat" on any big menu page, then click "Import databases and text files"
5. Import process can take some time. Once it is done, the corresponding database will be deleted from `UserData/FavCatImport` folder.

Note that your favorites are stored in `favcat-favs.db` - don't send it to your friends, favorite import is not supported. Most certainly don't send `favcat-images.db` to your friends - it's just a boring image cache.

#### Used libraries:
* [LiteDB](https://github.com/mbdavid/LiteDB) for all data storage
* [ImageSharp](https://github.com/SixLabors/ImageSharp), because unity is bad at loading images from streams on background thread

A long time ago this was based on Slaynash's [AvatarFav](https://github.com/Slaynash/AvatarFav) and [VRCTools](https://github.com/Slaynash/VRCTools), both licensed under the [MIT license](https://github.com/Slaynash/VRCTools/blob/master/LICENSE). Who knows how much of that still remains inside?

## ILRepack
There's a copy of [ILRepack.Lib.MSBuild.Task](https://github.com/ravibpatel/ILRepack.Lib.MSBuild.Task) and [ILRepack](https://github.com/gluck/il-repack) built for netcore/MSBuild 16 shipped with the repo.

## Installation
Before install:  
**Tupper (from VRChat Team) said that any modification of the game can lead to a ban, as with these mods**

To install these mods, you will need to install [MelonLoader](https://discord.gg/2Wn3N2P) (discord link, see \#how-to-install).  
Then, you will have to put mod .dll files in the `Mods` folder of your game directory

## Building
To build these, drop required libraries (found in `<vrchat instanll dir>/MelonLoader/Managed` after melonloader installation, list found in `Directory.Build.props`) into Libs folder, then use your IDE of choice to build.
 * Libs folder is intended for newest libraries (MelonLoader 0.2.2)

## License
With the following exceptions, all mods here are provided under the terms of [GNU GPLv3 license](LICENSE)
* ILRepack.Lib.MSBuild.Task is covered by [its own license](https://github.com/ravibpatel/ILRepack.Lib.MSBuild.Task/blob/master/LICENSE.md)
* ILRepack is covered by [Apache 2.0 license](https://github.com/gluck/il-repack/blob/master/LICENSE)
* UI Expansion Kit is additionally covered by [LGPLv3](UIExpansionKit/COPYING.LESSER) to allow other mods to link to it
* IKTweaks source code is not covered by a permissive license and provided for reference purposes only
