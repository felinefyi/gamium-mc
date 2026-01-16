<img width="2541" height="1390" alt="image" src="https://github.com/user-attachments/assets/59c1db0c-ac0c-49e0-93a0-c3e3049ca0ec" />

`setting up`

1. install java, [temurin](https://adoptium.net/temurin/releases) is recommended
2. install [prism launcher](https://prismlauncher.org/download/windows/) and configure it with your minecraft account
3. right click > create instance, import the modpack from [this repo](https://github.com/felinefyi/gamium-mc/raw/refs/heads/main/Brainium.zip)

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

a fork of photon shaders with support for voxy are preinstalled. shader options are available via options > video settings > shader packs (top right).
the shader pack settings menu has many available tweaks, but i recommend selecting a preset that suits your hardware.

if you do make any modifications, here are some useful notes to keep in mind:

- `fog` > `border fog` should be `off` to avoid occluding distant voxy chunks
- `sky` > `clouds` > `scale` has been reduced to 5x to increase cloud height, since low clouds cause some visual glitches at high altitudes

`useful keybinds`

i recommend visiting the keybinds menu to remap to your preferences. a few modifications have already been made, but all other binds are vanilla defaults.

```
V  set up voice chat
C  toggle mute/unmute
M  open world map
\  toggle minimap
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
