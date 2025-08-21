# Mascot Race

A simple, self-contained canvas app to run a race between your favorite mascots.

- No build tools required
- Runs entirely in the browser
- Choose which mascots participate and how long the race runs

## Quick start

Open `index.html` directly in your browser, or serve the folder locally:

```bash
# Option A: Python
python3 -m http.server 8000

# Option B: Node (if installed)
npx http-server -p 8000
```

Then visit http://localhost:8000

## Controls

- Duration: 30s, 45s, 60s
- Start: begins the race
- Reset: returns mascots to starting positions
- Mascot selection: pick which mascots are in the race

## Files

- `index.html` — App UI, canvas rendering, and race logic
- `assets/` — Mascot images

## Planned: Parachute Drop mode (portrait)

Add an optional mode for vertical monitors where mascots parachute from the top and land in a target zone.

Highlights:
- Mode toggle: Race | Drop
- Portrait-friendly canvas layout
- Procedural parachute rendering (no extra assets)
- Physics: gravity, gentle wind drift, parachute deploy to slow descent
- Winner: first to land (default) or closest to center target

Technical sketch:
- Introduce a `Mode` abstraction with `RaceMode` (current) and `DropMode` (new)
- `DropMode` maintains per-mascot state (`x, y, vx, vy, landed`) and integrates motion each frame
- Common UI (duration, start/reset, mascot selection) stays the same

## Contributing

- Keep it dependency-free and easy to run.
- Keep controls keyboard-accessible and responsive.

## License

MIT