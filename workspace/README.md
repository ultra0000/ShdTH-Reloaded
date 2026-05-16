## How to Build Reloaded Yourself

IF YOU ARE NOT ACTIVELY DEVELOPING A MOD OFF RELOADED, IT IS RECOMMENDED TO USE THE "RELEASES" TAB RATHER THAN DOING THE BELOW.
THIS IS PURELY FOR THOSE LOOKING TO REPRODUCE THE ROM FROM SCRATCH.

### Building from a clean slate

You must use the NTSC-U ROM as a base.

1. Extract the original game following "Extraction of Original Game / FST Format" below.
2. Merge the `\ISO EDITS` content ('files' and 'sys') with the extracted game.
3. Open the `\AFS` content from the repo. Follow the README and grab `PAFS` utility. Move the extracted game's `PRS_VOICE_E.afs` into this folder. Then drag it onto `PAFS.exe`. The patched AFS will be created. Rename the patched AFS to the original game name, and move it to the extracted game folder.
4. Extract the `Op.sfd.7z.00X` archive. It's compressed like that to avoid issues running into GitHub's non-LFS file size limit. Don't ask why we can't enable Git LFS right now.
5. Open the `\workspace\fileToDelete-every-release.txt` and delete these directories and files from your extracted game, as specified.
6. Download MCM (Melee Code Manager) if you haven't: https://github.com/DRGN-DRC/Melee-Code-Manager/releases
7. You will need to overwrite configurations to make it work with Shadow. After extracting v4.4.1 or newer:
In `\Original DOLs` place your ORIGINAL game's `main.dol` from `YourExtractedGame\sys` (not the overwritten one, re-extract it if needed) in this folder, renaming as `NTSC 1.06.dol`.
In `\lib` place/overwrite the `settings.py` from the repo's `\code\MCM`
In `\Mods Library` place the .txt files from the repo's `\code\MCM`
8. Launch MCM. Select your extracted DOL. It should show all of the codes across the four files. Enable all of them unless you're making a non-widescreen build, in which case you should keep the 'Advanced Full Widescreen' patch disabled.
Note: After opening the DOL, specify version 1.06 if asked.
9. If making a non-widescreen build, copy the overrides from `\workspace\Widescreen-ShadowTH-overrides\4x3\`. Overwrite when asked.
10. Build the ISO with Dolphin's -> Right Click Game -> 'Convert'. 

## Other information

* Place the `\code\GUPR8P.ini` file in `\GameSettings` of your `Dolphin User Folder`. You can find your `Dolphin User Folder` by launching Dolphin and clicking `File` on the menu bar, then `Open User Folder`.
* Use HeroesPowerPlant / HeroesOne-Reloaded, and other tools at github.com/ShadowTheHedgehogHacking to develop / make adjustments.

### Extraction of Original Game / FST Format
1. Get the latest release or dev Dolphin - [dolphin-5.0-21460 or newer recommended](https://dolphin-emu.org/download/)
2. (Optional: only do this step if you want to keep config separate) Before launching dolphin, create an empty file
   `portable.txt` in the same folder as Dolphin.exe
3. Open Dolphin
4. Right-click Shadow The Hedgehog in the game list
5. Select Properties
6. Select FileSystem Tab
7. Right-click "Disc"
8. Select Extract Entire Disc...
9. Select a new folder where you will store the game content and modify its files

### Replacement of Files & Converting FST to ISO
1. Open the newly extracted folder and merge/overwrite the 'ISO EDITS' content ('files' and 'sys').
2. Open Dolphin
3. Open Config (next to Graphics and Controllers)
4. Select Paths Tab
5. Select "Add" for Game Folders
6. Navigate to the folder where you extracted the game
7. Open the `sys` folder, and select "Select Folder"
8. Close the confirmation pane, your games list should populate a new 0 filesize game of Shadow The Hedgehog. The 0 filesize entry is the FST format game
9. Right click the FST format game and pick `Convert File...`
10. The Convert window will appear, click "Convert..." and name it `game.iso` for Nintendont, or `ShdTH-Reloaded.iso` for Dolphin
11. Move/Save the ISO to the Path Dolphin detects your games. A new ShadowTH-Reloaded entry should appear in your Dolphins game list with greater than 0 filesize, this is the ISO rather than extracted format.
12. Click View -> Purge Game List Cache if the Reloaded Icon is not appearing on the new entry. If it still does not appear, the files were not properly replaced
