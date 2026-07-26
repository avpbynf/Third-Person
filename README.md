<div align=center>

| English | [中文](./README-ZH.md) |
|---------|----------------------|

[![CurseForge downloads](https://img.shields.io/curseforge/dt/930880?style=flat&logo=curseforge&color=F1643%5E&cacheSeconds=3600&label=Downloads)](https://www.curseforge.com/minecraft/mc-mods/leawind-third-person)
[![Modrinth downloads](https://img.shields.io/modrinth/dt/S3D3QF0M?style=flat&logo=modrinth&color=17B85A&cacheSeconds=3600&label=Downloads)](https://modrinth.com/mod/leawind-third-person)

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/LEAWIND/Third-Person?tab=MIT-1-ov-file)
[![Stars](https://img.shields.io/github/stars/LEAWIND/Third-Person?style=flat&logo=github&color=daaa3f)](https://github.com/LEAWIND/Third-Person)

# Leawind's Third Person

A practical, smooth, feature-rich third person mod for all Minecraft players.

</div>

## Minecraft 26.1 port

> **This port now lives upstream.** It was merged as [Leawind/Third-Person#251](https://github.com/Leawind/Third-Person/pull/251) and released upstream as `v2.5.1-mc26.1`. Install the mod from [CurseForge](https://www.curseforge.com/minecraft/mc-mods/leawind-third-person) or [Modrinth](https://modrinth.com/mod/leawind-third-person) rather than from this fork. What follows is kept for reference.

This branch is an unofficial port of Leawind's Third Person 2.5.0 from Minecraft 1.21.11 to Minecraft 26.1, for both NeoForge and Fabric. All credit for the mod itself (features, design and assets) goes to [Leawind](https://github.com/Leawind) and the upstream contributors. Only the build toolchain and the hooks into the game changed.

What changed compared to 1.21.11:

- Build toolchain updated to Architectury Loom 1.17 (no-remap), Gradle 9.5 and Java 25. Minecraft 26.x ships de-obfuscated, so the Parchment mappings and the remap step are gone.
- The camera hook moved from `Camera#setup` to `Camera#alignWithEntity` and the FOV hook from `GameRenderer#getFov` to `Camera#calculateFov`, following the vanilla refactor.
- The crosshair hook and the entity visibility filtering still sit on `Gui#extractCrosshair` and `LevelRenderer#extractVisibleEntities`, which were only split out into `Hud` and `LevelExtractor` in 26.2.
- Player transparency now relies on the per-entity alpha path only, since the buffer flush it used was removed along with the immediate-mode pipeline. Armor translucency uses the vanilla `armorTranslucent` render type.
- Dependencies bumped for 26.1: Architectury API 20.0.9, Cloth Config 26.1.154, YACL 3.9.6, Mod Menu 18.0.0, MixinExtras 0.5.4.

To play, install [Architectury API](https://www.curseforge.com/minecraft/mc-mods/architectury-api) for your loader (required), plus [Cloth Config](https://www.curseforge.com/minecraft/mc-mods/cloth-config) or [YACL](https://modrinth.com/mod/yacl) if you want the in-game config screen (optional).

Now that the port is upstream, everything belongs on the [upstream issue tracker](https://github.com/Leawind/Third-Person/issues), the port included.

- **Client Side Only** No need to install on server. So you can join servers with this mod.
- **Free Rotation** Freely rotate the view while keeping the player's body stationary.
- **Free Adjustment of Camera Position**
	- While holding `Z`, moving the mouse adjusts the camera offset (the player's position on the screen), and the mouse
	  wheel adjusts the distance between the camera and the player
	- **Quick Switching of Camera Offset (Left|Center|Right)** Short press `CapsLock` to toggle between left and right.
	  Hold `CapsLock` to center the camera
- **Smart Aim Mode** Automatically switches to aim mode based on the item the player is holding and its using status.
  Rules can be customized. So it can be compatible with items from other mods
- **Shooting like first-person** When aiming at enemies in third-person, it predicts the target entity you want to shoot
  at, allowing you to simply place the crosshair above the enemy as if in first-person
- **Player Transparency** When the player entity obstructs the view, it becomes semi-transparent (May not be compatible
  with Sodium. This feature is disabled by default)
- **Smooth Perspective Switching** Smooth transition between first and third person perspectives
- **Disable Anytime** If the mod causes issues, you can disable it anytime in-game through the configuration menu or
  hotkey, reverting to the original third-person perspective

<div align=center>
<details>
<summary>Donates</summary>

<img alt=ΨQ src="https://github.com/Leawind/Third-Person/raw/gh-pages/docs/public/donate/IHY-216.jpg" width=648/>

> <details>
> <summary>Donate using Wechat</summary>
> <img alt=wechat src="https://github.com/Leawind/Third-Person/raw/gh-pages/docs/public/donate/wechat.jpg" width=320 />
> </details>
> <details>
> <summary>Other ways</summary>
>
> [Buy Me a Coffee](https://www.buymeacoffee.com/leawind)  
> [Afdian (爱发电)](https://afdian.com/a/Leawind)
>
> </details>

</details>
</div>
