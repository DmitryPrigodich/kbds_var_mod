# Combat Unit File Desciphration

## General Info
- Unit info file are located in `%_base_folder_%/data/data.kfs/%unit_name%.atom` or `%_base_folder_%/sessions/darkside/ses.kfs/%unit_name%.atom`;
- Unit filename could be found in `/sessions/darkside/loc_ses.kfs/<lng>_units.lng`: it contains unit names, single (`cpn_*`) or plural (`cpsn_*`);

## File Content
```
main{}
    class
    model
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
| name      | values    | description  |
| -         | -         | - |
| class     | see below | value defining what kind of object it will be |
| model     | *.bma     | model to use, should be in the same folder (?) |
| colmesh   | collision_*.cms     | collision mesh to use, should be in the same folder (?) |
| cullcat   | 0-10 | |
| bboxanim  | | |
| nodimming | boolean   | |

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