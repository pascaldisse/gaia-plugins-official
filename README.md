# gaia-plugins-official

gaia-daemon's bundled command plugins, migrated to pi packages
(`gaia plugin migrate`, see gaia-daemon docs/PLUGIN-FORMAT.md). Each subdir
is one gaia plugin (`plugin.json` + `index.mjs`, the gaia-format
contribution source of truth) plus its generated `pi-extension.mjs` wrapper
(auto-generated -- do not hand-edit, rerun `gaia plugin migrate <dir>` after
changing `index.mjs`).

One repo, four extensions, registered as ONE pi package (root `package.json`'s
`pi.extensions` lists all four `pi-extension.mjs` entry points) -- pi's git
source has no subpath addressing (only host/path/ref), so splitting this into
four separately-installable git sources would need four separate GitHub
repos. Documented compromise, not an oversight (gaia-daemon LANE C ghoul
report, 2026-09-05).

| dir | gaia plugin id | pi commands |
|---|---|---|
| fugu | gaia.fugu | fugu |
| rpg | gaia.rpg | rpg |
| rpg-engine | gaia.rpg-engine | rpg-engine |

Install: `gaia plugin install git:github.com/pascaldisse/gaia-plugins-official`
(or `pi install git:github.com/pascaldisse/gaia-plugins-official` directly).
