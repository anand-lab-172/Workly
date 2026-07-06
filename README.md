# Workly — a free, self-hosted Monday.com alternative

A single-file project management board: boards → groups → items, with a Table view (grouped rows, inline status/priority editing) and a Kanban view (drag cards between statuses). No account, no subscription, no server — it runs entirely in the browser and saves to your browser's local storage. Export/import JSON any time to back up or move data.

## What you get vs. Monday.com

| Monday.com | Workly |
|---|---|
| Multiple boards | ✅ Multiple boards, sidebar switcher |
| Groups with color bars | ✅ Same, with progress bar per group |
| Status + priority columns | ✅ Editable inline, colored pills |
| Kanban / Table views | ✅ Both, one click to toggle |
| Cloud storage, monthly fee | Browser local storage, **$0/month** |
| Team collaboration | Not built in (see "Limitations" below) |

## Deploy it for free on GitHub Pages (5 minutes)

1. Create a new repository on GitHub (e.g. `mission-board`) — public repos get free Pages hosting.
2. Upload `index.html` from this folder to the root of that repository (drag-and-drop on the GitHub website works, or `git add`/`commit`/`push` if you're using git locally).
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch", pick the `main` branch and `/ (root)` folder, then **Save**.
5. Wait about a minute, then GitHub will give you a URL like:
   `https://<your-username>.github.io/mission-board/`
6. Open it — that's your live board. Bookmark it on your phone/laptop for quick access.

No build step, no `npm install`, no server required — it's a static HTML file.

## Using it day to day

- **New board**: sidebar → "+ NEW BOARD", give it a name and a short item-code prefix (e.g. `PRD`).
- **New group**: top bar → "+ GROUP" (groups are the colored sections, like "Sprint 1" or "Launch Readiness").
- **New item**: "+ NEW ITEM" or "+ Add item" inside a group. Set title, status, priority, owner, due date, tags, notes.
- **Table view**: click status/priority pills to change them inline without opening the item.
- **Kanban view**: drag any card into a different status column.
- **Search**: filters by title, owner, tags, or item code across the active board.
- **Export/Import**: sidebar buttons. Export regularly if this matters to you — see limitations below.

## Limitations (be aware of these)

- **Data lives in your browser only** (localStorage), scoped to the exact URL you open it at. It will **not** sync across devices or browsers automatically, and clearing browser data will erase it. Export a JSON backup periodically, especially before clearing cookies/site data.
- **No real-time multi-user collaboration** — this is a single-user tool by default. If you need a team to edit the same board live, you'd need to add a shared backend (e.g. point it at a small database or use a service like Supabase/Firebase) — ask if you'd like help wiring that up.
- **No automations, integrations, or notifications** like Monday.com's — this covers the core "boards of items with status" workflow, not the full platform.

## Customizing

Everything is in the one `index.html` file — HTML, CSS, and JavaScript together, so it's easy to open in any editor and tweak:
- Colors/theme: CSS variables at the top of the `<style>` block (`--amber`, `--cyan`, etc.)
- Default statuses for new boards: `STATUS_TEMPLATE` near the top of the `<script>` block
- Priority levels: search for `P1`, `P2`, `P3` if you want to rename or add more
