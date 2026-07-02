# Ashley's Fighter Jet 🛸

A kid-friendly, portrait-mode mobile dodge game. Steer a fighter jet left and right
with your thumb to dodge cute aliens descending from the top of the screen.
No shooting, no power-ups — just dodging (for now).

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

- **Mobile:** press and drag your thumb anywhere on the screen — the jet follows left/right
- **Desktop:** ← / → arrow keys (or A/D), Space/Enter to start

## Gameplay

- Each alien that flies past you = **+1 point**
- Aliens get faster and more frequent the longer you survive
- Best score is saved on the device (localStorage)
- Touch an alien and you get "bonked" — tap to fly again
