# Troubleshooting

Start with **Settings -> Debug**: it shows the frame rate, the preset, the counters and a **Hooks** line that reports
which features are active, which are idle and the first reason. Then try **Advanced -> Safe mode (all risky modules
off)**, which turns off everything that changes what is drawn, ticked or loaded and keeps the settings reachable.

## The game crashes on start

1. Remove every other mod except **Fabric API** and PotatoPerf, then start again. If it works, add the other mods back
   one at a time.
2. Check that Fabric API matches your exact Minecraft version and that you use the PotatoPerf jar for that same
   version. A mismatched jar is refused by Fabric.
3. Check that your Java version is the one your Minecraft version requires. The 26.x line needs Java 25.
4. If it still crashes with only Fabric API installed, delete the PotatoPerf jar, start the game once, then put it
   back and choose **Potato**. Attach `latest.log` and the crash report to a bug report.

## It crashed once and now a feature is off

That is the crash guard: a module that threw is disabled on the next launch so the game starts. The **Advanced** tab
shows `Recovered: <module> was disabled`. Re-enable it only if you know the cause, or leave it off and report the crash
with the log.

## Sodium or Iris is installed

- The startup crash with Sodium is addressed by leaving the overlapping terrain work idle before it can run.
- If the game still crashes, confirm you do not have two terrain renderers installed, and report the crash with the
  full mod list and `latest.log`.
- With Sodium, terrain counters may read `n/a`. That is expected: PotatoPerf does not measure another renderer's work.
- The overlap line in **Debug** names what was detected.

## Mod Menu is not installed

You do not need it. Press `Right Shift + O` to open the settings. If that key does nothing, another mod may use it;
install Mod Menu to open the settings from the mod list instead.

## The settings do not open

- Press `Right Shift + O` while in a world, not while the game is still loading.
- Check the keybind in **Options -> Controls** for a conflict.
- Install Mod Menu and open the settings from the mod list.

## The overlay is missing

The overlay is off by default. Press `F9`, or use **Memory -> Live debug overlay** or **Debug -> Toggle overlay**.

## The game is slower after installing

1. Choose **Quality** to confirm the cause is one of the visual features.
2. Turn modules off one at a time in **Advanced**, starting with **Chunk Rendering** and **View-Focus Rendering**.
3. Check the overlap line in **Debug**. Two mods doing the same thing can cost more than either alone.
4. On a phone, lower `-Xmx` if the launcher is being killed, and use **Potato** with a shorter render distance.

## A feature is listed as unavailable

**Debug** lists each unavailable feature with a reason. The usual causes:

- **The game version does not expose what the feature needs.** Reduced-feature builds leave out terrain and renderer
  extras for this reason. Everything else keeps working.
- **Another renderer already handles it.** With Sodium or a similar mod installed, overlapping terrain work stays idle
  on purpose.
- **The feature was disabled after an error.** The crash guard turned it off; the reason says so.

A feature is never shown as active when it is not. There is nothing to fix on your side for the first two cases.

## The counters show `n/a`

`n/a` means the value cannot be measured on your renderer, usually because another renderer owns that part of the
pipeline. It is deliberate: a counter that cannot be measured is never written as a false zero.

## Launchers: MJLauncher, Pojav and the Pojav family

- Use the launcher's own JVM argument field for `-Xmx`. Do not duplicate it in two places.
- Put PotatoPerf in that instance's `mods` folder, not in a shared folder used by another instance.
- If the launcher is killed while loading, lower `-Xmx` by 256 MB and use **Potato**. On a 4 GB phone use about
  2048 MB, not 4096 MB: Android needs the rest.
- Use the **Copy <n> GB device JVM args** actions on the **Memory** tab for a ready-made argument set.
- On a translation layer (LTW, GL4ES, ANGLE, MobileGlues, VirGL, Zink), prefer the **Potato** preset, keep the
  resolution modest, and expect some counters to read `n/a`.
- If the screen is black but the game is running, try another renderer in the launcher before changing PotatoPerf
  settings.

## Logs are empty

- Check **Logs -> Session logging** is on and the level is **Normal** or **Detailed**.
- Use **Open logs folder (path copied)** to confirm where the files are written.
- A new session starts on the next launch; the current one may still be open.

## The report bundle does not appear

- Check free space on the device.
- Export it from a world; the bundle needs an active session.
- If it still fails, the game log records the reason. Report that line instead.

## Nothing here helped

Collect the report bundle from **Settings -> Logs -> Export report bundle**, note your device, launcher, renderer and
the exact Minecraft version from the supported versions table, and send it with the [bug report](REPORT_A_BUG.md)
template.
