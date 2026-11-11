<!-- This README was written and updated with help from Claude (Anthropic), cause i'm to lazy to write it myself :P -->
# mrpat_qbox

Free FiveM resources for [Qbox](https://github.com/Qbox-project) servers, by MisterPattie.

Each resource lives in its own folder and works on its own: install only the ones you want. Every folder has its own README with the full feature list, configuration and installation steps.

## Resources

| Resource | What it is | Version |
| --- | --- | --- |
| [mrpat_offshore_maintenance](mrpat_offshore_maintenance) | A civilian job at sea: repair buoys, seabed equipment, deep-sea pipelines and leaking wrecks, from a boat, in diving gear or by submarine. Diagnose the fault, pick the right repair, and level up into better-paid, deeper work. | 1.0.0 |

More resources will be added here over time.

## Requirements

All resources run on a standard Qbox stack, with no extra frameworks:

- **qbx_core**
- **ox_lib**
- **ox_target**

Some resources need one or two more (for example, mrpat_offshore_maintenance also needs **qbx_vehiclekeys**). The README of each resource lists exactly what it needs.

## Installation

1. **Download** this repository, or clone it with git.
2. **Copy the resource folder** you want (for example `mrpat_offshore_maintenance`) into your server's `resources` directory. Any `[category]` folder works. You don't need the rest of this repository.
3. **Start it after its dependencies.** In your `server.cfg`, below the lines for ox_lib, qbx_core and the other requirements:

   ```cfg
   ensure mrpat_offshore_maintenance
   ```

4. **Configure it** following the resource's own README, then restart the server and check the server console for config warnings.

## What every resource has in common

- **Server authority.** Everything that touches money or progress is decided on the server, so a modified client can't pay or level itself.
- **Three config files.** `config/server.lua` (server-only settings and hooks), `config/shared.lua` (settings both sides need) and `config/client.lua` (what players see and do). Every setting has a comment that says what it does.
- **Startup checks.** Mistakes in the config are reported in the server console when the resource starts, with what it will use instead, not halfway through a player's job.
- **Hooks instead of hard dependencies.** Things like XP storage, logging and fuel are small functions in the config, so you can point them at your own resources.
- **Translatable.** All player-facing text lives in `locales/`. English and Dutch are included, and the language follows your ox_lib setting (`setr ox:locale "nl"`). To add a language, copy `locales/en.json` to `locales/<code>.json` and translate the values.
- **Logging** through ox_lib's logger, so logs go wherever your server sends ox_lib logs.
- **Debug tools** for placing locations and testing, behind `Config.Debug`. Never turn that on on a live server.

## Issues and suggestions

Found a bug or have an idea? Open an [issue](https://github.com/MisterPattie/mrpat_qbox/issues). Mention the resource, what you did, what you expected, and any errors from the server console or F8.

## License

Copyright (C) 2026 MisterPattie

All resources in this repository are licensed under the GNU General Public License v3.0. See [LICENSE](LICENSE) for the full text.
