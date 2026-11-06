# Presets

PotatoPerf ships four presets. Each one sets every value it relies on, so applying the same preset twice always gives
the same result.

| Preset | Made for | What it does |
|---|---|---|
| **Potato** | Weak phones, 2-3 GB RAM, GL4ES/ANGLE or integrated graphics | The most aggressive preset. Short cull distances, a section draw cap, a particle alive cap with a render budget, a chunk upload budget, no menu blur, a static panorama and no clouds. Dynamic scaling is on. |
| **Low** | Older laptops and low-end phones with 3-4 GB RAM | Similar to Potato with more generous distances, a higher section cap and a larger particle cap. Dynamic scaling is on. |
| **Balanced** | The default: most gains with a vanilla-looking result | Distance culling and caps without the aggressive visual cuts. Dynamic scaling is off, so the view does not change while you play. |
| **Quality** | Only safe, non-visual optimisations | Culling and tick throttling are off, distances are unlimited, and no visual feature is changed. Only the measurement and logging features stay active. |

## Choosing a preset

- **First launch.** PotatoPerf reads device RAM, CPU thread count and the GPU renderer string and applies the preset
  for the detected tier: very low gets Potato, low gets Low, mid gets Balanced and high gets Quality.
- **Manual choice.** Picking a preset turns off **Auto preset on hardware change**, so your choice is kept on the next
  launch.
- **Switch at any time.** A preset applies immediately and resets dynamic scaling.

## Automatic quality scaling

Two presets, Potato and Low, turn dynamic scaling on. It never touches gameplay.

- **Step down** only while the frame rate is below the minimum for several seconds. It cannot step down while the
  frame rate is above the minimum.
- **Step up** when the frame rate holds at the comfort level, or after a long stretch of stable frame time.
- **Thresholds** are derived from the hardware tier unless you set them: a minimum of 30 on the lowest tiers, 45 on
  mid-range and 60 on high-end, with comfort at 1.25x the minimum.
- **Settling.** Scaling pauses after a join until frame time is stable, and it ignores menus, loading and resource
  reloads.
- **Every step is logged** with the frame rate, the frame time, the scale and the reason.

## If a preset is not right

- Too slow still? Choose **Potato**, lower the render distance, and turn on **Safe mode** to check whether another mod
  is responsible.
- Too much visual change? Choose **Quality** and enable one feature at a time from **Advanced**.
- Wrong for one device only? Run **Auto-select preset** again.
