# Illyriad Tools Suite

Illyriad Tools Suite is a userscript developed by IKnights and HoRRis Lupercal that adds planning, reference, note-taking, and interface customization tools to [Illyriad](https://elgea.illyriad.co.uk/). It runs on the game page and adds a suite sidebar, tool windows, and optional interface changes. The tools read the game page and keep their settings and plans in browser storage; they do not replace the game’s own forms or authoritative values.

## Installation

1. Install a userscript manager such as Tampermonkey or Violentmonkey in a desktop browser.
2. Install the published [`Illyriad-Tool-Suite.user.js`](https://raw.githubusercontent.com/HoRRis-Lupercal/Illyriad-Tool-Suite/main/Illyriad-Tool-Suite.user.js). The loader requires the matching published bundle, `Illyriad-Tool-Suite.bundle.js`.
3. Open or reload `https://elgea.illyriad.co.uk/`. The suite sidebar and its tools are available on the game page.

The script metadata matches both HTTP and HTTPS versions of the Elgea game host. Mobile behavior depends on the browser and userscript manager.

## Included tools

The build manifest enables the features below. Open the suite’s **Tools** sidebar tab to launch the tools that appear as windows. **Notes** is a separate sidebar tab.

### Quartermaster

Allocates a town’s available trade capacity across selected resources and fills the corresponding quantities on the Trade Orders page. It supports Wood, Clay, Iron, Stone, and Food. Choose resources and percentage weights; the total percentage is shown as you edit. The allocator reads caravan capacity and town inventory from the game page, adds the selected resource rows to the consignment, and fills the amounts. It does **not** submit the trade order.

The **Over-Juice Protection** modes control how much stock is left behind:

- **Crewmate** applies the selected percentage weights while reserving the configured amount of each selected resource.
- **Cabin Boy** divides capacity according to the selected resources’ current stock proportions.
- **Bilge Rat** applies the selected percentage weights without the resource reserve.

Set a caravan reserve to leave a chosen number of caravans unused. Use **Distribute** on Trade Orders to fill the current consignment, **Next Town** to move to the next town using Illyriad’s own control, and **Last Page** to return to the previous page. Save, load, and delete named presets; **Share Code** and **Load Code** export and import a preset through a compact code. Presets and settings are stored in the browser.

### Prestige Builder

Builds a local construction plan for one town at a time. It reads the town’s building plots and active construction from **Town Map**, reads the resource bar from the town page, and can read inbound shipments from **Trade Movements**. Use **Refresh from game** after visiting those pages to scan their current data.

In **Setup**, choose a target building, target level, and optional priority for each plot. Resource plots and level-20 buildings can be hidden from this list. Targets are saved separately for each town. **Planning** reports remaining upgrade costs, estimated delivery shortfalls, population change based on food upkeep, and a prestige estimate. It also provides a proposed upgrade order and earliest estimated funding times, and shows incoming cargo, data-quality warnings, and storage-overflow notices. Choose a planning strategy: balance resources, prefer marked buildings, or use food upkeep as a population proxy. Confirm the town’s storage capacity in the game before relying on the estimate. **Prestige Building** shows the next affordable planned upgrade and upcoming order; **Next Building** navigates to that building’s game page without starting it.

This is a planner, not an automatic builder. It does not start, queue, demolish, or prestige buildings. The game’s displayed costs and queues remain authoritative. Replacing a plot’s building requires manual demolition and construction, then a fresh scan; demolition is not included in the plan. Inbound shipment data must be refreshed on Trade Movements, and plans show warnings when a scan is missing, incomplete, or stale. Build and resource-cost data are bundled with the suite.

### Catalogue

An icon-grid reference with **Gear Catalogue**, **Item Catalogue**, and **Unit Catalogue** tabs. Search by name or ID and filter by type. Selecting an entry copies its Illyriad reference ID to the clipboard. The catalogue reports the number of matching entries and provides feedback if clipboard access is unavailable. It is a lookup aid; it does not acquire, equip, or deploy anything.

### Notes

Adds a **Notes** tab to the suite sidebar. Keep a set of notes for the current town or switch to **Global** notes, edit the text, then choose **Done** to save. Town notes follow the active town as you navigate; each town has its own saved note. Notes are kept in browser storage. The renderer supports clickable links and note formatting/theme directives understood by the module.

### Customizer

Provides a window for changing the appearance of the game interface. Choose and apply bundled interface themes and city-map skins, or reset to the native appearance. Color controls cover text, backgrounds, borders, inputs, headers, links, chat highlights, alliance labels, and city-dropdown states. You can choose grey, blue, or red game buttons if in the blackout mode; replace paper, dark-header, or light-header textures with selected colors; and enable optional custom CSS. Apply or clear color overrides from the controls. Theme and customizer settings persist in browser storage.

The enabled themes include **LuperDark Warm**, **LuperDark Blackout**, and **LuperDark Cold** interface themes, plus the **Lupercalian Union** city skin. They use bundled artwork for interface and city-map elements.

### UI Tweaks

Optional page enhancements are managed in the **UI Tweaks** window. Settings are grouped into collapsible sections and can be enabled independently:

- **Warnings and highlights:** sovereignty claim mismatch highlighting; configurable harvester travel-time bands; resource time-until-empty/full figures in the town resource bar and/or tooltips with text colors; warnings for empty production queues with a building blacklist and highlight color; and configurable minimum/maximum stock thresholds and highlights for advanced resources.
- **Additional information:** resource tooltip statistics, travel-time displays for diplomatic and trade orders, NPC group-size estimates on map tooltips, and commander potential-level display.
- **Town map:** building plot level labels with configurable text, border, and gradient colors.
- **Convenience buttons:** a Demolish button on resource plots and a Max Occupy Time button on Military Orders.
- **Tutorial button replacements:** replace or hide the Tutorial button with a suite tool, globally or with page-specific overrides for world map, town map, production, sovereignty, inventory, military orders, armies, commanders, and trade orders.
- **Custom City Dropdown:** replace the city selector with a configurable grid (2–6 columns and 2–10 rows), with per-city background color and description settings.

An in-window **Native Reset** clears UI Tweaks settings and cached data and restores the default behavior without reloading the game. It preserves custom city descriptions. Most features are off until enabled.

## Suite sidebar and shared behavior

The shared core adds the suite’s sidebar tabs, tool launcher, dialogs, and common storage helpers. Its **Tools** panel lists registered tools, opens them, and provides access to their settings windows. The core adapts the sidebar to Illyriad’s current layout, preserves open/selected state where possible, and coordinates suite buttons with the game’s native controls. Individual tool windows can be moved and resized; tools that implement geometry persistence remember their window position and size.

Settings, notes, presets, and plans are stored locally by the browser on the Illyriad site. They are not automatically synchronized between browsers or devices. Clearing site data or browser storage can remove them. The suite uses no userscript-manager grants (`@grant none`); it interacts with the game page, browser storage, and clipboard where the browser permits it. Some game icons and sprite sheets are loaded from Illyriad’s asset host.

## License

The repository’s [`LICENSE`](LICENSE) grants personal, non-commercial use and reserves other rights, including modification and redistribution. Individual source modules may also carry their own licensing notices; review the applicable notices before reuse.
