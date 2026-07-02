# Ashley's Fighter Jet 🛸

A kid-friendly, portrait-mode mobile game. Steer a fighter jet left and right
with your thumb to dodge cute aliens descending from the top of the screen,
and tap to shoot them down.

Everything lives in a single `index.html` — vanilla HTML5 Canvas, zero dependencies,
no build step.

## Run it

```
node server.js
```

Then open:

- **On this PC:** http://localhost:8000
- **On your phone (via Tailscale):** http://100.118.156.77:8000
  (or use the machine's MagicDNS name, e.g. `http://<machine-name>:8000`)

The server binds to all interfaces on port 8000, so any device on your tailnet can reach it.

> **If the phone can't connect:** Windows Firewall may be blocking inbound
> connections to Node. Allow it via the popup Windows shows the first time,
> or run (as admin):
> `netsh advfirewall firewall add rule name="Ashley Jet 8000" dir=in action=allow protocol=TCP localport=8000`

## Controls

- **Mobile:** press and drag your thumb anywhere on the screen — the jet follows left/right.
  Quick **tap** (without dragging) to fire a bullet — tap 3 times for 3 bullets.
- **Desktop:** ← / → arrow keys (or A/D) to steer, Space/Enter to shoot (and to start)

## Gameplay

- Each alien that flies past you = **+1 point**
- Shooting an alien = **+1 point** — one hit destroys it, and the bullet stops on impact
- Aliens get faster and more frequent the longer you survive
- Best score is saved on the device (localStorage)
- Touch an alien and you get "bonked" — tap to fly again

## Sound

All audio is synthesized live with the Web Audio API (no sound files):
dreamy space background music, a "pew" when you shoot, a happy pop when
an alien is hit, and a wobbly "womp" when the jet crashes. Tap the 🔊
button in the top-right corner to mute/unmute (remembered per device).
Sound starts after the first tap — browsers require a user gesture.
