<img width="2541" height="1390" alt="image" src="https://github.com/user-attachments/assets/59c1db0c-ac0c-49e0-93a0-c3e3049ca0ec" />

`setting up`

1. install java, [temurin](https://adoptium.net/temurin/releases) is recommended
2. install [prism launcher](https://prismlauncher.org/download/windows/) and configure it with your minecraft account
3. right click > create instance, import the modpack from [this repo](https://github.com/felinefyi/gamium-mc/raw/refs/heads/main/Brainium.zip)

`right click` > `edit` to browse instance settings and make it your own -- entirely optional, of course. in particular **you may want to enable/add mods from the `mods` menu**,
enable/install `resource packs` (higher resolution textures significantly increase render cost!), or modify `settings` > `java` custom parameters.
i have included the recommended set of parameters for java 11+ as detailed in [this post](https://github.com/brucethemoose/Minecraft-Performance-Flags-Benchmarks?tab=readme-ov-file#base-java-flags).

if you have issues launching, you may need to adjust these, but they should work with any modern adoptium temurin installation. note that prism launcher has separate settings for the `Xmx` and `Xms` flags which are configured upon installing prism.
the pack comes with `4GB Xmx` (maximum allocation) preconfigured; if you have poor performance when rendering large areas, you can increase it to up to 80% of your available memory. you may want to close any open browsers if you approach the limit.
if you are particularly concerned about performance, it is recommended to match both `Xmx` and `Xms` to avoid having to dynamically allocate more memory while playing.

`about`

the server aims to be a mostly faithful experience with a few general enchancements and quality-of-life improvements, primarily centered around world generation.
hopefully, this world should be more beautiful and rewarding to explore than a typical vanilla experience. here's what you can look forward to:

- considerably more biome variety
- more lifelike terrain generation
- more details added to existing structures
- additional structures to discover

the server is 100% vanilla compatible. just play with any **1.21.7** client and you should be able to connect.
however, playing with the modpack is highly recommended for the following:

- proximity voice chat
- world map & player markers
- many visual improvements
- preconfigured multiplayer menu
- no chat reports client support

`gamerules`

- doMobGriefing (creeper explosions, enderman block displacement) is currently disabled, but planned to re-enable after a period to allow players to settle
- game difficulty is set to normal. this means curing zombie villagers is not guaranteed, but mobs do less damage
- keepInventory is disabled. there is no tombstone mod installed. see `useful commands` for ways to help yourself survive

these are all subject to change at the whim of the spirit of fun.

`configuration`

the pack comes preinstalled with several mods to improve your experience, including proximity voice chat, shaders and LoD rendering, and performance improvements.

not all mods are enabled by default: there are a few mods in the mod folder which have the `.disabled` extension added.
simply remove this extension to enable them.

here is a summary of the disabled mods, what they do, and why they are disabled:

- `voxy`: LoD rendering, caches low-resolution data of terrain to render at great distances. highly experimental, water rendering is not supported with shaders. may slowly fill space on disk.
- `bobby`: overrides server-side chunk render distance limit. unnecessary without voxy, incurs performance overhead
- `c2me`: multi-threaded chunk loading. requires very modern java installation, experimental, but may make exploration smoother.
- `sound physics`: applies audio effects like reverb and filters to in-game audio, including voice chat. rather expensive on cpu, effect can be jarring.

`graphics`

a fork of photon shaders with support for voxy are preinstalled. shader options are available via `options` > `video settings` > `shader packs` (top right).
the `shader pack settings` menu has many available tweaks, but i recommend selecting a preset that suits your hardware.

if you do make any modifications, here are some useful notes to keep in mind:

- `fog` > `border fog` should be `off` to avoid occluding distant voxy chunks
- `sky` > `clouds` > `scale` has been reduced to 5x to increase cloud height, since low clouds cause some visual glitches at high altitudes

`useful keybinds`

i recommend visiting the keybinds menu to remap to your preferences. a few modifications have already been made, but all other binds are vanilla defaults.

vanilla binds refresher:

```
WASD  move
E     inventory
Tab   player list
Ctrl  sprint
Shift crouch (prevents walking off ledges)
F     swap offhand
Q     drop item
T     open chat
```

custom binds:

```
V  set up voice chat
C  toggle mute/unmute
R  toggle push-to-talk
Z  zoom (requires telescope)
M  open world map
\  toggle minimap
[] zoom minimap
+  quick waypoint
```

`useful commands`

essential commands has been installed, which provides access to several utility functions. here is a brief list of them:

```
/nickname set <nickname> . set a nickname for yourself
/tpa <playername>          send a request to teleport yourself to a player (they must accept)
/home set  . . . . . . . . set your personal home
/home tp                   teleport to your personal home
/spawn . . . . . . . . . . teleport to spawn
```

`troubleshooting`

need more perf? here's a prioritized list of frame-boosting recommendations:

1. lower your shader preset: `video settings` > `shader packs` (top-right) > `shader pack settings` > `preset` (highest impact)

- it is recommended to do this from the main menu to avoid recompilation
- alternatively, disable shaders entirely. this will provide the highest possible FPS

2. disable any high-res (32x or higher) resource packs (not installed by default): `resource packs` > use the large arrow icon to move back to the 'available' list (high impact)

- don't worry about packs marked as 'incompatible', this is almost always an over-assessment by minecraft when loading legacy packs. trust the pack listing by the developer.

3. if `voxy` is enabled, lower `voxy` quality: set `video settings` > `voxy` > `pixels^2 of subdivision size` to 128/256 (medium impact)

- alternatively, disable `voxy` and `bobby` entirely

4. reduce your render ranges:

- `video settings` > `general` > `render distance`: 8 is reasonable (medium impact)
- `video settings` > `general` > `simulation distance`: 12 is default, would not reduce past 6 (low impact)

5. lower `video settings` > `quality` options:

- `graphics`: fast
- `clouds`: off
- `weather`: fast
- `leaves`: fast
- `particles`: decreased
- `smooth lighting`: disabled

if you are still having trouble with framerate (or had to go more than 2 deep into this list), message me directly and i will provide direct support to improve your experience.
