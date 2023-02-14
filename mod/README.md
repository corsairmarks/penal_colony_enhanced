# Overview

Have you ever wondered why Resort Colonies are perfectly useful on Tomb Worlds but not Penal Colonies?  Or been frustrated at needing to use a high-habitability planet as your Penal Colony?  Then this mod is for you!  The modifier for Penal Colonies is altered to grant 100% habitability, but imposes a flat -50% to Pop growth speed (the same as 0% habitability).  In exchange for the overall growth penalty, you gain a new bonus to immigration-based Pop growth, a bonus to inmate job output, and (implicitly) reduced upkeep due to high habitability.  Finally - your prison-planet has a large penalty to research - the criminals cannot be trusted with state research secrets and have limited ability to communicate off-planet.

# Changes

Adds a new pop stratum "Inmate" that is automatically assigned to most Pops on a Penal Colony.  This new stratum acts similarly to slave - Pops demote instantly, they have +10% productive job output, and they have a significant happiness penalty (-25%).  In addition they have a -90% penalty to research point output to represent the lack of off-world communication as well as tight control of any information they do receive.  Inmates have very little political power and their unhappiness won't significantly impact the happiness of non-Inmate Pops on the planet (ruler-strata Pops, enforcers, telepaths, and soldiers - the Inmates can't be trusted to supervise _themselves_).  Should you also have the Police State civic, each Inmate produces bonus Unity.  Regardless, Inmates generate crime - which is doubled when unemployed.

The Penal Colony planet designation has been altered to +1 Criminal job per 10 Pops - some of the convicts in the planet-wide prison system manage to escape supervision.  To compensate, Penal Colonies gain bonus stability that scales compared to how _unhappy_ Inmate Pops are.

The Penal Colony planet modifier (added when you enact the Create Penal Colony decision) has been slightly altered as well - it grants +100% habitability (just like Resort Worlds) and +33% Pop Growth from immigration, but now also imposes a flat -50% to overall Pop Growth.  Your other planets also receive a small amount of flat crime reduction (-5) in addition to the existing -25% crime bonus.

To keep your Penal Colony running smoothly, this mod also creates a new capitol building complete with recolored icons.  Some Politician jobs are replaced with the new Warden job that produces unity and stability, but also decreases the happiness of Inmate-stratum Pops.  Countries with other Politician-substitution civics end up replacing all of the Politician jobs with a split of Wardens and their special ruler jobs.  If your empire uses Battle Thralls, they can also serve as Wardens.

Finally, you can use your inmates to your military advantage.  Penal colonies are automatically defended by Penal Conscript Garrisons instead of standard Defense Armies, and you can conscript (train) more to serve in assault Penal Conscript Legions.  Penal Conscripts (both types) have double the health of their corresponding standard army types, but deal increased collateral damage and have lower moral.  Penal Conscript Legions are limited to one per Pop with the Inmate stratum (the maximum count updates monthly).

## Localisation

* English by corsairmarks (author)
* German (Deutsch) by [Lucanoria](https://steamcommunity.com/id/Lucanoria)

## Compatibility

This mod replaces four game objects related to Penal Colonies:

* `decision_penal_colony` decision to enact a Penal Colony
* `col_penal` Penal Colony designation
* `penal_colony` static modifier for Penal Colonies
* `penal_colony_other_planets` static modifier that decreases crime on other planets

And it overrides three scripted triggers related to capitol buildings:

* `has_upgraded_capital`
* `has_major_upgraded_capital`
* `has_fully_upgraded_capital`

And finally it overrides the `planet_jobs` (Jobs) economic category in order to create multipliers for inmate production.

This mod is incompatible with other mods that want to also overwrite these same game objects.  It works with other mods that alter built-in buildings or jobs - the new capitol building is implemented without any building file overwrites.  If other mods also attempt to change the script for checking whether advanced buildings are allowed to be constructed, a compatibility patch should be straightforward.  This mod has built-in compatibility with [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835).

Built for Stellaris version 3.6 "Orion."  Not compatible with achievements.

### When to Install

This mod can be safely added to your savegame after the game has started, but not removed.  Because this mod adds buildings and a job, removing it could result in problems when the game cannot find an expected building definition or finds Pops assigned to a job that no longer exists.  Back up your savegame before trying to remove a mod.

### Known Compatible Mods

[Prison, Resort and Thrall Habitats](https://steamcommunity.com/sharedfiles/filedetails/?id=2905474716) allows establishing Prison, Resort, and Thrall habitats.

## Known Issues

Overriding game elements causes the game to log errors, so expect to see six lines in the error.log file similar to:

```
[18:22:55][game_singleobjectdatabase.h:165]: Object with key: planet_jobs already exists, using the one at  file: common/economic_categories/10_penal_colony_enhanced_category_overrides.txt line: 1
[18:22:57][game_singleobjectdatabase.h:165]: Object with key: col_penal already exists, using the one at  file: common/colony_types/01_penal_colony_enhanced_colony_types_overrides.txt line: 1
[18:22:58][game_singleobjectdatabase.h:165]: Object with key: has_upgraded_capital already exists, using the one at  file: common/scripted_triggers/02_penal_colony_enhanced_scripted_trigger_buildings_overrides.txt line: 2
[18:22:58][game_singleobjectdatabase.h:165]: Object with key: has_major_upgraded_capital already exists, using the one at  file: common/scripted_triggers/02_penal_colony_enhanced_scripted_trigger_buildings_overrides.txt line: 77
[18:22:58][game_singleobjectdatabase.h:165]: Object with key: has_fully_upgraded_capital already exists, using the one at  file: common/scripted_triggers/02_penal_colony_enhanced_scripted_trigger_buildings_overrides.txt line: 142
[18:23:00][game_singleobjectdatabase.h:165]: Object with key: decision_penal_colony already exists, using the one at  file: common/decisions/03_penal_colony_enhanced_special_decisions_overrides.txt line: 1
```

## Changelog

* 1.0.0 Initial version
* 1.1.0 Add German localisation by Lucanoria
* 1.2.0 More enhancements
    * Add Penal Conscript Legions - similar to normal assault armies but have twice mas much health; they are limited by how many Pops are on your Penal Colony
    * Add Penal Conscript Garrisons - similar to normal defensive armies but have twice mas much health; they **not** limited but are only available to spawn on Penal Colonies
    * Increased happiness reduction by Wardens (5% => 10%)
    * Buffed the "Penal Colony Other Worlds" modifier to reduce crime by a small amount (-5) in addition to the existing -25%
* 2.0.0 Update for Stellaris version 3.3 "Libra"
    * Convert references to Administrators to Politicians
    * Influence costs converted to unity, to match the changes from 3.3
    * Update the Penal Colony designation so its bonus scales with new Planetary Ascension Tiers, but its penalties do not
* 3.0.0 Update for Stellaris version 3.4 "Cepheus"
    * Update penal armies with new army properties
    * Authoritarians and Police States have an increased chance for Pops to resettle to a Penal Colony
    * Allow the AI to designate Penal Colonies
    * Update the overridden economic category `planet_jobs` with underlying changes from 3.4
    * Update Warden job weights to use the new weighting system and amenity production system
    * Apply memory optimizations to effects and triggers
* 4.0.0 Update for Stellaris version 3.6 "Orion" (and changes from version 3.5 "Fornax")
    * Update the pop category `inmate` to use the the new inline scripts and account for new sources of growth/upkeep/production
    * Update penal capitol buildings with new cybernetic tradition and federation effects (added in 3.6 to other capitols)
    * Update the overridden economic category `planet_jobs` with underlying changes from 3.5/3.6
    * Update Warden job to attract species with the new army-boosting traits
    * Restrict the AI from creating a Penal Colony until it has more than 5 worlds
    * AI is more inclined to choose lower-habitability worlds as Penal Colonies
* 4.1.0 Add compatibility with [Prison, Resort and Thrall Habitats](https://steamcommunity.com/sharedfiles/filedetails/?id=2905474716)
    * Add new penal habitat capital buildings
* 5.0.0 Add a compatibility trigger for other mods to check whether this one is active, remove old compatibility global flag
* 5.1.0 Add built-in support for [Planetary Diversity](https://steamcommunity.com/sharedfiles/filedetails/?id=819148835)

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/penal_colony_enhanced)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.