# Install

## What you need

- A **Minecraft Java Edition** version from the supported versions table in the [README](../README.md).
- **Fabric Loader** for that exact game version.
- **Fabric API** for that same version.
- **The Java version your Minecraft version requires.** The 26.x line needs **Java 25**.
- Optional: **Mod Menu**, to open the settings from the mod list.

PotatoPerf is client side only. A server does not need it, and nothing is installed on the server.

## Steps

1. Install **Fabric Loader** for the Minecraft version you play.
2. Open your game folder and find the `mods` folder. Create it if it does not exist.
3. Put **Fabric API** in `mods`.
4. Put the PotatoPerf jar for the **same** Minecraft version in `mods`.
5. Optional: put **Mod Menu** in `mods` too.
6. Start the game with the Fabric profile. On first launch PotatoPerf reads your hardware and applies a preset.
7. Press `Right Shift + O` to open the settings, or use Mod Menu.

Use exactly one PotatoPerf jar. A jar for a different game version is refused by Fabric instead of loading half-way.

## After installing

- The **Debug** tab shows the frame rate, the current preset, the counters and which features are active, idle or
  unavailable.
- `F9` toggles the overlay. It is off by default.
- `F8` marks a moment in the session log, so a hitch you felt can be matched with the frames around it.
- If your device still struggles, open **Presets** and choose **Potato**. If the game looks wrong, choose
  **Quality**, which only uses changes that do not alter what you see.

## Launchers

- **Desktop launchers** need nothing special; use the Fabric profile.
- **MJLauncher, Pojav and the Pojav family, Boardwalk and Fold Craft** are recognised from the launch environment.
  Use the launcher's own JVM argument field for `-Xmx` and put PotatoPerf in that instance's `mods` folder.
- If the launcher is killed while loading, lower `-Xmx` by 256 MB and use the **Potato** preset. A 4 GB phone should
  use a 2048 MB heap, not 4096 MB: Android needs the rest of the memory.

## Updating

1. Delete the old PotatoPerf jar from `mods`.
2. Put the new jar for the same game version in `mods`.
3. Start the game. Your settings are kept; new options take their preset value.

## Uninstalling

Delete the PotatoPerf jar from `mods`. PotatoPerf does not modify vanilla options permanently; anything it changed can
be restored from **Memory -> Restore original vanilla options** before removing it.
