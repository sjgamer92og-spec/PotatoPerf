# Compatibility

## Sodium and other terrain renderers

PotatoPerf is a **companion to Sodium**, not a replacement.

- With **Sodium** installed, PotatoPerf's overlapping terrain work stays idle and its entity, particle, GUI, tick,
  memory and diagnostic features stay active. You get Sodium's terrain rendering plus PotatoPerf's culling, caps, logs
  and presets.
- The same applies to other terrain renderers and shader stacks that announce themselves as taking over the terrain
  pipeline, including Iris, Embeddium, Rubidium, OptiFine, Oculus, Indium and Celeritas.
- **Never install two terrain renderers at once.** PotatoPerf steps aside, but two renderers can still conflict with
  each other.
- **Shaders** work as they do with the renderer you already use. PotatoPerf does not compile shaders and does not
  replace the renderer.

The Debug tab shows the overlap line, for example `Overlap: sodium`, so you can see what was detected.

## Other optimisation mods

PotatoPerf detects common optimisation mods and leaves overlapping work idle instead of fighting them:

- entity culling mods (for example EntityCulling);
- particle culling mods;
- memory and general optimisation mods (for example FerriteCore, Lithium, ModernFix, BadOptimizations, C2ME, VMP and
  MemoryLeakFix);
- UI mods (for example ImmediatelyFast, FastLoad and SmoothBoot).

If two mods do the same thing, keep the one you prefer. **Advanced -> Copy detected conflicts** copies the list for a
bug report.

## Reduced-feature builds

Builds fall into two groups:

- **Full-feature builds** keep the complete feature set, including all terrain and renderer extras.
- **Reduced-feature builds** keep the core - presets, entity, block-entity and particle culling, caps, tick throttling,
  logging, diagnostics and the settings screen - and leave out extras that the game version does not expose, such as
  section culling, fog at the section cap, GUI profiling, the static panorama and chunk fade.

Which group a build belongs to is fixed by the Minecraft version it targets. The supported versions table in the
[README](../README.md) lists every version, and **Settings -> Debug** names each unavailable feature and the reason on
the build you are running. A feature is never reported as active when it is not.

## Servers and multiplayer

PotatoPerf is client side only. It does not change what the server sees, does not send packets of its own and gives no
gameplay advantage. Servers do not need to install anything, and servers may recommend it.

## Modpacks

Modpacks may include PotatoPerf free of charge by linking to or downloading it from its official page. The jar must not
be repackaged into a separate download and must not be modified. Paid or commercial modpacks need written permission.
The full terms are in the [LICENSE](../LICENSE).
