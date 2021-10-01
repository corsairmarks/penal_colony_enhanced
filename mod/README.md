# Overview

Have you ever wondered why Resort Colonies are perfectly useful on Tomb Worlds but not Penal Colonies?  Or been frustrated at needing to use a high-habitability planet as your Penal Colony?  Then this mod is for you!  I have altered the modifier for Penal Colonies to grant 100% habitability, but impose a flat -50% to Pop growth speed (the same as 0% habitability).  In exchange for the overall growth penalty, you gain a new bonus to immigration-based Pop growth, specialist and worker job output, and reduced consumer goods upkeep.  Finally - your prison-planet has a large penalty to researcher and culture-worker output - the criminals cannot be trusted with state research secrets and have limited ability to communicate off-planet.

# Changes

Alters Penal Colonies to have a focus on non-research jobs as well as bonuses to stability for _lower_ happiness.  Additionally, there is a new capital building for Penal Colonies and a special job provided only by this building - the Warden.  Wardens increase stability at the expense of non-ruler happiness.

## Compatibility

Built for Stellaris version 3.0.\* "Dick."

This mod replaces three game objects related to Penal Solonies:

* `decision_penal_colony` descision to enact a Penal Colony
* `col_penal` Penal Colony designation
* `penal_colony` static modifier

This mod is incompatible with other mods that want to also overwrite these same game objects.

Not compatible with achievements.

### When to Install

This mod can be safely added to your savegame after the game has started, but not removed.  Because this mod adds buildings and a job, removing it could result in problems when the game cannot find an expected building definition or finds Pops assigned to a job that no longer exists.  Back up your savegame before trying to remove a mod.

## Known Issues

Overriding a colony designation or a decision causes the game to log an error, so expect to see two lines in the error.log file similar to:

```
[00:14:44][game_singleobjectdatabase.h:147]: Object with key: col_penal already exists
[00:14:45][game_singleobjectdatabase.h:147]: Object with key: decision_penal_colony already exists
```

## Changelog

* 1.0.0 Initial version

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/penal_colony_enhanced)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.