# Combat Unit File Desciphration

## General Info
- Unit info file are located in `%_base_folder_%/data/data.kfs/%unit_name%.atom` or `%_base_folder_%/sessions/darkside/ses.kfs/%unit_name%.atom`;
- Unit filename could be found in `/sessions/darkside/loc_ses.kfs/<lng>_units.lng`: it contains unit names, single (`cpn_*`) or plural (`cpsn_*`);

Regexp pattern:
- `(?<=^main \{[\s]+class=army[\s\w=.{}]+)cullcat=` - positive lookback, might not be supported
- `^main \{[\s]+class=army[\s\w=.{}]+cullcat=`
- `^main \{[\s]+class=[\s\w=.{}]+cullcat=1[\s]`
- `^main \{[\s]+class=platform`


## File Content
```
main{}
    class
    ...
    model{...}
    infobox{...}
arena_params{}
    ...
    resistances{}
    %action_script%{}
        damage{}
        custom_params{}
    script_data{}
    arena_bonuses{}
scripts{}
animations{}
editor{}
attachments{}
prefetch{}
```

### Main{}
| name             | type      | values            | example                   | location              | description  |
| ---------------- | --------- | ----------------- | ------------------------- | --------------------- | ------------ |
| class            | string    | see below         | chesspiece                | common                | game object type |
| model            | string    | *.bma             | chosha.bma                | common                | model to use |
| spawnscale       | double    | 0-x?              | 1.01                      | common                | model scale to use |
| colmesh          | string    | collision_*.cms   | collision_alchemist.cms   | common                | collision mesh to use |
| cullcat          | int       | 0-10              | 0                         | common                | usage not clear; for chesspiece is 0 |
| blend            | double    | 0-1 (?)           | 0.85                      | common                | allows model to be transparent |
| bboxanim         | boolean   | true/false or 0/1 | 1                         | common                | usage not clear; big_box_animation? |
| nodimming        | boolean   | true/false or 0/1 | true                      | common                | usage not clear; found for orb1/2/3; |
| norndframe       | boolean   | true/false or 0/1 | 1                         | chesspiece, dynamic   | usage not clear; found for orb1/2/3, fxm_water_spurt_cast, ui_sounds |
| receiver         | string    | bones             | bones                     | chesspiece            | usage not clear; found for skeleton-type units, including infernodragon(1|2|3)  |
| hitdist          | int       | 0-x?              | 10                        | chesspiece            | found for catapult only; probably, limits hit distance |
| apass            | int       | 2,3               | 2                         | common                | the delay between actions?  |
| infobox.msgbox   | string    | ?                 | ?                         |                       ||
| infobox.hint     | string    | ?                 | ?                         |                       ||
| aggro_sound      | string    | ?                 | demon_aggro               | army                  | sound for attacking hero on map |
| minimap_pic_size | string    | ?                 | BIG                       | army                  | minimap dot size |
| minimap_pic_type | string    | ?                 | FRIEND                    | army                  | minimap dot color |
| turn_speed       | double    | ?                 | 1.5                       | army                  | hero turning speed |
| walk_speed       | double?   | ?                 | 1                         | army                  | hero walking speed |
| run_speed        | double?   | ?                 | 4                         | army                  | hero running speed |
| selfdestruct     | int       | 0-1               | 1                         | common                | in how many turns this object will disappear |
| cursor           | string    | ?                 | take                      | army                  | cursor form on hover |
| lutemplate       | string    | ?                 | template_item_mb          | army                  | usage not clear |
| ttl              | int       | 0                 | 0                         | -                     ||
| speed            | int       | 0-x               | 20                        | -                     ||
| mapicon          | int       | 0-x               | 20                        | -                     ||
| radar_radius     | int       | 0-x               | 20                        | -                     ||
| decal            | int       | 0-x               | 20                        | -                     ||
| instanced        | int       | 0-x               | 20                        | -                     ||
| ttl              | int       | 0-x               | 20                        | -                     ||
| addangle         | int       | 0-x               | 20                        | -                     ||
| cooldown         | int       | 0-x               | 20                        | -                     ||

#### Model
Example of usage:
```
model=cyclop.bma
```
```
model {
    0=cyclop.bma
    1=cyclop_death.bma
}
```
```
  model {
    0=death.bma
    1=clip_icemagic.bma
    2=deathred.bma
  }
```
0 is for living model, 1 is for death animation model.

#### Infobox
Example of usage:
```
infobox {
    msgbox=cpn_hint_alienegg
    hint=enemy_hint
}
```

#### Class
| classname     | count | description   |
| - | - | - |
| chesspiece    | 180   | battlefield unit objects info |
| pawn          | 185   | battlefield spawned unit objects info |
| throwable     | 505   | battlefield throwable objects info |
| spirit        | 4     | battlefield magic objects info |
| hollow        | 129   | battlefield effect objects info |
| castle        | 243   | map objects info |
| bridge        | 109   | map objects info |
| platform      | 9     | map objects info |
| land          | 10    | map objects info |
| npc           | 303   | map npc's info |
| hero          | 4     | hero's info |
| army          | 291   | map army info |
| boat          | 16    | map boats info |
| box           | 162   | small objects info |
| static        | 1925  | static objects info |
| dynamic       | 383   | battlefield unit info |
| multistate    | 0       | battlefield unit info |

##### Class Examples

###### Throwable
```
main {
  class=throwable
  model=slime.bma
  speed=20
  nodimming=true
  spawnscale=1.01
  blend=1
  ttl=4.0
}
```
###### Pawn
```
main {
  class=pawn
  nodimming=1
  model=fxm_bloodrune.bma
  blend=0
  apass=2
  cullcat=0
}
```
###### Castle
```
main {
  class=castle
  model=abbey.bms
  lutemplate=building_trader
  addangle=0
  cullcat=0
  mapicon=3
}
```
###### Bridge
```
main {
  class=bridge
  model=amazon_03.bms
  cullcat=0
  instanced=1
}
```
###### NPC
```
main {
  class=npc
  model=altar_courage.bms
  turn_speed=2.0
  walk_speed=1.2
  run_speed=2.5
  lutemplate=NPC_template
  minimap_pic_size=BIG
  minimap_pic_type=FRIEND
  cullcat=0
  infobox {
    hint=hint_default_text
  }
}
```
###### Hero
```
main {
  class=hero
  turn_speed=2.5
  walk_speed=7.0
  radar_radius=40
  nodimming=true
  sloping_v=1
  sloping_h=0
  specialhero=hero_olaf
  cullcat=0
  model {
    0=ork_horse.bma
	1=ork_horse_wings.bma
  }
}
```
###### Army
```
main {
  class=army
  model=ah_free_cavalry.bma
  aggro_sound=horseman_aggro
  minimap_pic_size=BIG
  minimap_pic_type=FRIEND
  turn_speed=2.0
  walk_speed=1
  run_speed=3.8
  cullcat=6
  infobox {
    hint=enemy_hint
  }
}
```
###### Box
```
main {
  class=box
  model=statuedwarf02.bms
  lutemplate=template_item_altar
  cooldown=0
  cullcat=6
  infobox {
    hint=globstr_1947623135
    msgbox=globstr_1569319261
  }
}
```

### Action Scripts
| script        | creature  | description   |
| ------------- | --------- | ------------- |
| moveattack    | a lot | 
| use_rune1     | a lot |
| use_rune2     | a lot |
| use_rune3     | a lot |
| take          | cerberus  |