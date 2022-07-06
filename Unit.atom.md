# Combat Unit File Desciphration

## General Info
- Unit info file are located in `%_base_folder_%/data/data.kfs/%unit_name%.atom` or `%_base_folder_%/sessions/darkside/ses.kfs/%unit_name%.atom`;
- Unit filename could be found in `/sessions/darkside/loc_ses.kfs/<lng>_units.lng`: it contains unit names, single (`cpn_*`) or plural (`cpsn_*`);

Regexp pattern - `^main \{[a-zA-Z\s=\._\d\{\}]+class=chesspiece`

## File Content
```
main{}
    class
    model{}
    cullcat
    infobox{}
arena_params{}
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
| name          | type      | values            | example                   | req? | description  |
| -             | -         | -                 | -                         | -    | - |
| class         | string    | see below         | chesspiece                | Y    | common; game object type |
| model         | string    | *.bma             | chosha.bma                | Y    | common; model to use |
| cullcat       | int       | 0-10              | 0                         | N    | common; usage not clear |
| colmesh       | string    | collision_*.cms   | collision_alchemist.cms   | N    | common; collision mesh to use |
| bboxanim      | int       | 1                 | 1                         | N    | chesspiece; usage not clear  |
| nodimming     | boolean   | true/false        | true                      | N    | usage not clear |
| apass         | int       | ?                 | ?                         | N    | pawn   |
| spawnscale    | double    | ?                 | ?                         | N    | chesspiece,pawn; model scale to use; found for gorguana, gorguana2, viking  |
| infobox       | double    | ?                 | ?                         | N    | pawn  |
| receiver      | string    | ?                 | bones                     | N    | chesspiece; found for skeleton-type units  |
| hitdist       | int       | 0-x               | 10                        | N    | chesspiece; found for catapult  |
| blend         | double    | 0-1 (?)           | 0.85                      | N    | chesspiece; allows model to be transparent |
| norndframe    | int       | ?                 | 1                         | N    | chesspiece; found for orb1,orb2,orb3  |

| aggro_sound       | string    | ?                 | demon_aggro       | N    | army; sound for attacking hero on map |
| minimap_pic_size  | string    | ?                 | BIG               | N    | army; minimap dot size |
| minimap_pic_type  | string    | ?                 | FRIEND            | N    | army; minimap dot color |
| turn_speed        | double    | ?                 | 1.5               | N    | army; hero turning speed |
| walk_speed        | double?   | ?                 | 1                 | N    | army; hero walking speed |
| run_speed         | double?   | ?                 | 4                 | N    | army; hero running speed |
| selfdestruct      | boolean?  | 0,1?              | 1                 | N    | army; usage not clear |
| cursor            | string    | ?                 | take              | N    | army; cursor form on hover |
| lutemplate        | string    | ?                 | template_item_mb  | N    | army; usage not clear |

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
0 is for living model, 1 is for death animation model.

#### Infobox
Example of usage:
```
infobox {
    msgbox=cpn_hint_alienegg
    hint=enemy_hint
}
```

#### Class:
- chesspiece
battlefield units
- pawn
spawned battlefield units
- throwable
throwable battlefield objects
- castle
- bridge
- platform
- land
- hollow
- spirit
- npc
- hero
- army
- boat
- box
- static
- dynamic
- multistate


### Action Scripts
| script        | creature  | description   |
| ------------- | --------- | ------------- |
| moveattack    | a lot | 
| use_rune1     | a lot |
| use_rune2     | a lot |
| use_rune3     | a lot |
| take          | cerberus  |