# TOB Respawn Script

## How To Use In a Mission
1. Create a new mpmission in-game.
2. Go to `Documents\Arma 3\{username}\mpmissions\{mission_name}\` and save all the files from this repo in the folder.
3. In the editor, select the Zeus unit (NOT the module, the unit) and give it a variable name of `God`.
4. Create empty game logic (Systems(F5) > Logic Entries > Objects > Game Logic (Vanilla)), and set variable name as `fw_respawn`.

## How It Works
1. **Entry point** - `init.sqf` - adds diary entry for admin and zeus to call in respawn and allows admin to call respawn wave via respawn command (`respawnWave`). Also adds 2 event listeners when player is killed to put them in spectator mode and run respawn logic when respawn wave is called.

2. **Save Loadout** - `initPlayerLocal.sqf` - saves the starting player loadout which is then used to apply the loadout when player respawns.

3. **Remove all gear** - `fnc_remoteAllGear.sqf` - removes all the gear a player has.

4. **Force player into spectator screen** - `fnc_spectateCheck.sqf`

5. **Run respawn logic** - `fnc_spectatePrep.sqf` - retrieves respawn point based on player side and respawns player with the kit saved from when the player joined at the respawn point.

### More Info
Script based on [Olsen Framework](https://github.com/dklollol/Olsen-Framework-Arma-3)
