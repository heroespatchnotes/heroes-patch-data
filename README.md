# Heroes Patch Data

## Resources

* [patchversions.json](patchversions.json)

### patchversions

* JSON file containing a list of patch objects for every patch in Heroes of the Storm

Example:

```javascript
{
    "internalId": "patch-notes-october-17-2017",
    "patchName": "Junkrat Patch",
    "officialLink": "http://us.battle.net/heroes/en/blog/21116539",
    "patchType": "Patch Notes",
    "gameVersion": "28.3",
    "fullVersion": "2.28.3.58623",
    "ptrOfficialLink": "http://us.battle.net/heroes/en/blog/21072302",
    "ptrDate": "2017-10-09",
    "ptrBuild": "58344",
    "liveDate": "2017-10-17",
    "liveBuild": "58623"
}
```

Some notes on the properties:
* `patchName` follows the naming convention of last hero released + type of patch (optional) + the word 'Patch' + number (optional, if multiple patches of the same type have been released without a new hero)
    * Examples: Chromie Patch, Chromie Hotfix Patch #1, Chromie Hotfix Patch #2, Chromie Balance Patch, Medivh Patch
    * Exceptions: the Launch Day patch and 2.0 Launch contain said terms in their name (e.g. `Genji Patch, 2.0 Launch`)
* `officialLink` property name will always appear, but its value may occasionally be `null` (ex: hotfix patches sometimes do not receive offical blog posts).  When `officialLink` is null, an `alternateLink` property should appear (which generally points to BlizzTrack's copy of the patch notes)
* `patchType` will have one of the following values: Patch Notes, Balance Update, Hotfix Patch
* `gameVersion` is the shortened version most often used to refer to a patch (e.g. 28.3 rather than 2.28.3)
* `fullVersion` is the full version number as found in the launcher
    * Some liberties have been taken with pre-Heroes 2.0 full version numbers.  Using [Gamepedia wiki's patch list](https://heroesofthestorm.gamepedia.com/Patches), and specifically the notion that Beta and earlier patches started with a major version of 0, it made sense that all patches between launch and the start of 2.0 should have the major version of 1.
* If a patch had a PTR, you'll find links to the PTR notes, the PTR release date, PTR build, and any additional PTR update patches as properties with `ptr` prepended.
    * Examples from above: `ptrOfficialLink`, `ptrDate`, `ptrBuild`
* `liveDate` is the date the patch hit the live servers in North America
* `liveBuild` is the build number for this patch, which should also match those used by [heroprotocol](https://github.com/Blizzard/heroprotocol)

## Credits & Thanks

* Big thanks to [@AhliSC2](https://twitter.com/AhliSC2) for sending some super old patch info my way, and for directing me to resources to locate historical hotfix patches
* Also thanks to [Vekkul and his The Patch History](https://us.battle.net/forums/en/heroes/topic/18301004598) post on the official forums, providing a great base from which to start
* The following websites were also utilized in creating this list:
    * [Atlas Industries' Heroes of the Storm wiki](https://www.atlasindustries.info/wiki/Heroes_of_the_Storm/Patch_11.1)
    * [BlizzTrack's patch notes](https://blizztrack.com/patch_notes/heroes_of_the_storm/)
    * [Gamepedia wiki's patch list](https://heroesofthestorm.gamepedia.com/Patches)
    * [heroprotocol on github](https://github.com/Blizzard/heroprotocol)
