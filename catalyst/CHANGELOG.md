# Catalyst — Changelog

## v1.3 — 2026-07-22
- A personal touch: pick a name and an avatar from a gallery of 100, right from the new profile row at the bottom of the sidebar.
- Launch is steadier — fixed a race that could intermittently leave the dashboard loading forever until the app was reopened.
- The dashboard fills in faster: Python detection now checks all interpreters at once instead of one at a time.
- Package updates no longer stall silently — long installs stream their progress live, and anything that would sit waiting forever is stopped and reported.
- On Python 3.12+ with Protected mode on, package lists now say "Protected Mode" instead of offering an Install button that couldn't work.

## v1.2 — 2026-07-22
- Noticeably faster — screens open quicker and long package lists scroll smoothly, even while the machine is busy.
- A leaner backend: catalog and update requests do less work and recover cleanly when the network is slow or drops out.
- Fixed a batch of bugs from the last release, so more actions succeed on the first try.
- Groundwork under the hood for what's coming next.

## v1.1 — 2026-07-21
- Automatic updates are now verified end to end, so future versions arrive in the background and install with a single click.
- The update badge in the sidebar is quieter — it tells you what's happening and asks nothing of you until an update is ready to install.
- Small fixes and polish throughout.
