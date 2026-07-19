# UNSLEEVED — Card Ripping Commerce Mockup

A single-page, mobile-first mockup for a digital pack-ripping app: users buy
mystery packs containing **real physical sports cards**, reveal them one at a
time, then decide per card — keep in the vault, sell back for instant credit,
or ship to their door.

**No backend, no build step.** Everything is static/fake data in one file.

## Run it

Open `index.html` in any browser. That's it. (Google Fonts load over the
network; system fallbacks are used offline.)

## Views

1. **Shop** — four pack tiers ($5 / $25 / $100 / $500) with max pull value,
   printed odds, and a chase-card preview. Wallet balance in the header.
2. **Rip Experience** — the centerpiece. Drag the foil strip to tear the pack
   (or smash the button), then tap-to-flip each card with CSS 3D transforms.
   Reveal order escalates by value; rare+ cards get a suspense "charge"
   (shake, gold glow, screen dim), and big hits trigger a gold ray burst,
   confetti, banner slam, haptic pulses, and a count-up market value.
3. **Post-Rip Decision** — per-card Vault / Sell Back / Ship segmented
   controls plus a spent-vs-pulled-vs-net summary.
4. **Vault** — kept cards in retro frames, total value, and a "Ship Selected"
   flow with a mock address sheet.
5. **Wallet** — balance, non-functional deposit/cash-out, and rip activity
   ledger.

## Notes for the real build

- **Sound hooks:** all game events route through `playSound(name)` and also
  dispatch a `sfx` CustomEvent (`grab`, `tear`, `flip`, `charge`, `hit`,
  `cash`, `ship`, …). Wire real audio there.
- **Haptics:** `haptic(pattern)` wraps `navigator.vibrate` where supported.
- Pack odds in the shop tiles are display-only; the demo generator boosts hit
  rates by tier so the celebration path is easy to see.
- All players, cards, serials, and prices are fake demo data.
