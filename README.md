# Digital Devil Saga: Spanish Translation (English ReadMe)
This temp repo contains stuff that people interested on modding/translating DDS or Atlus PS2 SMT alike (Nocturne and Raidou Duology).
Note: most if not all of these tools are highly experimental WIP and contain most of the comments inside in Spanish but so far work and don't have issues unless specified.

# Exploring the files, directories and common formats.
-Just use TGE's PackTools, they can extract and build the .IMG container along with the .LB containers.\
-The textures are .TMX and/or inside .SPR files, use the latest Amiticia tool.\
-There's a fair pair of repeated files, specially in the NTSC release.\
-.PM1 and .BF text files can be extracted manually and repacked with TGE's Atlus Script Tools or with PersonaEditor.\
-.AT3 files are headerless and their HZ rates difer from most.\
-There's .TBL files that include binary strings inside, use PersonaEditor to explore with a UI and/or use a hex editor.\
-The Font file is stored inside the Font folder, specifically font0.FNT.\
-The FMV video files are stored inside the MOVIE/MOVIE2 folders.\

# Sound modding (.AT3/.ADB)
Tool and documentation in progress, mostly done. Includes converting to .WAV and creating them.

# FMV video files (.IPS)
So far I only managed to extract the video files with audio and without any luck converting a .mp4 h264/.avi/.pngs to .ips, I don't have any knowledge with video files or stuff like that, mostly Claude Opus 4.6 and Gemini 3.1 Pro Extended work.\
There's some .IPU files that contain misc background cutscenes used in the credits.\

# Font editing (.FNT)
The compression rework tool it's mostly done, didn't tested adding more glyphs as there isn't a need even with the tightly packed font.\
It's a standard Atlus ps2 era file, it has the same inner workings as P3/P4 ones except for a different compression work that PersonaEditor doesn't handle correctly. Refer to the Persona Modding Amiticia page or community for better documentation.\

# Cutscene editing and subtitle work (.PM1/.PM2)
Subtitle editor cli tool done and working whitout issues so far. I'll be releasing it along with a UI.\
Cutscenes files (fmv/in-engine) are stored inside Events, starting from e601 to e670. The subtitles are stored inside the .PM1 while their timing data are stored inside the .PM2.\
You can basically use PersonaEditor with a DDS font, your modified font or even the basic P3/P4 font selected as they share the common english letters and symbols.\
Using any of the Korean particles causes the entire subtitle of the cutscene to break (missing letters all over it and slow fade in effect randomly played).\

# General text editing (.BF/.BMD/raw .MSG)
-General text boxes strings from talking to a npc, interacting with doors, chests, notifications, etc (Basically almost everything that uses the text boxes) are referred as "FIELDS", stored inside .LB files in "fld/f".\
PersonaEditor works without issues but there's a lot of repeated text along every single field, I recommend working with any .PO (poedit as an example) editing program.\
-Battle lines are inside "battle/aicalc.tbl", they are stored as .MSG and also containts battle tutorials (Read the comment about these too at .ELF executable).\
-Facilities (Karma Terminals, Vendors, Healing Stations) text lines are inside "facility/msg/<choose-the-facility>". These are standard .BMD files.\


# MSG.TBL (Binary and text files)
Battle/MSG.TBL\
-MSG00: Description of demon affinities (When inspecting enemies in battle).\
-MSG01: Mantra names.\
-MGS02: Description of demon affinities (again but with less content, maybe bosses?)\
-MSG03: Demon names.\
-MSG04: Item names\
-MSG05: Protagonist and team names (untested).\
-MSG06: Race names.\
-MSG07: Skill names\
-MSG08/MSG09: ???\
-MSG10: Item descriptions.\
-MSG11: Skill descriptions.\
-MSG12: Battle status text.\
-MSG13: Basic battle options.\

# FLDALL.TBL (Binary)
Fld/f/bin/fldall.tbl\
-Location names.\

# .ELF executable (WIP)
I'm not the best at reverse engineering and offsets stuff.\
It contains short and common strings used mostly for gameplay, includes:\
-Main Menu strings along with their x position of each sub category of strings (Main Menu/Items/Special Items).\
-Main Menu quotes when selecting an option.\
-PS2 Memory card related strings and startup main menu in-engine text (These are separated as a way to lower line, using the empty space doesn't cause any issue except the text getting out of the screen).\
-Common battle options (Attack, Shoot, Revert, Deploy, etc...).\
Note: These are stored in MIPS with a hardcoded 8 bytes limit, trying to move or increase it causes the entire text rendering of the game to break, it also needs a 1 empty byte (00) at the end to make space for the next.
-Mantra descriptions (These are stored inside the .ELF as .PM1 files with their header and related stuff, needs more investigation).
-Battle tutorials (These are repeated as said in the Text editing section, they also are stored as .PM1 files).
-Credits (It reads from bottom -> top, needs testing).
