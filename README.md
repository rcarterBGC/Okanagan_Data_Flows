# Okanagan Data Flows

Interactive data-dependency flowchart for **Okanagan Basin Creeks Floodplain Mapping, Phase 2** (BGC 0511017, FBC / FHIMP).

It shows what each workstream needs and from whom, the milestone calendar, and who sits on each team.

## Using it

Open `index.html` in Chrome or Edge. It is a single self-contained file: no install, no server, no build step. It only goes online for Google Fonts, and falls back to system fonts without internet.

- **Hover over a box** to isolate its inputs and outputs.
- **Click a box** for its people, deliverables and due dates.
- **Pick a name** under "Who's on each team" to highlight every team that person works on.
- **Click a calendar item** to open the team that owns it.

## Editing

Everything on the page is generated from plain JavaScript lists near the top of the `<script>` block in `index.html`. To change content, edit the list and reload the page.

| What to change | Look for | Format |
|---|---|---|
| People | `const P = {` | `ID:["Full Name","Company","Role"],` — company is `BGC`, `Pinna`, `ONA` or `Ecoscape` |
| Team membership, outputs, dates | `const N = {` | each team has `team:[["ID","lead|core|support|review","Role on this team"], …]` and `due:[["Date","Deliverable","Review window"], …]` |
| Arrows (data hand-offs) | `const DE=[` | `["from","to","label",[[x,y],…points],[labelX,labelY],"type"]` — type is blank (hand-off), `"fb"` (feedback loop) or `"sc"` (screening) |
| Box positions and text | `const L={` | `x, y, w, h` in chart units (canvas is 1400 × 700) |
| Milestone calendar | `const EV=[` | `["YYYY-MM-DD","Label","m2|m3|m4|m5|mpm","teamId"]` |

The chart boxes are `sd` (Survey & Field Data), `hydro`, `geo`, `ldof`, `hyd`, `map`, `en` (Engagement), `rep` and `fbc`. `sd` and `en` are built by merging the `survey`/`data` and `eng2`/`eng3` team entries.

Colours and fonts are CSS variables at the top of the `<style>` block (`--c-hydro`, `--c-geo`, …), with separate values for dark mode.

## Publishing with GitHub Pages (optional)

Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`. The site will be served at `https://rcarterbgc.github.io/Okanagan_Data_Flows/`.

Note: GitHub Pages sites are public unless the repository belongs to a paid organization plan with private Pages. The page contains staff names and roles, so check before enabling Pages on a personal account.

## Source

Built from *Okanagan Project Team – Roles and Connections.pptx* (01 Project Management / 02 Team Project Coordination / 05 Project Team Coordination), with later corrections from the project team.
