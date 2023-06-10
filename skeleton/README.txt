DotUI is a minimal launcher for the Miyoo Mini Plus, adapted from Shaun Inman's MiniUI

DotUI Source: https://github.com/Xpndable/DotUI

MiniUI Source: https://github.com/shauninman/MiniUI

----------------------------------------
Features

- No settings or configuration
- Simple launcher, simple SD card
- Automatically hides extension 
  and region/version cruft in 
  display names
- Consistent in-emulator menu with
  quick access to save states, disc
  changing, and emulator options
- Automatically sleeps after 30 seconds 
  or press POWER to sleep (and wake)
- Automatically powers off while asleep
  after two minutes or hold POWER for
  one second
- Automatically resumes right where
  you left off if powered off while
  in-game, manually or while asleep
- Resume from manually created, last 
  used save state by pressing X in 
  the launcher instead of A
- Streamlined emulator frontend 
  (picoarch + libretro cores)

----------------------------------------
Install

DotUI works on all known versions of the official firmware, no need to upgrade. Save yourself a headache.

Copy the contents of this archive to the root of a fresh FAT32 formatted SD card. Don't forget the "miyoo354" folder. Insert your SD card into the device and power it on. DotUI will install automatically and be ready to go in about 10 seconds.

----------------------------------------
Update

To install an update copy just the "miyoo354" folder to the root of your SD card. Insert your SD card into the device and power it on. DotUI will update automatically and be ready to go in about 10 seconds.

----------------------------------------
Shortcuts

Reduce/increase brightness:
MENU + Volume UP or DOWN

Reduce/increase volume:
Volume Buttons
(To show volume level, hold SELECT in menus)

Force power off (in case of hangs):
MENU + POWER

----------------------------------------
Roms

Included in this zip is a Roms folder containing folders for each console DotUI currently supports. You can rename these folders but you must keep the uppercase tag name in parentheses in order to retain the mapping to the correct emulator (eg. "Nintendo Entertainment System (FC)" could be renamed to "Nintendo (FC)", "NES (FC)", or "Famicom (FC)"). 

You should probably preload these folders with roms and copy each one to the Roms folder on your SD card before installing. Or not, I'm not the boss of you.

When one or more folder share the same display name (eg. "Game Boy Advance (GBA)" and "Game Boy Advance (MGBA)") they will be combined into a single menu item containing the roms from both folders (continuing the previous example, "Game Boy Advance"). This allows opening specific roms with an alternate pak.

----------------------------------------
Bios

Some emulators require or perform much better with official bios. DotUI is strictly BYOB. Place the bios for each system in a folder that matches the tag in the corresponding Roms folder name (eg. bios for "Sony PlayStation (PS)" roms goes in "/Bios/PS/"),

Bios file names are case-sensitive:

   FC: disksys.rom
   GB: gb_bios.bin
  GBA: gba_bios.bin
  GBC: gbc_bios.bin
   PS: psxonpsp660.bin
	
----------------------------------------
Disc-based games

To streamline launching multi-file disc-based games with DotUI place your bin/cue (and/or iso/wav files) in a folder with the same name as the cue file. DotUI will automatically launch the cue file instead of navigating into the folder when selected, eg. 

  Harmful Park (English v1.0)/
    Harmful Park (English v1.0).bin
    Harmful Park (English v1.0).cue

For multi-disc games, put all the files for all the discs in a single folder and create an m3u file (just a text file containing the relative path to each disc's cue file on a separate line) with the same name as the folder. Instead of showing the entire messy contents of the folder, DotUI will launch the appropriate cue file, eg. For a Policenauts folder structured like this:

  Policenauts (English v1.0)/
    Policenauts (English v1.0).m3u
    Policenauts (Japan) (Disc 1).bin
    Policenauts (Japan) (Disc 1).cue
    Policenauts (Japan) (Disc 2).bin
    Policenauts (Japan) (Disc 2).cue

the m3u file would contain just:

  Policenauts (Japan) (Disc 1).cue
  Policenauts (Japan) (Disc 2).cue

DotUI also reportedly supports chd files and official pbp files (multi-disc pbp files larger than 2GB are not supported).

----------------------------------------
Collections

A collection is just a text file containing an ordered list of full paths to rom, cue, or m3u files. These text files live in the Collections folder at the root of your SD card, eg. "/Collections/Metroid series.txt" might look like this:

  /Roms/GBA/Metroid Zero Mission.gba
  /Roms/GB/Metroid II.gb
  /Roms/SNES (SFC)/Super Metroid.sfc
  /Roms/GBA/Metroid Fusion.gba

----------------------------------------
Advanced

DotUI can automatically run a user-authored shell script on boot (eg. for starting daemons like screenshots). Just place a file named "auto.sh" to "/.userdata/".

Just keep in mind, syntax errors in auto.sh may prevent DotUI from launching which will allow the stock system to modify your SD card, polluting the root of the card and your Roms folder with unnecessary subfolders, and removing the hook that allows DotUI to boot. If this happens you will need to reinstall DotUI (well, really just its "./tmp_update/" folder). No userdata is lost when this happens, it's just kinda annoying.

----------------------------------------
DotUI Thanks

Huge thanks to Shaun Inman from whom this code base is ported for the Miyoo Mini Plus and will be adapted to suit over time. His efforts on MinUI and MiniUI are monumental for the entire community, and we would be poorer without his efforts.

Check out Shaun's repos: https://github.com/shauninman

----------------------------------------
MiniUI Thanks (from Shaun)

To eggs for his example middleware code, countless bug fixes, neon scalers, and patience in the face of my endless questions.

Check out eggs' releases: https://www.dropbox.com/sh/hqcsr1h1d7f8nr3/AABtSOygIX_e4mio3rkLetWTa

To neonloop for putting together the Trimui toolchain from which I learned everything I know about docker and buildroot and is the basis for the Miyoo Mini toolchain I put together, and for picoarch, without which I might have given up entirely.

Check out neonloop's repos: https://git.crowdedwood.com

To Jim Gray, Totofaki, and the entire Onion crew for taking a joke, running with it, and turning a stop-gap into a beloved launcher and community, it's been amazing to watch.

Check out Onion for a more full-bodied Miyoo Mini experience: https://github.com/OnionUI/Onion/

To Evil_Rob for gently and regularly nudging me towards a better understanding of how all the Linux-y bits (are supposed to) work under the hood.

To the creators of the Trimui Model S and Miyoo Mini for making some nice (now hard to find) hardware and simple interfaces in a market crowded with bloated, ugly front ends that require entirely too much work to setup as intended.

And to the entire Retro Game Handhelds Miyoo Mini and dev Discord community for their enthusiasm and encouragement. 

Checkout the channel on the Retro Game Handhelds Discord: https://discord.com/channels/529983248114122762/891336865540620338
