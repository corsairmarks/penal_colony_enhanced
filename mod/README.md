# Overview

Have you ever wondered why Resort Colonies are perfectly useful on Tomb Worlds but not Penal Colonies?  Or been frustrated at needing to use a high-habitability planet as your Penal Colony?  Then this mod is for you!  I have altered the modifier for Penal Colonies to grant 100% habitability, but impose a flat -50% to Pop growth speed (the same as 0% habitability).  In exchange for the overall growth penalty, you gain a new bonus to immigration-based Pop growth, a bonus to inmate job output, and (implicitly) reduced upkeep due to high habitability.  Finally - your prison-planet has a large penalty to research - the criminals cannot be trusted with state research secrets and have limited ability to communicate off-planet.

# Changes

Adds a new pop stratum "Inmate" that is automatically assigned to most Pops on a Penal Colony.  This new stratum acts similarly to slave - Pops demote instantly, they have +10% productive job output, and they have a significant happiness penalty (-25%).  In addition they have a 90% penalty to research point output to represent the lack of off-world communication as well as tight control of any information they do receive.  Inmates have very little political power and their unhappiness won't significantly impact the happiness of non-Inmate Pops on the planet (ruler-strata Pops, enforcers, telepaths, and soldiers - the Inmates can't be trusted to supervise _themselves_).  Should you also have the Police State civic, each Inmate produces bonus Unity.  Regardless, Inmates generate crime - which is doubled when unemployed.

The Penal Colony planet designation has been altered to +1 Criminal job per 10 Pops - some of the convicts in the planet-wide prison system manage to escape supervision.  To compensate, Penal Colonies gain bonus stability that scales compared to how _unhappy_ Inmate Pops are.

The Penal Colony planet modifier (added when you enact the Declare Penal Colony decision) has been slightly altered as well - it grants +100% habitability (just like Resort Worlds) and +33% Pop Growth from immigration, but now also imposes a flat -50% to overall Pop Growth.

To keep your Penal Colony running smoothly, this mod also creates a new capitol building complete with recolored icons.  Some Administrator jobs are replaced with the new Warden job that produces unity and stability, but also decreases the happiness of Inmate-stratum Pops.  Countries with other Administrator-substitution civics end up replacing all of the Administrator jobs with a split of Wardens and their special ruler jobs.  If your empire uses Battle Thralls, they can also serve as Wardens.

## Compatibility

This mod replaces three game objects related to Penal Colonies:

* `decision_penal_colony` decision to enact a Penal Colony
* `col_penal` Penal Colony designation
* `penal_colony` static modifier for Penal Colonies

And it overrides three scripted triggers related to capitol buildings:

* `has_upgraded_capital`
* `has_major_upgraded_capital`
* `has_fully_upgraded_capital`

This mod is incompatible with other mods that want to also overwrite these same game objects.  It works with other mods that alter built-in buildings or jobs - the new capitol building is implemented without any building file overwrites.  If other mods also attempt to change the script for checking whether advanced buildings are allowed to be constructed, a compatibility patch should be straightforward.

Built for Stellaris version 3.2.\* "Herbert."  Not compatible with achievements.

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