# Report a bug

Thanks for testing. One report per problem, please.

## Before you report

1. Use the newest PotatoPerf release for your exact Minecraft version.
2. Reproduce the problem once with your normal settings and once with **Advanced -> Safe mode (all risky modules off)**.
3. Collect the report bundle: **Settings -> Logs -> Export report bundle**. The zip is written to
   `potatoperf/exports` and the path is copied for you.

## Template

Copy the text below into your report and fill in every line you can.

```text
### What happened

- What you did:
- What you expected:
- What actually happened:

### Device

- Phone or PC model:
- Android version and launcher (LTW / Pojav / other):
- RAM:
- Renderer line (Settings -> Debug, or the launcher log):
- PotatoPerf version:
- Minecraft version (from the supported versions table):
- Fabric Loader and Fabric API versions:
- Other mods (especially Sodium, Iris, Indium, Embeddium, EntityCulling):

### Settings

- Preset:
- Render distance and simulation distance:
- Was Sodium installed?
- Singleplayer or multiplayer (do not name the server):

### Files

- Report bundle attached: yes / no
- `latest.log` attached (if it crashed): yes / no
- Crash report attached (if it crashed): yes / no
- Screenshot of the Debug tab (if the overlay or HUD is involved): yes / no

### Optional

- Time since joining when it happened:
- Does it also happen with Spread join work off?
- Does it also happen with Safe mode on?
- Does it also happen without Sodium?
```

## What not to include

- your username, home path, server address or exact coordinates;
- your full game folder;
- personal information of any kind.

The report bundle is already redacted for those. If you attach `latest.log`, check it for a server address first.

## After you report

A report without a bundle is much harder to diagnose. If you cannot export one, say so and include the exact frame
rate and frame time from the **Debug** tab instead.
