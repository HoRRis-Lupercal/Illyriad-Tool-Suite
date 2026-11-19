# Illyriad Tool Suite

Illyriad Tool Suite is a modular userscript that adds trading, reference, note-taking, customization, and interface tools to Illyriad. Its shared Core provides the suite launcher, sidebar integration, module registration, and persistent settings. The release build combines enabled modules into one userscript.

## Included tools

### Quartermaster

Quartermaster reads caravan capacity, available vans, and town inventory from the Trade Orders page. Select Wood, Clay, Iron, Stone, or Food and set target percentages; the tool tracks the total and fills the consignment quantities using available stock and capacity. Review and submit the trade yourself.

Choose an allocation mode:

- **Bilge Rat** follows the selected percentages and draws from available stock to fill the vans.
- **Crewmate** keeps a chosen amount in reserve and redistributes shortages among the other selected resources.
- **Cabin Boy** bases the allocation on the proportions currently stored in the town.

Quartermaster also provides Next Town and Last Page navigation, and lets you save, load, and delete named presets. Share Code and Load Code transfer a preset as text. Settings and presets are saved in the browser, and the resizable, movable window remembers its geometry.

### Catalogue

Browse the **Gear**, **Item**, and **Unit** catalogues. Search by name or game ID, filter by type, and click an entry to open Illyriad’s native detail popup with a custom buttom present to copy the entries chat code.

### Notes

Keep notes separately for each town or switch to **Global** notes. Notes are saved in the browser cache, and the city view shows the note for the currently selected town. The editor supports clickable URLs and Markdown-style links, basic bold/italic/underline and font-size markup, and optional text, panel, button, and border colour tags.

### Customizer

Choose an interface theme and a city-map theme independently, apply changes, or return to Native. Custom Color Settings provide color inputs and swatches for text, backgrounds, borders, inputs, links, names, chat, diplomacy labels, and city-dropdown elements. Optional controls replace paper or header textures with selected colors. Custom CSS can also be enabled and edited in the Customizer.

Included themes:

- **LuperDark (Warm)**, **LuperDark (Blackout)**, and **LuperDark (Cold)** interface themes.
- **Lupercalian Union Skin** city-map theme.

All theme artwork is packaged inline with the script to minimize image flicker.

### UI Tweaks

UI Tweaks groups optional controls in its own accordion menu. Settings are saved in the browser.

**Warnings and information**

- Highlight sovereignty claims when no structure is present or the structure level is below the claim level; customize the highlight color.
- Show resource time-to-empty or time-to-full statistics in the Next Events panel and resource tooltips, plus daily rates for Gold, Mana, and Research. Set separate colors for draining, filling, one-day warnings, and full warnings.
- Set minimum and maximum stock levels for ten advanced resources—beer, books, spears, swords, bows, saddles, leather armour, chainmail, plate armour, and siege blocks. Below-minimum and above-maximum levels highlight the stock, icon, and production-rate cells.
- Highlight the Production tab when a building on the town map has an empty production queue. Configure the highlight color and exclude selected outputs with the blacklist.
- On the Commanders page, display each commander’s potential level when unspent experience could raise it.

**Maps, menus, and convenience buttons**

- Add building-level labels to the town map, with adjustable text and border colors, a custom level gradient, and a preview.
- Replace the city dropdown with a configurable 2–6 column, 2-10 row menu. Set a background color and description for each city.
- Add a resource-plot demolish button and a **Max** hold-time button on Military Orders, which sets the available d,hr,m controls to their maximum values.
- Replace or hide the Tutorial button with a Quartermaster, Customizer, Catalogue, or UI Tweaks launcher. Set overrides for individual pages, including World Map, City Map, Production, Sovereignty, Inventory, Military Orders, Armies, Commanders, and Trade Orders.

## Installation

Install the compiled `Illyriad-Tool-Suite.user.js` in Tampermonkey or another compatible userscript manager, then use it on Illyriad. 

The suite requires Illyriad and a compatible userscript manager. Mobile performance not tested.

## License

Personal, non-commercial use only. Modification and redistribution require prior written permission. See [LICENSE](LICENSE) for the full terms.
