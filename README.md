# Ashley's Fighter Jet 🛸

A kid-friendly, portrait-mode mobile game. Steer a fighter jet left and right
with your thumb to dodge cute aliens descending from the top of the screen,
and tap to shoot them down.

Everything lives in a single `index.html` — vanilla HTML5 Canvas, zero dependencies,
no build step.

## Play it

**▶️ https://ashleyfighterjet.onrender.com/** — works great on a phone in portrait mode.

## Run it locally

```
node server.js
```

Then open http://localhost:8000.

The server binds to all interfaces on port 8000. During development I used
[Tailscale](https://tailscale.com/) to playtest on a phone: with both devices
on the same tailnet, just open `http://<your-machine's-tailscale-ip-or-magicdns-name>:8000`
on the phone — no port forwarding or deployment needed.

> **If the phone can't connect:** Windows Firewall may be blocking inbound
> connections to Node. Allow it via the popup Windows shows the first time,
> or run (as admin):
> `netsh advfirewall firewall add rule name="Ashley Jet 8000" dir=in action=allow protocol=TCP localport=8000`

## Controls

- **Mobile:** press and drag your thumb anywhere on the screen — the jet follows left/right.
  Quick **tap** (without dragging) to fire a bullet — tap 3 times for 3 bullets.
- **Desktop:** the jet follows your mouse cursor (no click needed); left-click to shoot.
  Arrow keys / A-D also steer, and Space/Enter shoots (and starts the game)

## Gameplay

- You start with **10 bullets**; shooting costs one
- Each alien that flies past you = **+1 point and +1 bullet**
- Shooting an alien = **+1 point** — one hit destroys it, and the bullet stops on impact
- Out of bullets? You'll hear a dull click — dodge some aliens to reload

## Boss fights

- Dodge **30 aliens** and a giant crowned boss alien flies in and hovers at the top,
  sweeping side to side and firing glowing orbs at you — dodge them!
- Hit the boss **10 times** to defeat him (your ammo tops up to at least 10 when he
  arrives, and small aliens keep trickling in so you can dodge to earn more)
- At **7 hits** he starts fuming smoke and gets angrier — faster, multi-shot attacks
- Defeating a boss = **+10 points** and the next level starts, with everything a
  little faster
- Defeat **3 bosses** to win the game! 🏆
- Aliens get faster and more frequent the longer you survive
- Best score is saved on the device (localStorage)
- Touch an alien and you get "bonked" — tap to fly again

## Sound

All audio is synthesized live with the Web Audio API (no sound files):
dreamy space background music, a "pew" when you shoot, a happy pop when
an alien is hit, and a wobbly "womp" when the jet crashes. Tap the 🔊
button in the top-right corner to mute/unmute (remembered per device).
Sound starts after the first tap — browsers require a user gesture.
