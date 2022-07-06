# King's Bounty Dark Side - Variation Mod
 Mod by Dmitry "AmDDRed" Prigodich to tryout King's Bounty modding and modify few positions in the game's balance.

## Initial Goals
0. [ ] Create some basic documentation
1. [ ] Make undead poison immune;
2. [ ] Make undead bleed immune;
3. [ ] Make undead morale neutral;
4. [ ] Make demons hot-resistant; (if not already)
5. [ ] Add all 1-2 level units for orcs, demons, undead to the base
6. [ ] Update skeleton.atom with receiver=bones function
7. [ ] Update ghosts with blend=0.85 function
8. [ ] Update fire_elementals from undead roots
9. [ ] Update inferno_dragon with model{1=phoenixash.bma}?

## Knowledge Base
- `*.kfs` is a simple .zip archive, opened by any archive manager, like 7Zip or WinRar;
- `/data/data.kfs` - contains unit data and a lot of other stuff, some new additional units may be found in ses.kfs archive;
- `/sessions/darkside/loc_ses.kfs/<lng>_units.lng` - contains unit names, single (`cpn_*`) or plural (`cpsn_*`); these names could be used to find unit config (`*.atom`);
- `/sessions/darkside/loc_ses*.kfs/<lng>_units_features.lng` - contains strings for features_label, features_hints for unit's .atom's;
- `/sessions/darkside/loc_ses*.kfs/<lng>_windows.lng` - UI localization, possible to add mod naming, for example, in `start_version=`;
- `/sessions/darkside/ses.kfs/logic.txt` - contains all feature list, not added automatically to the unit description;
- `/sessions/darkside/ses.kfs/hero.txt` - starting settings for heroes;
- `/sessions/darkside/ses.kfs/logic_hero.lua` - update settings for heroes;

## Features
- resistances=
> physical,poison,magic,fire,glacial,astral

- features=
> armor,shot,mage,undead,eyeless,demon,dragon,plant,mind_immunitet,fire_immunitet,magic_immunitet,poison_immunitet,freeze_immunitet,holy,bone,golem,humanoid,beast,nonecro,barrier,archer,boss,pawn,orb,mech,summoned_creature,rune_knowledge,ice_creature,light_step,ghost,light,dark

## Units
Information for fast access.

### Undeads
| lvl   | orig_name         | good_to_be_name         | имя                     | path |
| - | - | - | - | - |
| 1     | spider_undead     | undead_spider           | Мёртвый паук            | ./data/data.kfs   |
| 1     | skeleton          | undead_skeleton         | Скелет                  | ./data/data.kfs   |
| 1     | archer            | undead_skeleton_archer  | Скелет-лучник           | ./data/data.kfs   |
| 2     | zombie            | undead_zombie           | Зомби                   | ./data/data.kfs   |
| 2     | zombie2           | undead_zombie2          | Гниющий зомби           | ./data/data.kfs   |
| 3     | pirat_ghost       | undead_ghost_pirate     | Пират-призрак           | ./data/data.kfs   |
| 3     | ghost             | undead_ghost            | Привидение              | ./data/data.kfs   |
| 3     | ghost2            | undead_ghost2           | Проклятое привидение    | ./data/data.kfs   |
| 3     | vampire_woman     | undead_vampiress        | Вампиресса              | ./session/darkside/ses.kfs |
| 3     | vampires_cloud    | undead_vampiress_cloud  | Вампиресса (Облако)     | ./session/darkside/ses.kfs |
| 3     | vampire           | undead_vampire          | Вампир                  | ./data/data.kfs   |
| 3     | bat               | undead_vampire_bat      | Вампир (Мышь)           | ./data/data.kfs   |
| 4     | vampire2          | undead_vampire2         | Древний вампир          | ./data/data.kfs   |
| 4     | bat2              | undead_vampire2_bat     | Древний вампир (Мышь)   | ./data/data.kfs   |
| 4     | blackknight       | undead_black_knight     | Чёрный рыцарь           | ./session/darkside/ses.kfs |
| 4     | necromant         | undead_necromancer      | Некромант               | ./data/data.kfs   |
| 5     | bonedragon        | undead_bone_dragon      | Костяной дракон         | ./data/data.kfs   |

### Demons
| lvl   | orig_name         | good_to_be_name         | имя                     | path              |
| ----- | ----------------- | ----------------------- | ----------------------- | ----------------- |
| 2     | imp               | demons_imp             | Имп                   | ./data/data.kfs   |
| 2     | imp2              | demons_imp2            | Имп-насмешник         | ./data/data.kfs   |
| 3     | cerberus          | demons_cerberus        | Цербер                | ./data/data.kfs   |
| 3     | firemental        | demons_fire_elemental  | Огненный элементаль   | ./data/data.kfs   |
| 3     | priestess_blood   | demons_blood_priestess | Жрица Крови           | ./session/darkside/ses.kfs |
| 4     | demoness          | demons_demoness        | Демонесса             | ./data/data.kfs   |
| 4     | demon             | demons_demon           | Демон                 | ./data/data.kfs   |
| 4     | demon2            | demons_demon2          | Палач                 | ./data/data.kfs   |
| 5     | archdemon         | demons_archdemon       | Архидемон             | ./data/data.kfs   |

### Orcs
| lvl   | orig_name         | good_to_be_name         | имя                     | path              |
| ----- | ----------------- | ----------------------- | ----------------------- | ----------------- |
| 1     | goblin            | orcs_goblin           | Гоблин                | ./data/data.kfs   |
| 1     | goblin2           | orcs_goblin2          | Неистовый гоблин      | ./data/data.kfs   |
| 1     | goblin_rider      | orcs_goblin_rider     | Говорящий с духами    | ./session/darkside/ses.kfs |
| 1     | catapult          | orcs_goblin_catapult  | Гоблин с катапультой  | ./session/darkside/ses.kfs |
| 1     | orc               | orcs_orc              | Орк                   | ./data/data.kfs   |
| 1     | orc2              | orcs_orc2             | Орк-ветеран           | ./data/data.kfs   |
| 1     | ork_scout         | orcs_orc_scout        | Орк-разведчик         | ./session/darkside/ses.kfs |
| 1     | shaman            | orcs_orc_shaman       | Шаман                 | ./data/data.kfs   |
| 1     | ogre              | orcs_ogre             | Огр                   | ./data/data.kfs   |
| 1     | ogre_chieftain    | orcs_orc_chieftain    | Орк-вождь             | ./data/data.kfs   |
