<div align="center">

<h1>tetrisMAX</h1>

<p>
developed and maintained by
<a href="https://www.initmax.com"><img alt="initMAX" src="./.readme/logo/initmax-logo-framed.svg" height="22" valign="middle"></a>
and community
</p>

<p><strong>Tetris on a Zabbix dashboard.</strong><br>
The game everyone knows, as a widget: add it to a page, press an arrow key, and play. It runs entirely in your browser - the widget asks Zabbix for a board and never speaks to it again.</p>

<p>
<img src="./.readme/badge/zabbix.svg" alt="Zabbix 6.0-7.4">
<img src="./.readme/badge/version.svg" alt="version 2.0.1">
<img src="./.readme/badge/php.svg" alt="PHP 7.4+">
<img src="./.readme/badge/free.svg" alt="FREE AGPLv3">
<img src="./.readme/badge/gpg.svg" alt="GPG signed">
</p>

<p>
<a href="#what-you-can-build"><strong>Features</strong></a> &nbsp;·&nbsp;
<a href="#examples"><strong>Examples</strong></a> &nbsp;·&nbsp;
<a href="#install"><strong>Install</strong></a> &nbsp;·&nbsp;
<a href="#free-vs-pro"><strong>FREE vs PRO</strong></a> &nbsp;·&nbsp;
<a href="https://portal.initmax.com"><strong>Portal</strong></a> &nbsp;·&nbsp;
<a href="https://www.initmax.com/wiki/tetrismax-game/"><strong>Docs</strong></a>
</p>

<br>

<img src="./.readme/screen/01-overview.png" width="880" alt="Play a complete Tetris game directly inside a Zabbix dashboard without sending or storing monitoring data.">

</div>

---

## Why tetrisMAX

Because a monitoring dashboard is where people wait. tetrisMAX is initMAX's gift to the Zabbix community - a genuinely complete game, given away, on the tool you already run. It is also the least demanding widget we ship: it reads no item, writes nothing, and makes exactly one request in its life.

## What you can build

<table>
<tr>
<td width="50%" valign="top">

**The whole game**
Seven pieces, four rotations each, a next-piece queue, line clears, rising levels and a running clock.

</td>
<td width="50%" valign="top">

**Nothing leaves the browser**
No Zabbix API call, no item, no stored score, no profile row. The tile is drawn once and the game runs client-side.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**Three speeds**
Slow, Normal or Fast to open with. The game speeds up on its own with every level.

</td>
<td width="50%" valign="top">

**A severity bar you will recognise**
The stack height is drawn against Zabbix's own severity colours, from Not classified up to Disaster.

</td>
</tr>
<tr>
<td width="50%" valign="top">

**Every supported Zabbix**
One package covers 6.0 through 7.4 - the same board, the same form, the same look.

</td>
<td width="50%" valign="top">

**In your language**
The configuration form follows each user's own Zabbix display language.

</td>
</tr>
</table>

## Examples

<table>
<tr>
<td width="50%" align="center" valign="top"><img src="./.readme/screen/02-board.png" alt="Board"><br><small><b>Board</b> - The game board shows the next pieces, elapsed time, level and cleared lines in one polished widget.</small></td>
</tr>
</table>

## Configuration

One field: **Speed** - the pace the game opens at. Everything else about a game of Tetris is decided by playing it.

## How to play

Add the widget to a dashboard and the game starts by itself. The dashboard page has to have focus - click it once - and then:

| Key | Does |
| --- | --- |
| **←** / **→** | move the piece sideways |
| **↑** | rotate |
| **↓** | drop one row |
| **Space** | hard drop |

Every minute the level goes up and the pieces fall faster. When the stack reaches the top the game shows your score and a **Play again** button. The score is shown and then forgotten - there is no board to post it to.

## Install

**FREE** ships as **GPG-signed `deb` / `rpm` packages** from the initMAX repository - `apt` / `dnf` installs them and keeps them updated.

### Easiest way - the guided installer on the Portal

Open the product page, pick your **OS** and **edition**, and copy the ready-made command. FREE is fully public (no login); PRO fills in your token once you sign in. There's a feedback box right there too.

<div align="center">
<a href="https://portal.initmax.com/catalog/zabbix-tetrismax#how-to-install"><img src="./.readme/screen/portal-installer.png" width="100%" alt="Guided installer on the initMAX Portal - click to open"></a>
</div>

<p align="center"><a href="https://portal.initmax.com/catalog/zabbix-tetrismax#how-to-install"><strong>→ Open the installer on the Portal</strong></a></p>

Prefer a plain archive? Every release also ships as a **ZIP** [straight from the repo](https://repo.initmax.com/zabbix/free/zip/tetrismax/) - handy for offline or manual installs.

The module is enabled automatically during the package installation - verify it in **Administration → General → Modules**. Done.

## Upgrading

**From 2.0.x, if you used the score board:** it is gone, and so is the endpoint it posted to. Nothing needs uninstalling - the widget simply stops sending. The Zabbix items you pointed it at are untouched and keep whatever they already recorded; delete them yourself if you no longer want them. Any API token you created for it is no longer used by anything and should be revoked. Dashboards keep working: the widget ignores the settings it no longer has.

## FREE vs PRO

tetrisMAX is a gift, so there is no paid edition of it - and with the score board gone there is nothing left that a paid edition could contain. Everything below is in the one package.

| Feature | FREE |
| ---------------------------------------------------------- | :----: |
| The full game - board, pieces, levels and on-screen score | ✅ |
| Runs entirely in the browser - no Zabbix API call, nothing stored | ✅ |
| Choice of falling speed | ✅ |
| One package for Zabbix 6.0 - 7.4 | ✅ |
| Localised into all 25 Zabbix display languages | ✅ |
| High availability ready | ✅ |
| Licence | AGPLv3 |

## Requirements

|              |                                                              |
| ------------ | ------------------------------------------------------------ |
| **Zabbix**   | 6.0 · 6.2 · 6.4 · 7.0 · 7.2 · 7.4 - one package covers all    |
| **PHP**      | 7.4 or newer                                                 |
| **OS**       | Debian/Ubuntu · RHEL/Rocky/Alma/Oracle/Amazon · SUSE         |
| **Editions** | FREE (public repo) - there is no paid edition                  |
| **Permissions** | None beyond seeing the dashboard. The widget reads no item, so it needs no host or item permission |
| **Languages** | All 25 Zabbix display languages - the widget follows each user's own language setting |
| **High availability** | Ready. No server-side component and no stored state of any kind; install it on every frontend node of an HA cluster and any node can serve it |

Everything above works on every supported version, including 6.0 and 6.2, whose module API predates the one the widget is written against - the package carries a second module tree for those two lines and the installer picks the right one. The board, the score panel, the severity bar and the configuration form are identical on all six versions; a game configured on any of them keeps its setting when Zabbix is upgraded, in either direction.

There is **no capability tetrisMAX offers on a newer Zabbix and not on an older one.** The game is drawn in the browser, so the frontend's age has nothing to bring to it.

## Support &amp; links

- **[Documentation / Wiki](https://www.initmax.com/wiki/tetrismax-game/)**
- **[Product page](https://www.initmax.com/product/tetrismax-game/)**
- **[Portal](https://portal.initmax.com)** - downloads, tokens, support tickets
- **Source code (FREE, AGPLv3)** - included in every package and published as a [source archive](https://repo.initmax.com/zabbix/free/zip/tetrismax/) on repo.initmax.com
- **[support@initmax.com](mailto:support@initmax.com)**

---

<div align="center">
<sub>FREE: <a href="https://www.gnu.org/licenses/agpl-3.0.html">AGPLv3</a> &nbsp;·&nbsp; © 2021–2026 initMAX s.r.o.</sub>
</div>
