# Settings reference

Open the settings with `Right Shift + O`, or from Mod Menu if it is installed. Eight tabs run down the left side:
**Presets**, **Rendering**, **Entities**, **Chunks**, **Memory**, **Logs**, **Advanced** and **Debug**.

Every switch ends with `ON` or `OFF`. Every slider shows its current value and unit. Long-press or hover a control for
its tooltip. `Done` saves and closes.

A reduced-feature build shows fewer rows: a feature that the game version cannot support is left out of the tab and
listed as unavailable in **Debug** with the reason.

## Presets

- **Auto-select preset** - reads device RAM, CPU thread count and the OpenGL renderer string, then applies Potato, Low
  or Balanced. Run it once after installing on a new device.
- **Potato preset**, **Low preset**, **Balanced preset**, **Quality preset** - applies that preset immediately and resets
  dynamic scaling. The active preset is marked with `>`.
- **Auto preset on hardware change** - on first launch, and when the detected GPU/CPU/RAM fingerprint changes, applies
  Potato, Low or Balanced. A manual preset choice turns this off.
- **Dynamic quality scaling** - lowers distances, particle and chunk budgets only while the frame rate is below your
  minimum, and raises them at the comfort level or after stable frame time.
- **Module: Dynamic Scaling** - master switch for the whole module.

## Rendering

- **Module: View-Focus Rendering** - master switch for the culling features on this tab.
- **Entity culling** - entities outside the camera cone or beyond the distance below are not drawn. Bosses, glowing,
  named and mounted entities are always kept unless you opt in.
- **View-cone culling** - entities behind the camera are culled, with a margin so turning never pops them in visibly.
- **View-cone half-angle** - 60 to 170 degrees in steps of 5. 100 keeps a useful margin; 170 is nearly off.
- **Entity render distance** - 0 to 256 blocks in steps of 8. 0 disables distance culling. Does not affect ticking or
  gameplay.
- **Entity render cap** - 0 to 512 entities in steps of 8. Renders at most this many by shrinking an adaptive distance.
  Near entities, players, bosses, named and glowing entities are always kept. 0 is off.
- **Mob distance** - 0 to 256 blocks. Separate render distance for mobs and players; 0 uses the general distance.
- **Dropped item distance** - 0 to 128 blocks.
- **Item frame distance** - 0 to 128 blocks.
- **Armor stand distance** - 0 to 128 blocks.
- **Cull other players** - off by default, because hiding players is a gameplay disadvantage.
- **Cull glowing entities** - off by default; glowing outlines are a gameplay signal.
- **Cull named entities** - off by default; named pets and villagers stay visible.
- **Cull entities behind walls** - off by default. A cheap wall test that can hide a partially visible entity at a
  corner.
- **Block entity culling** - chests, signs, banners, beds and other block entities beyond the distance below are not
  drawn. Chests remain usable and no data is changed.
- **Block entity distance** - 0 to 256 blocks. 0 disables the cap.
- **Block entities behind walls** - off by default. Adds a cheap wall test for chests and signs.
- **Particle culling** - particles beyond the distance below are skipped and how many new particles are accepted per
  tick is capped. Purely visual.
- **Particle distance** - 0 to 128 blocks. 0 disables distance culling.
- **Particle budget** - 0 to 5000 new particles per tick in steps of 100. 0 means unlimited. A low budget can visibly
  thin explosions and rain on purpose.
- **Particle cap per type** - 0 to 1000 per particle type in steps of 10. 0 disables the per-type cap. Explosions,
  totems and sonic booms are never capped.
- **Rain particle interval** - 1 to 10 ticks. 1 is vanilla; 3 runs the rain spawn pass every third tick and cuts that
  fixed cost. Rain columns still render normally.
- **Rain particle radius** - 0 to 10 blocks. Caps the radius of the rain spawn scan; 0 keeps the vanilla weather radius.
  A smaller radius means fewer splash particles near you, not less rain.
- **Alive particle cap** - 0 to 2000 alive particles in steps of 50, enforced before a particle is created. 0 is off.
  Explosions, totems and sonic booms are never refused.
- **Alive cap per type** - 0 to 500 living particles of one type in steps of 5, sampled every 10 ticks. 0 is off.
- **Particle render budget** - 0 to 20 ms. If particle rendering stays over this for 3 seconds, the effective alive cap
  shrinks until it fits, and the types that dominate are written to the spike log. 0 is off.
- **Simplify distant particles** - keeps one in three particles beyond 60% of the particle distance. Off by default;
  makes far rain and smoke lighter without moving or removing nearby effects.
- **Culling margin** - 0 to 32 blocks in steps of 2. Extra distance added to every culling test so entities do not pop
  when the camera turns.

## Entities

- **Module: Entities & Particles** - master switch for the features on this tab.
- **Distance tick throttling** - items, armor stands and item frames outside the distances below tick at a quarter rate.
- **Throttle dropped items** - far item merging and despawn logic runs at a quarter rate. No item loss.
- **Item tick distance** - 8 to 128 blocks in steps of 8. Items closer than this tick normally; distant items tick one
  in four.
- **Throttle armor stands** - far armor stands skip three of four client-side animation ticks.
- **Armor stand tick distance** - 8 to 128 blocks in steps of 8.
- **Throttle item frames** - far item frames update their map and rotation animation less often.
- **Item frame tick distance** - 8 to 128 blocks in steps of 8.
- **Throttle mobs (AI visible to you)** - throttles only the client-side animation of distant mobs to one tick in four.
  It never runs on the server and cannot change mob AI results; very distant movement may look slightly stepped.
- **Mob tick distance** - 8 to 256 blocks in steps of 8. Only used when mob throttling is on.
- **Far entity LOD** - far mobs keep their base model but skip render layers: armor, held items, banners, custom heads
  and elytra. Players, bosses, glowing and named entities always keep full detail. Off by default.
- **Entity LOD distance** - 16 to 128 blocks in steps of 8.
- **Entity shadow distance** - 0 to 64 blocks in steps of 4. Skips the shadow for entities farther away. 0 disables the
  cut.
- **Freeze far animations** - freezes age-based animation and limb swing past the distance below. Off by default; can
  look static. Position, rotation and head tracking stay live.
- **Freeze farther than** - 16 to 160 blocks in steps of 8.

## Chunks

- **Module: Chunk Rendering** - master switch for the features on this tab.
- **Chunk build slots** - 0 to 16 jobs. Caps how many chunk sections are built at the same time. 0 leaves vanilla
  unchanged. Applies after a game restart.
- **Chunk rebuild budget** - 0 to 64 rebuilds per frame in steps of 2. 0 leaves vanilla unchanged. Lower is smoother;
  higher fills distant chunks faster.
- **Chunk upload budget** - 0 to 12 ms. Per-frame budget for draining compiled chunk meshes. The rest stays queued and
  is retried next frame; the old mesh stays visible until it is replaced. 0 is vanilla.
- **Spread join work** - for four seconds after a join, chunk rebuilds, uploads and the entity render cap ramp from 25%
  to 100% instead of doing the whole burst in the first frames. Client-only and visual.
- **Entity tick attribution** - measures client entity-tick time by entity type and adds the top three to the spike
  log. Measurement only.
- **Skip empty section builds** - air-only sections return the empty result immediately instead of walking every
  position. Visuals are identical.
- **Prioritize deferred chunks** - when the per-frame budget defers work, the backlog is fed back nearest-to-camera
  first.
- **No chunk fade** - removes the chunk fade-in animation.
- **Far section cutoff** - 50 to 100% in steps of 5. Stops drawing whole chunk sections beyond this percentage of your
  render distance. 100 is off. Always reset to 100 when a Sodium-like renderer is present.
- **Section draw cap** - 0 to 2000 sections in steps of 10. Ceiling on chunk sections submitted per frame; vanilla
  feeds them nearest-first, so the farthest are dropped first. 0 is off.
- **Static-camera visibility cache** - skips the visibility update while the camera is completely still and nothing
  changed. It refreshes at least once per second and is invalidated by every world or block change.
- **Adaptive terrain budget** - lowers the section cap while measured terrain time is above the target and recovers
  slowly when there is headroom. The section draw cap is the ceiling.
- **Terrain budget target** - 2 to 30 ms. Lower values trim the section cap more aggressively; each change is logged.
- **Fog hides the section cutoff** - when the cap actually removes sections, the fog end is pulled in to the farthest
  drawn section so there is no visible hole.
- **Cave / wall section culling** - off by default because a wrong result could show a missing wall. Enable only if you
  accept a small visual risk.
- **Cave search radius** - 1 to 8 chunks. How far the cave visibility search spreads.
- **Cave search interval** - 10 to 120 ticks in steps of 5. How often cave visibility is recomputed.
- **Dynamic quality scaling** - steps quality down only below the minimum frame rate and back up at the comfort level,
  with cooldown and hysteresis.
- **Module: Dynamic Scaling** - master switch for the same module as on the Presets tab.
- **Minimum acceptable FPS** - 0 to 120 in steps of 5. 0 means automatic by hardware tier: 30 on the lowest tiers, 45
  on mid-range, 60 on high-end.
- **Comfortable FPS** - 0 to 180 in steps of 5. 0 means automatic, 1.25x the minimum. The gap above the minimum is what
  stops the ladder from oscillating.
- **Reset scaling thresholds to auto** - clears both thresholds so the hardware tier decides again.

## Memory

- **Module: Memory & GC** - master switch for the memory features.
- **Live debug overlay** - shows frame rate, 1% low, frame time, allocation rate, memory, GC, section, entity and
  particle counters, the unaccounted-time line and the current bottleneck verdict. Updates once per second.
- **Profiler overlay** - master switch for the on-screen profiler lines. The file log keeps recording while the overlay
  is hidden.
- **Detailed profiler lines** - adds per-layer draw counts and the sky, cloud, weather, fog, lightmap and tick
  sub-buckets to the overlay. The file log always contains them.
- **Profiler CSV log** - writes one line per second with frame, CPU, present/GPU wait, chunk build, entity, particle,
  GUI, GC, allocation and the counters. Rotated at 4 MB.
- **Copy profiler log path** - copies the absolute path of the profiler log.
- **GC stutter warnings** - warns in chat and in the log when a GC pause crosses the threshold.
- **GC warning threshold** - 40 to 500 ms in steps of 10. A warning is written at most once every 30 seconds.
- **Cap texture mipmaps** - reduces texture memory on low-memory devices. Applies on the next resource reload or
  restart.
- **Mipmap cap** - 0 to 4 mip levels. 2 is a good mobile compromise; 0 saves the most memory but adds texture shimmer.
- **Apply mipmap cap now** - sets the vanilla mipmap option, saves it, closes the screen and reloads resources.
- **Restore original vanilla options** - restores the vanilla options PotatoPerf changed from the value saved before
  the first change, then reloads resources. PotatoPerf's own settings are untouched.
- **Module: UI & Loading** - master switch for the UI savings.
- **No menu blur** - skips the full-screen blur in menus. Stays off automatically when a compatible UI mod is present.
- **Static panorama** - freezes the rotating panorama on low-end devices. Off by default because it is visible.
- **Copy 2 GB device JVM args**, **Copy 3 GB device JVM args**, **Copy 4 GB device JVM args**, **Copy 6 GB device
  JVM args**, **Copy 8 GB+ device JVM args** - copies a ready-made argument set for that amount of device RAM.
- **Copy JVM guidance** - copies the short explanation: use no more than about half of the device's physical RAM, do
  not duplicate `-Xmx` in the launcher, and lower it if the launcher is killed while loading.

## Logs

- **Session logging** - writes `potatoperf/logs/session-*/` with a summary, one CSV row per second, spike entries and
  events. All writes happen on one low-priority background thread; a full queue drops lines instead of freezing the
  game. No username, IP address, server address or exact position is written.
- **Log level** - cycles Off, Normal and Detailed. Detailed also writes an event line for each marked moment and each
  preset or scaling action.
- **Mark this moment** - writes a MARK line to the event log. `F8` does the same in game.
- **Open logs folder (path copied)** - copies `<game>/potatoperf/logs`. Sessions rotate at 10 folders or 50 MB.
- **Report a bug (Modrinth)** - opens the Modrinth bug-report page and copies the link. A placeholder until the public
  page is live.
- **Export report bundle** - zips the current session, the diagnostics file and a README into `potatoperf/exports`,
  then copies the path. Runs on a background thread.
- **Copy session folder path** - copies the current session folder, or the logs root when no session is active.
- **Logger cost: <n> ms** - the measured time spent building and queueing the latest frame row, not the disk write.

## Advanced

- **Module:** one switch for each of **View-Focus Rendering**, **Chunk Rendering**, **Entities & Particles**,
  **Memory & GC**, **Lighting & World**, **UI & Loading** and **Dynamic Scaling**. Enabling a module arms the crash
  guard; if the game crashes, that module is disabled automatically on the next launch.
- **Advanced logging** - writes culling and renderer detail to the game log. Leave off unless collecting a report.
- **Safe mode (all risky modules off)** - turns off every module that changes what is drawn, ticked or loaded, and
  leaves the profiler and the settings reachable.
- **Reset all settings** - click once to arm, again to confirm. Resets the settings to Balanced defaults; it does not
  delete the file or touch vanilla options.
- **Export diagnostics file** - writes a diagnostics file next to the config: versions, OS, CPU and memory, GPU and
  renderer, preset, enabled modules, live counters and mod ids. No user name, IP address or credential.
- **Singleplayer: lower render 8 / simulation 5** - saves your current vanilla distances, then applies 8 and 5 chunks.
  The integrated server shares the CPU, so this is the largest safe singleplayer win.
- **Restore saved render/simulation distance** - restores the distances saved by the action above.
- **Copy debug report** - copies hardware, settings, counters and conflicts.
- **Copy detected conflicts** - copies the overlap list for other optimisation mods.
- **Copy config path** - copies the absolute path of the config file.

## Debug

- **FPS sparkline** - adds a one-line frame-time sparkline to the overlay. It is a single text draw, not a graph.
- **Stutter attribution** - shows the most recent frame above the threshold and logs it at most every 5 seconds,
  attributed to chunk builds, entity extraction, particles, GC or GPU/other.
- **Stutter threshold** - 10 to 250 ms in steps of 5. 50 ms is roughly a visible hitch; 16 ms would flag normal jitter
  at a high frame rate.
- **Copy debug report** - hardware, settings, counters and conflicts for a bug report.
- **Copy recommended JVM args** - the recommendation for this device's memory.
- **Reset counters** - clears the live overlay and 1% low counters without changing settings.
- **Force garbage collection** - debug only. It can freeze the game for a moment and should not be used while playing.
- **Toggle overlay** - shows or hides the overlay.
- **Copy hardware info** - copies the detected GPU renderer and vendor and the memory values.

The Debug tab also shows seven live lines: frame rate and 1% low with the current scaling step and verdict; section
counts; entity and particle counts; memory and GC; overlapping mods and detected hardware; the last stutter; and a
**Hooks** line that reports how many features are active, how many are idle and the first reason.
