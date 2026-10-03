# Changelog

## 1.11.3 — 2026-10-03

### Fixed
- An element made shorter than its content in the Studio (*scrolls inside*) no longer shows a grey scrollbar: it still scrolls with the mouse wheel or a finger, without the bar.

## 1.11.2 — 2026-10-03

### Fixed
- When Home Assistant's own top bar and sidebar are visible, the Studio's bars no longer cover the bottom of the dashboard: the page measures the real space between Home Assistant's header and the Studio's bars and fits into it, on computer, tablet and phone.
- Full-height pages fit under Home Assistant's visible top bar instead of running 56 px below the screen (takes effect the next time the dashboard is saved).

## 1.11.1 — 2026-10-03

### Fixed
- Card settings no longer slide sideways and cut off their left side: the tabs (*Content*, *Layout*, *Style*, *Actions*, *Visibility*, *Code*) wrap to a second row when the panel is narrow.
- In the phone and tablet versions the Studio leaves room under the page, so the last row of the dashboard is no longer hidden behind the Studio's bars.
- On phones the toolbar of a selected element on a hand-made page shows all its buttons instead of scrolling sideways.

## 1.11.0 — 2026-10-03

### Added
- **Separate computer, tablet and phone versions.** A bar above the Studio's bottom bar picks the version you edit — computer (over 1024 px), tablet (601–1024 px, upright or turned) or phone (up to 600 px). Order, position, width, spacing, colours, texts, hidden items, bars, the top bar, popups and the elements inside modules change only in that version; the canvas takes the device's size, so what you see is what the device shows. Pages, the dashboard name and the theme stay shared, and every panel says whether it edits *this version* or *all versions*.
- **All** applies a change to every version where the element is the same — even if its old value was different there, or the module sits elsewhere in the zone. A toast tells you where it went and where it was skipped.
- **⧉ Copy** copies a page, the top bar or the whole version from the one you're on to the others. Ctrl+Z undoes it.
- The Studio tour and the guide explain the versions.

### Changed
- Hiding or restyling something in one version no longer duplicates the page: the dashboard keeps one page with the differences per screen size, so it stays small and fast.
- *Hide* and *Delete* name the version they act on.
- Empty zones no longer draw an empty frame on the dashboard.
- Top-bar buttons that don't show on screens up to 900 px are marked so in the menu settings.

### Fixed
- The Studio opens on phones and upright tablets too.
- The page keeps its scroll position after a change, Undo or Redo.
- On 1024–1440 px screens the bottom bar no longer runs off the screen and *Save* stays visible.
- The bottom zone and messages are no longer covered by the Studio's bars.
- Redo returns to the version the change was made in.
- Long-press dragging with a finger no longer breaks off.
- On phones the page scrolls normally, also over the Studio's frames, and the phone's own spacing is used.
- In the popup editor the toolbar of the selected element no longer covers *Settings* and *Try*, and the header fits narrow popups.

## 1.10.1 — 2026-10-03

### Changed
- The dashboard file is about 20% smaller, so it loads faster, especially on tablets and phones.

## 1.10.0 — 2026-10-03

### Added
- **Mega Dashboard is a Home Assistant app.** In Home Assistant open *Settings → Apps → App store → ⋮ → Repositories*, add `https://apps.mega-dashboard.eu/` and install *Mega Dashboard*. The app installs the dashboard together with button-card, layout-card, card-mod, kiosk-mode, mini-graph-card and advanced-camera-card (an add-on that HACS already installed is left alone), creates a *Mega Dashboard* dashboard and keeps everything registered. HACS is no longer needed.
- On the dashboard the app creates, the setup wizard opens by itself.

## 1.9.1 — 2026-10-03

### Fixed
- The wizard no longer gets stuck on *Which devices do you use most?* when the Home Assistant logbook answers slowly. It now reads at most three days at a time, skips a day that doesn't answer within 20 seconds, shows suggestions right away and moves on with what it has after 40 seconds.

## 1.9.0 — 2026-10-03

### Added
- **Parts of a button are editable on their own.** Inside a selected card, tap the name, icon, state, label or a custom field to select just that part: drag it, nudge it with the arrow keys, resize it from the corner, or set its size, weight, colour, alignment, background, radius, padding and opacity in the panel. *Hide* fades it in the Studio and removes it on the dashboard; *Delete* takes it off the card. Alt+click goes straight to the innermost element.
- **Every bar can be managed** — the top bar, columns, bottom bar, slide-out panel and the zones of hand-made pages. Select one by its label or an empty spot in it to get a toolbar and a panel: **inner spacing (padding)** on all four sides, **outer spacing (margin)** separately, width or height (also with a handle on its edge), background and radius. *Hide* keeps the content and comes back with *Show*; *Delete* removes the bar and *Add bar* (or Ctrl+Z) brings it back. In both cases the other zones take the freed space.
- *Layout* lists all bars of the page with a switch, settings and delete.
- **The old “Top spacing” is now the top bar's padding** — four separate values that push the menu's content inward while the bar stays in place and grows taller. Existing settings are kept as the bar's outer margin.
- A notice when the browser still runs an older copy of Mega Dashboard, with a *Reload* button.
- *Help* links to [mega-dashboard.eu](https://mega-dashboard.eu/) and to [Buy me a coffee](https://buymeacoffee.com/harryasarz).

### Changed
- The centre takes the width of hidden or deleted columns; with many modules, narrow ones drop to their own row before they get too small, and nothing runs under the neighbouring bars at any screen size.
- On hand-made pages a picture card (such as the 3D map) that grows into a freed column keeps its proportions and stays centred instead of covering the top and bottom bars.
- The bottom bar keeps a sensible maximum height on full-screen pages and scrolls inside.

### Fixed
- Resizing a bar or module no longer stops halfway when the mouse passes over another element.
- A module's own root is labelled with the module's name instead of “Zone m0”.

## 1.8.0 — 2026-10-02

### Added
- **Every element is editable on its own.** Tap a module and tap again to go inside: buttons, texts, icons, nested cards, `custom_fields` and pop-up contents can each be selected, moved, resized, styled, hidden or locked. Your changes are kept as personal edits on top of what the module generates, keyed by a stable ID — they survive a new device in the module, a title or theme change, and a *Reset* per property, per element or for the whole module brings back the original. A duplicated module is fully independent.
- **Element panel with tabs** — *Content*, *Layout*, *Style*, *Actions*, *Visibility*, *Code*: size (auto/fixed/min/max, aspect ratio), spacing, offset and layer; containers as column, row, grid or free positioning over an image, with gap, alignment and wrapping; background, text and icon colours, opacity, border, radius, shadow, font; hover, press and keyboard focus without moving neighbours, colours by state, reduced motion respected. Explicit colours are kept when the accent changes. Any size or style can apply to *all screens* or only phone, tablet or desktop.
- **Breadcrumbs, Layers tree and multi-select**: page › zone › module › element; Shift-click to select several, then align, distribute, group (Ctrl+G), ungroup, duplicate (Ctrl+D), copy and paste the look (Ctrl+Alt+C / V), delete. Free elements move with drag (snap and guides, can be turned off) or the arrow keys.
- **New elements**: heading, text, description, divider, value from a device (attribute, decimals, unit, text when there is no data), button, icon, image, device, groups, grid, free area, clock, tabs and a button with a pop-up.
- **The top bar clock** is now two elements — time and date — each with position, size, font, colour, alignment, 12/24 h, seconds and date format. It ticks by itself and never reloads the dashboard.
- **Menu editor** in *Top bar*: order of the parts, tabs in any order, links and groups (sub-menus), labels, size, alignment, capital letters, the colour of the current tab, top or left (vertical) position and what happens when they don't fit — scroll, wrap to more rows, or the first ones plus *More*.
- **Pop-ups** open in an editing stage with the same tools, plus title, size, width, max height, radius, background, padding, closing on outside click and auto-close. *Try* opens the real browser_mod pop-up; without browser_mod the Studio says so.
- **Device preview** (phone 360, tablet portrait and landscape, desktop) with the live draft, and a **Test** mode where taps really work.
- **Page address** can be changed in *Pages*; the menu, groups and buttons that open the page follow.
- **Arrange automatically** in *Layout*: small modules two or three per row, large ones full width, order kept — with a preview and Ctrl+Z.

### Changed
- Overview pages with many modules in the centre now scroll inside the centre instead of running under the bottom bar; bars with more than four modules wrap.
- On a phone the clock keeps its width next to the weather, and the weather shrinks instead of overlapping.

### Fixed
- The Studio finds the current page when Home Assistant opens it by number (`/dashboard/0`).

## 1.7.0 — 2026-10-02

### Added
- **The Studio edits hand-made dashboards in place.** It now opens instead of the old editor on every dashboard. On your own pages you can select any card right on the dashboard: a second tap goes one level deeper, and a double-click opens its settings. The toolbar has settings, the parent card, up/down (left/right in a row), duplicate, delete, open the page a button leads to, and drag and drop between zones. The **+** and the *Library* add ready modules into your own columns and bars. Your cards stay as they are; only what you change is saved. *Advanced* still opens the full editor on the selected card.
- **Card settings** in the Studio use the same forms as the full editor, including the top menu parts and **pop-ups**: open a pop-up from *Inside*, edit what is in it, or put a ready module into it with *Put a module in the popup*.
- **Top spacing** in the *Top bar* panel: the gap between the top of the screen and the dashboard, for Studio pages and hand-made ones.
- **Card colour** in *Style*: *Glass*, *Solid* or *See-through*, any colour and an opacity slider — so cards stay readable on a photo background.
- **AI assistant instructions** in the wizard are now a step-by-step guide in English (models follow it best) built from what you chose: your rooms and their devices, the whole-house devices of the pages you picked, and your favourites as the default. The assistant still answers in your language. Locks, the gate, the alarm and any script or scene that opens or unlocks are listed apart and always need a clear "yes" first.

### Changed
- Locks, doors and windows, the gate, status, lights, cameras, room lights, climate rows and people get a glass panel when they sit in a wide zone, so they don't float on the background.
- The Studio clock shows the date in the dashboard language (e.g. *Петък, 2 окт 2026*).
- The bottom of a hand-made page is no longer hidden behind the Studio bar while editing.

## 1.6.1 — 2026-10-02

### Fixed
- **The Studio no longer replaces a dashboard it did not make.** Opening a hand-made dashboard in the Studio and saving used to turn every page with a known address (Overview, Cameras, Climate…) into ready modules and overwrite the shared styles and the top menu, so custom 3D maps and cards were lost. Now every page of such a dashboard stays exactly as it is, your styles and top menu are kept, and the Studio only adds the styles it is missing. A page changes only when you press *Turn into modules* on it, which now asks first.

## 1.6.0 — 2026-10-02

### Added
- **Module width** in the Studio: drag the handle on the right of a selected module to make it narrower or wider (¾, ⅔, ½, ⅓, ¼ or any twelfth). Narrow modules sit side by side; on a phone they always take a full row. Double-click the handle, or *Full width* in the module settings, to go back. The **+** between two modules on the same row works too.
- **Hints** at the bottom of the Studio that say what you can do right now (nothing selected, a module selected, Library, Layout, Look, unsaved changes). Close them with ×, turn them back on in *Help*.
- **Language** is asked on first open (English or Bulgarian, the Home Assistant language is preselected), in the first wizard screen, and can be changed any time in the Studio's *Help*.
- **Full screen** in the Studio's *Top bar* panel: hide the Home Assistant header and the sidebar separately. Turning one on also adds the *HA menu* button so administrators can always get back.
- The **accent colour** now has a live example with numbered markers (selected tab, heading bar, switches that are on, selected modes) in the wizard and in *Look*, and it also tints glass card borders and switches.

### Changed
- **Cameras page**: the big viewer and the camera list fit the screen; the list scrolls inside its column and shows as many cameras as you choose; *Recent snapshots* is one row that scrolls sideways.
- *Full screen* now hides the Home Assistant sidebar too. Dashboards made by earlier versions with full screen get it on the next save.
- On a phone the page tabs in the top bar share the width evenly and long names wrap, so they never run out of the bar.

### Fixed
- *Configuration error* on the cameras page with newer Advanced Camera Card versions (`live.auto_unmute`). Open the dashboard in the Studio and save once to fix an existing one.

## 1.5.0 — 2026-10-02

### Added
- **Studio**: edit the dashboard right on the dashboard. Pages are made of zones (columns, a bottom bar, a slide-out side panel) and zones hold **modules** — 36 ready blocks (rooms, lights, scenes, cameras, climate, radiators, media, energy, locks, doors and windows, people, weather, to-do, vacuum, system and more) that fill themselves with your devices.
  - Select a module to get a toolbar: settings, up/down, duplicate, hide, delete, and *Advanced* for the full editor.
  - **+** between modules, a **Library** with a live preview of every module, and drag and drop with mouse and touch.
  - **Layout** presets (Like Overview, Cameras, One column, Two columns), zones on and off, and **Pages**, **Top menu** and **Look** panels.
  - Simple settings for each module (title, devices, rooms, options) and *Default settings*. A module changed by hand in Advanced mode is kept as it is.
  - Nothing is saved until *Save*; undo and redo for every step. On a phone the panels open as bottom sheets.
- **Wizard** with ten screens: where the dashboard will be viewed, the devices you use most (from the last 14 days of the logbook, only actions by a person), rooms in your order, pages and modules, a picture of your home with a guide and a ready AI image prompt, the look, an AI assistant, a home check and add-ons. *See it on the dashboard* shows the result before saving, and a three-step tour follows.
- **AI assistant** (optional): ChatGPT, Claude, Gemini or Ollama with your own key. The wizard writes instructions for your home (rooms, devices, most used), connects the provider in Home Assistant, creates the assistant and, if you want, makes it the main Assist pipeline.
- **Home check**: batteries below 20%, devices that don't respond, lights without a room (put them in rooms in one go) and tips.
- **HA menu** button in the dashboard's top bar (administrators only): with kiosk-mode it brings back the Home Assistant header for the current page, otherwise it toggles the sidebar.
- New guide where every step has *Show me*.

### Changed
- The *Settings* button follows the sidebar in all four states (docked, collapsed, hidden, phone drawer) and hides when the dashboard's top bar has its own ⚙️, which opens the Studio.
- The previous editor is now **Advanced mode**, with a *Studio* button to go back.

## 1.4.0 — 2026-10-01

### Added
- **Starter dashboard**: a wizard that builds a complete dashboard in the Mega Dashboard style from your areas and devices — a top bar with clock, page tabs, energy, system, voice and weather; *Overview* with rooms and their lights (or a 3D map of your home), status, people and a bottom bar; and *Cameras*, *Climate*, *Media*, *Energy* and *System* pages. It asks which pages and rooms you want, an optional picture of your home, and full screen. Works on desktop and phone.
- The starter installs missing add-ons (button-card, layout-card, card-mod and kiosk-mode) through HACS after you confirm, then saves and reloads.
- It opens by itself on an empty dashboard, and is in *Help* and the first guide step.

### Changed
- A new or automatically generated dashboard now opens in the editor (with the starter) instead of showing an error.

## 1.3.2 — 2026-10-01

### Fixed
- The *Settings* button was hard to see once the guide had been seen, and sat on top of the Home Assistant sidebar (profile and notifications). It is now clearly visible and moves next to the docked sidebar.

## 1.3.1 — 2026-10-01

### Changed
- *Help* shows the author and website ([homenetcloud.eu](https://homenetcloud.eu)) next to the version.
- New README with *Open in HACS* buttons, getting started, settings and troubleshooting, a full Bulgarian README, and issue templates.

## 1.3.0 — 2026-10-01

### Added
- **Step-by-step guide** for new users. It opens the first time you open the editor and is always available from *Help* and `Ctrl+K`. Nine short steps: how the editor works, which add-ons are installed, pages, a menu between pages, cards, *Pick on the page*, the 3D map, phone/tablet layout and saving. Each step has a button that does it for you.
- Card gallery: **3D map / floor plan** — upload a picture of your home and get an empty map with an *Edit* button, ready for the map editor.
- Until the guide has been seen, the *Settings* button on the dashboard is shown with its label, so it is easy to find.

### Fixed
- *Top bar* in the tree can be collapsed again.
- *Pick on the page*: the hint, the highlight and the name label lost their colours (they were transparent over the dashboard). They are readable again, the highlight is stronger, and the hint moves to the bottom when you point at something near the top.
- *Show on the page* lost its colours the same way.
- Live preview on *Phone*, *Tablet* and *Laptop* also applies the chosen width to styles that cards create while they run (for example from JavaScript templates), so e.g. the weather row in the top bar is laid out like on a real phone.

## 1.2.2 — 2026-10-01

### Fixed
- Live preview on *Phone*, *Tablet* and *Laptop* now shows cards as they really look on that screen. `@media` rules (in `extra_styles` / `card_mod`) and layout-card `mediaquery` used to follow the browser window instead of the chosen preview width.
- *Top menu* preview uses the real top bar from the open page, including its own `card_mod`, so the phone layout (clock and buttons, tabs, weather on separate rows) shows up correctly.
- *Tablet* and *Laptop* preview are scaled down when the preview area is narrower than the chosen width, instead of squeezing the card.

## 1.2.1 — 2026-10-01

### Fixed
- If an old manual copy (1.1.0 or earlier) is still added as a resource next to the HACS one, only one copy runs now — no more two settings buttons. The console tells you which resource to remove.

## 1.2.0 — 2026-10-01

### Added
- **Editor look** (*General settings → Editor look*) — glass, solid, black (OLED), light or *Like HA* theme; ten accent colours or any custom colour; background opacity; four text/button sizes. Stored in your HA user and applied instantly to both editors and all dialogs. Text on the accent colour switches between white and dark automatically so it stays readable.
- Map editor: **redo** (`Ctrl+Y` / `Ctrl+Shift+Z` and a toolbar button), `Backspace` removes the selected point, `Ctrl+S` saves.
- Conditional cards show what they depend on in the tree (e.g. *Only on Phone*, *Only for 2 users*).

### Fixed
- Undo/redo restored the selection and page incorrectly after some changes; a failed change is now rolled back with a message instead of leaving a half-applied state.
- Saving twice quickly no longer writes twice; edits made while a save is in progress are kept as unsaved instead of being marked saved.
- History is written only after the dashboard itself has been saved, and a failed history write no longer blocks saving.
- Move / duplicate / remove now work on cards wrapped in a `conditional` card.
- Restoring a hidden card whose place no longer exists puts it at the end of the page instead of failing.
- *New card* on panel and strategy pages, and on sections without a card list.
- Visibility: switching screens no longer drops users that are currently inactive.
- Pick on the page now works with touch; clicks that were lost while a text field was being committed are delivered.
- Keyboard shortcuts work with a Cyrillic layout and no longer fire while typing in a field.
- Map editor: moving a point no longer drags the light/AC effects of another point with the same device; X/Y fields ignore invalid numbers; sliders create one undo step per drag; the map image error state, saving state and late-loading history are handled.
- Map editor: saving checks that the map was not moved to another place in the meantime, and adds `entity: sun.sun` when day/night images need it.
- Map editor: the point filter keeps the keyboard open on phones.
- Tablets: the toolbar title no longer overlaps the buttons.
- Phones: text fields use 16px so iOS no longer zooms the page when you tap one.
- Larger text sizes: the layout adapts to the space actually available, dialogs fit the screen and dragging stays under the finger.
- The preferences loaded from HA no longer overwrite a change made in the first seconds after opening the page; the language follows a change of the HA profile language.
- The file is ignored if it is loaded twice (e.g. a manual resource and a HACS one).

### Changed
- The source is split into ES modules (`src/core`, `src/dash`, `src/map`, `src/icons`) and bundled with esbuild; ESLint, unit tests and a translation check run in CI.
- English texts moved to `src/i18n/en.json`.

## 1.1.0 — 2026-10-01

### Added
- **Card gallery** — *New card* opens 24 ready-made cards built only from Home Assistant's own cards: tile (with brightness / cover / fan / HVAC features), thermostat, alarm, scenes, scripts, room (heading + sensors + every device in an area), pages menu, phone-only menu, who is home, people map, weather, sensor with graph, history, gauge, energy, to-do, calendar, media, camera, heading, text, grid, column and web page. Cards whose devices you don't have are greyed out. *Like the cards next to it* is still there.
- **Where it shows** — every card (and section) gets phone / tablet / laptop / large-screen switches and a user list. Uses HA `visibility` (same breakpoints as the HA editor); inside add-on containers that ignore it, the card is wrapped in a `conditional` card, and unwrapped again when everything is switched back on.
- **Preview by device** — phone (390px), tablet (820px) and laptop (1180px) widths in the preview, with a notice when the card is hidden at that size.
- **Icon library** in both editors — 13 curated groups, search across all 7000+ MDI icons by name and keywords (Bulgarian words too), recently used icons first. The map editor shows icons that fit the device plus *More icons…*.
- **Sections views** — max columns and dense section placement.
- **Kiosk mode on phones only** — separate switches written to `kiosk_mode.mobile_settings`.
- Text fields for heading, URL and Markdown content.

### Fixed
- Map editor: the right panel could not scroll, so the bottom settings of a point were cut off. The whole panel now scrolls with a sticky list header.
- Map editor: proper layout on tablets and phones (map on top, settings below, icon-only toolbar).
- *New card* on a page of a sections view no longer tries to insert into the page list; it goes into the last section (or a new one).

## 1.0.0 — 2026-10-01

First public release as a HACS dashboard plugin.

### Added
- **Command palette (Ctrl+K)** — search cards, pages, devices and actions from one box.
- **Redo** (Ctrl+Y / Ctrl+Shift+Z) next to undo.
- **Card toolbar** — move up/down, add a card by device, duplicate, hide, remove, and *Show on the page* (jumps to the card and outlines it).
- **Add card by device** — copies the look of a neighbouring card for the same kind of device, otherwise adds a standard tile.
- **Tabbed card settings** — Content, Actions, Style and Code (JSON with copy / format / apply).
- **General settings** — dashboard title, one theme for all pages, kiosk-mode switches, device check, cleanup of unused shared styles, backup download / restore, editor preferences.
- **Page settings** — theme, subview, and *Who sees it* (per-user visibility).
- **Any map** — every `picture-elements` card with points can be opened in the map editor, not only the original 3D map; supports `sections` views and image-upload media images.
- **English and Bulgarian UI** — follows the Home Assistant language or a manual choice.
- **Responsive layout** — works from wide desktops down to phones.
- **Help & shortcuts** dialog (`?`).

### Fixed
- The live preview no longer freezes on the state from when the editor was opened.
- The default dashboard and YAML dashboards are detected correctly (YAML opens read-only; auto-generated dashboards explain how to take control).
- Map history is shared between the map pencil and the settings editor.
- Animation images use a relative path, so they work both locally and through a remote URL.
