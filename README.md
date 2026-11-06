# PotatoPerf

**PotatoPerf is a client-side performance companion for Minecraft Java Edition (Fabric), built for weak and mobile
devices and safe on a normal PC.**

It does not promise a fixed frame rate. It removes work your client does not need, keeps the frame time steadier, and
reports honestly what it changed and what it could not measure. It never changes gameplay, world data or anything the
server sees.

| | |
|---|---|
| **Minecraft** | every version in the table below; one jar per version |
| **Loader** | Fabric Loader and Fabric API |
| **Java** | the Java version your Minecraft version requires |
| **Side** | client only |
| **Author** | SJGAMER92 |
| **Version** | 1.6.0 |

## Supported Minecraft versions

<!-- supported-versions:start -->
- 1.21.11 - tested on a device
- 1.21.10 - tested on a device
- 1.21.9 - tested on a device
- 1.21.8 - tested on a device
- 1.21.7 - tested on a device
- 1.21.6 - tested on a device
- 1.21.5 - tested on a device
- 1.21.4 - tested on a device
- 1.21.3 - tested on a device
- 1.21.2 - tested on a device
- 1.21.1 - tested on a device
- 1.21 - tested on a device
- 26.1 - tested on a device
- 26.1.1 - tested on a device
- 26.1.2 - tested on a device
- 26.2 - tested on a device
- 26.3 - tested on a device
<!-- supported-versions:end -->

Download the jar that matches your exact game version and drop it in `mods`. A mismatched jar is refused by Fabric
instead of loading half-way.

## What it does

- **Hardware-aware presets.** On first launch PotatoPerf reads device RAM, CPU threads and the GPU renderer string,
  then applies Potato, Low, Balanced or Quality. You can change the preset at any time.
- **Adaptive quality.** Below your minimum frame rate, quality steps down; once the frame rate is comfortable or
  stable, it steps back up. Both thresholds are yours to set.
- **Entity and block-entity culling.** Things outside your view or beyond a distance are not drawn. Players, bosses,
  named and glowing entities are always kept unless you opt in.
- **Particle limits.** A real cap on living particles per effect and in total, plus a render budget on the lowest
  presets. Explosions, totems and sonic booms are never refused.
- **Chunk and terrain budgets.** A cap on simultaneous chunk builds, a rebuild budget, an upload time budget and a
  spread-out join warm-up keep the first seconds after a join smooth without changing what is in the world.
- **Menu and UI savings.** Optional removal of the menu blur, a static panorama and no chunk fade.
- **Session logs and a report bundle.** One zip for bug reports, with no username, server address or exact
  coordinates.
- **Honest counters.** A counter that cannot be measured on your renderer says `n/a`, never a false zero.
- **Sodium companion.** With Sodium or another terrain renderer installed, overlapping terrain work stays idle and the
  rest keeps working. PotatoPerf is not a replacement for Sodium.

## Requirements

- **Fabric Loader** for the Minecraft version you play.
- **Fabric API** for that same version.
- **The Java version your Minecraft version requires.** The 26.x line needs **Java 25**.
- Optional: **Mod Menu**, to open the settings from the mod list.

PotatoPerf is client side only. A server does not need it and nothing is installed on the server.

## Install

1. Install **Fabric Loader** for your Minecraft version.
2. Put **Fabric API** in your `mods` folder.
3. Put the PotatoPerf jar for the **same** Minecraft version in `mods`.
4. Optional: install **Mod Menu** to open the settings from the mod list.
5. Start the game. On first launch PotatoPerf detects the device and applies a preset.

**Keys:** `Right Shift + O` opens the settings. `F9` toggles the overlay. `F8` marks a moment in the session log.

## Diagnostics and privacy

Settings -> Logs -> **Export report bundle** writes a zip under `potatoperf/exports`. It contains the session summary,
frame counters, spike entries, events and a diagnostics file. It never contains your username, your home path, your
server address or exact coordinates. Attach it to a bug report and say which device, launcher and renderer you use.

## Links

- **Modrinth page:** coming soon
- **Support and bug reports:** coming soon

Until the pages are live, keep the report bundle ready; the Logs tab's **Report a bug** action will point at the
Modrinth page as soon as it exists.

## License

All Rights Reserved, Copyright (c) SJGAMER92. See `LICENSE`.

The source code is not public. Modpacks, servers, videos and reviews are welcome under the permissions in `LICENSE`.
