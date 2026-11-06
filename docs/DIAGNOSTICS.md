# Diagnostics

PotatoPerf measures your client and writes that measurement to files you own. Nothing is uploaded and nothing leaves
your device unless you attach a file to a report yourself.

## Session logs

With **Session logging** on (Logs tab), each game session writes a folder under `<game>/potatoperf/logs/`:

| File | What it holds |
|---|---|
| `session-summary.txt` | Versions, hardware, preset and modules, the counters, the feature health table and the settings that matter for the session. |
| `frames.csv` | One row per second: frame rate, 1% and 0.1% low frame time, the measured phases, counters, memory, GC and the current scaling step. |
| `spikes.log` | Every frame above 50 ms and more than twice the current average, with that frame's breakdown, the screen, the dimension, counts and the last actions. |
| `events.log` | Presets applied, scaling steps, terrain-budget changes, GC pauses, a module disabled after an error, slow screens, resource reloads, world changes and your `F8` marks. |

Logs rotate: 10 sessions or 50 MB, whichever comes first. The `exports` folder is excluded from rotation.

- **Log level** cycles **Off**, **Normal** and **Detailed**. Detailed adds an event line for each marked moment and each
  preset or scaling action.
- **Mark this moment** (or `F8`) writes a MARK line, so a hitch you felt can be matched with the frames around it.
- **Logger cost** shows the time spent building and queueing the latest frame row. Writing happens on one low-priority
  background thread; a full queue drops lines instead of freezing the game.

## The report bundle

**Logs -> Export report bundle** writes a zip to `<game>/potatoperf/exports/` and copies its path. The bundle contains
the current session files, the diagnostics file and a short README. It is built on a background thread so the game does
not freeze.

Attach that zip to a bug report, and say which device, launcher and renderer you use.

## The diagnostics file

**Advanced -> Export diagnostics file** (and the bundle) writes `potatoperf-diagnostics.txt` next to the config. It
holds:

- mod, Minecraft, Fabric Loader, Fabric API and Java versions;
- operating system and architecture, CPU thread count, maximum heap and device memory;
- GPU renderer and vendor strings, the detected renderer family and translation layer, and a launcher hint;
- hardware tier, preset, enabled modules and the important tuning values;
- live frame rate, 1% low, frame time, phase times, allocation rate and GC;
- section, entity, particle and draw counters, the verdict and the last stutter;
- the overlap list and the ids of installed mods.

## What it never contains

- your Minecraft username or your operating-system user name;
- your home directory or any file path outside the game folder;
- your server address, exact coordinates or chat;
- IP addresses: IPv4 and IPv6 strings are redacted before a line is written;
- credentials of any kind.

If you see something in a bundle that should not be there, delete that file before attaching the zip and mention it in
the report.
