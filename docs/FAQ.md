# FAQ

**Is PotatoPerf a Sodium replacement?**
No. It is a companion. With Sodium installed, PotatoPerf's overlapping terrain work stays idle and its entity,
particle, GUI, tick, memory and diagnostic features stay active. See [Compatibility](COMPATIBILITY.md).

**Does it change gameplay or the world?**
No. Everything is client side and visual or measurement only. It does not change blocks, entities, inventory, packets
or anything the server sees.

**Will it give me a fixed frame rate?**
No, and it does not promise one. It reduces work the client does not need and keeps frame time steadier. The result
depends on the device, the launcher, the renderer, the render distance and the world.

**Does it work in multiplayer?**
Yes. It is client side only and gives no gameplay advantage. Servers do not need to install anything.

**Do I need Fabric API?**
Yes. Fabric Loader and Fabric API are both required.

**Do I need Mod Menu?**
No. Mod Menu only adds an entry in the mod list; the same screen opens with `Right Shift + O`.

**Which file do I download?**
The jar for your exact Minecraft version. The supported versions table in the [README](../README.md) lists every
version. A mismatched jar is refused by Fabric.

**Why does a feature say "unavailable"?**
Because that build cannot provide it, or because another renderer already handles it. **Settings -> Debug** shows the
reason and never pretends the feature is active. See [Troubleshooting](TROUBLESHOOTING.md).

**Why do some counters say `n/a`?**
The value cannot be measured on your renderer, usually because another mod owns that part of the pipeline. A false zero
would be misleading, so it says `n/a` instead.

**Why do I not see any change?**
You may already be limited by something else, such as render distance, the launcher, the device's thermal limit or the
world itself. Try the **Potato** preset, check the Debug tab, and compare with the same scene and render distance.

**Does it work with shaders?**
It works alongside the renderer you use for shaders. PotatoPerf does not compile shaders or replace the renderer.

**Can I include it in a modpack?**
Yes, free of charge, by linking to or downloading it from its official page, without repackaging or modifying the jar.
Paid or commercial modpacks need written permission. See the [LICENSE](../LICENSE).

**Can I reupload the jar somewhere else?**
No. Reuploading, modifying, decompiling, selling, or putting the jar behind ad links or paywalls is not permitted.

**Is the source code available?**
No. The source code is not public. Bug reports and ideas are welcome on the Modrinth page (coming soon).

**Where do I report a bug?**
Use the [report template](REPORT_A_BUG.md) and attach the report bundle from **Settings -> Logs -> Export report
bundle**. The report page is coming soon.

**Does it send anything to a server?**
No. Nothing is uploaded automatically. The report bundle is written to your own game folder and only leaves your device
if you attach it to a report yourself.

**Does it work on a very old device?**
The **Potato** preset is made for weak phones with 2-3 GB of RAM and a translation layer. If your device cannot run
Minecraft at all, no mod will change that.
