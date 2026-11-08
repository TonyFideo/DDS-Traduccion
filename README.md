# Digital Devil Saga: Spanish Translation (English ReadMe)
This temp repo contains stuff that people interested on modding/translating DDS or Atlus PS2 SMT alike (Nocturne and Raidou Duology).
Note: most if not all of these tools are highly WIP and contain most of the comments inside in Spanish but so far work and don't have issues unless specified.

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
-MSG13: Basic battle options.

# FLDALL.TBL (Binary)
Fld/f/bin/fldall.tbl\
-Location names.

# .ELF executable (WIP)
I'm not the best at reverse engineering and offsets stuff.\
It contains short and common strings used mostly for gameplay, includes:\
-Main Menu strings along with their x position of each sub category of strings (Main Menu/Items/Special Items).\
-Main Menu quotes when selecting an option.\
-PS2 Memory card related strings and startup main menu in-engine text (These are separated as a way to lower line, using the empty space doesn't cause any issue except the text getting out of the screen).\
-Common battle options (Attack, Shoot, Revert, Deploy, etc...).\
Note: These are stored in MIPS with a hardcoded 8 bytes limit, trying to move or increase it causes the entire text rendering of the game to break, it also needs a 1 empty byte (00) at the end to make space for the next.\
-Mantra descriptions (These are stored inside the .ELF as .PM1 files with their header and related stuff, needs more investigation).

#Fields names
F001 = N/A (contains common repeated strings).\
F002 = Outside Embryon base.\
F003 = Outside Vanguards base.\
F004 = Outside Maribel base.\
F005 = Outside Solids base\
F006 = \
F007 =\
F008 =\
F009 =\
F010 =\
F011 =\
F012 =\
F013 =\
F014 =\
F015 =\
F016 =\
F017 =\
F018 =\
F019 =\
F020 =\
F021 =\
F022 =\
F023 =\
F024 =\
F025 =\
F026 =\
F027 =\
F028 =\
F030 = Karma Temple\
F031 = Swimming section.\
F032 = Belzebuub encounter.

# Battle tutorials
-These are repeated as said in the Text editing section, they also are stored as .PM1 files).

# Credits
-It reads from bottom -> top, needs testing.
