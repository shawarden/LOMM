#Linux Overlay Mod Mapper

LOMM uses the fuse version of overlayfs to install mods onto any given game.
Using Linux's OverlayFS system the core game remain untouched by the mods.

Usage:

  Required:

    -g/--game [dir] The game directory that will be overlayed.
                    This directory becomes functionally write-protected.
    -m/--mod  [dir] Mod directory to be overlayed over the --game directory
                    Can be specified multiples times.
                    Mods load in order given.
                    Mods loaded here will be layered before any --base mods
                    If --top and --base directories are not set then the last
                     mod layer set here will be used to capture changes.
    -b/--base [dir] Directory that contains a collection of mods to overlay
                     over the --game directory.
                    Must contain a \"mods\" directory that contains the mods
                    Mods are loaded alphabetically.
                    If no --top specified then overlay_store directory will be
                     created here.

  Optional:
  
    -t/--top [dir]  Allows you to specify the writable, top level directory that
                     captures all changes made to the current stack.
                    If not specified it will default to the last --mod specified
                     directory or a dedicated overlay_store folder in --base.
    -n/--nope       Prints what would happen without actually doing it.
                     Implies --debug because of the implication.
    -d/--debug      Debug process
    -w/--wait       Wait in terminal to allow automatic unmounting.


 Copyright: Why? Anyone with the internet can write this. GPL2 it is then!
