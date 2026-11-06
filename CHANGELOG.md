# Changelog

User-facing changes only.

## 1.6.0

- **Multiple Minecraft versions.** One jar per supported version; use the table in the README to pick yours.
- **Sodium compatibility.** PotatoPerf no longer crashes on startup next to Sodium and similar terrain renderers. Its
  overlapping terrain work stays idle while the rest keeps working.
- **Smarter automatic scaling.** Quality steps down only while the frame rate is genuinely below your device's
  minimum, and steps back up when the frame rate is comfortable or stable. Both thresholds are in the settings.
- **Counters that report honestly.** Draw calls, layer draws, uniform uploads and visibility work now appear in the
  logs. A counter that cannot be measured says `n/a` instead of a false zero.
- **Particle control.** Real living-particle caps per effect and in total, plus a particle render budget on the lowest
  presets. Explosions, totems and sonic booms are never refused.
- **Faster joins.** The chunk upload and rebuild bursts after joining are spread over more frames, and the entity
  render distance ramps up over four seconds. Nothing in the world or gameplay changes.
- **Bug reporting.** The Logs tab has a **Report a bug** action that opens the Modrinth page.
- **Feature health.** The Debug tab and the session summary show which features are active, idle or unavailable, with
  the reason.

## 1.5.0

- First public release.
