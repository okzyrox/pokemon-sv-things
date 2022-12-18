`findings.md`
# findings from the datamining

(this information was gathered from a profiling log by using Ryujinx 1.1.476, which happens when the game thread is terminated)


## 'mons' section

In the 'mons' section, there are six entries, presumably for the 6 possible pokemon that a person can have on a team.

example of a team with just 'Sprigatito' (national id of 906, paldea id of 001)
```json
    "mons_no_1": "0906_00", 
    "mons_lv_1": 6,
    "mons_no_2": "",
    "mons_lv_2": -1,
    "mons_no_3": "",
    "mons_lv_3": -1,
    "mons_no_4": "",
    "mons_lv_4": -1,
    "mons_no_5": "",
    "mons_lv_5": -1,
    "mons_no_6": "",
    "mons_lv_6": -1,
```

As you can see, it has the national id for the pokemon first, then and underscore to seperate 2 0's (what i presume to be for determining if its a shiny or not but thats just speculation)

Underneath the mon and its number in the party, is the level of it, ranging from 1-100 and -1 if there isnt a party member in the spot.

```json
    "mons_lv_1": 6,
```

## Stats and Cash

Afterwards, you have a pretty-easy-to-understand section of how much LP and CASH your player has.
```json
    "money": 300,
    "lp": 0,
```

Then, you have what I believe to be summaries of how many pokemon you have encountered, battled, caught, etc. Although, I believe it may be innacurate due to none of the values changing from `'-1'`, even after battling Nemona and receiving our starter.

```json
    "meet_pkmn_sum": -1,
    "get_pkmn_sum": -1,
    "run_pkmn_sum": -1,
    "defeat_pkmn_sum": -1,
    "s_battle_sum": -1,
    "s_battle_result_great_sum": -1,
    "s_battle_result_good_sum": -1,
    "s_battle_result_bad_sum": -1,
    "zr_battle_sum": -1,
    "zr_battle_back_attack_sum": -1,
    "gem_sum": -1,
    "npc_battle_sum": -1,
    "hidden_item_sum": -1,
    "raid_play_sum": -1,
    "wazamachine_machine_sum": -1,
    "outbreak_sum": -1,
    "emote_sum": -1,
    "symbol_gem_meet_sum": -1,
    "symbol_gem_ko_sum": -1,
    "symbol_gem_get_sum": -1,
    "photo_mode_sum": -1,
```
It also included 'summaries' for other things like 'photo_mode' and 'hidden_item', suggesting they may be flags that tell the game whether your doing something at the moment, such as battling or doing Tera raids.

## DLC?

After all of that, there is a flag sent named 'dlc_flag', defaulting to `'0'` naturally as there is no dlc available currently, but it alludes to the conspiracy of whether there will or will not be DLC for SV.

```json
    "dlc_flag": 0,
```

## Other Games & The Pokédex

Moving back to the top of the profiling, you have the values to tell the game whether you own/have played the previous pokemon games on your device, if yes I assume the value turns to `'1'` and the game allows you to access certain perks, such as the Pokémon Legends: Arceus Phone Case if you own the game, and others.

```json
    "play_pikavee": 0, - lets go pikachu and eevee
    "play_swsh": 0, - sword and shield
    "play_bdsp": 0, - brilliant diamond and shining pearl
    "play_pla": 0, - pokemon legends: arceus
    "play_home": 0, - pokemon home (?)
```

Right underneath that you have the values for how many different pokemon you have caught, and how many different pokemon you have encountered; this is for the 'pokedex menu' which shoes the unique pokemon enoucountered aswell as the number of unique pokemon caught.
```json
    "pokedex_cap": 1, - Sprigatito
    "pokedex_cnt": 2, - Sprigatito and Quaxly (rival)
```

## Other stuff

Badge count
```json
    "badge_count": 0,
```

Team Circle (probably for the number of players currently connected)
```json
    "team_circle": 0,
```

"Is the user connected to the internet (ingame)?"
```json
    "internet": 0,
```

## conclusion
most of the other information is pretty self-explanatory and boring so if you'd like you can read through it in the `profiling.json` file.
