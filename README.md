# SHOCKPROOF

A rebuild of the home intro of [BulletProof](https://www.wearebulletproof.com) (Awwwards Site of the Day, Nov 16 2026) with zero JavaScript of my own.
Every animation on the page is a class name from [Tweenwind](https://tweenwind.dimaac.com), my free library that turns
`gs-` classes into GSAP animations. Every time, size and ease comes from the original's own loader.

**Live demo:** https://dimaac.com/projects/shockproof
**Tutorial:** https://youtu.be/i2hx4oIjOHg
**Tweenwind:** https://tweenwind.dimaac.com ([npm](https://www.npmjs.com/package/tweenwind), [GitHub](https://github.com/Hank-D-Tank/tweenwind))

## How it works

The only script on the page is Tweenwind, which loads GSAP for you:

```html
<script src="https://cdn.jsdelivr.net/npm/tweenwind@0.2.0"></script>
```

- **One timeline:** the header is `load:gs-timeline load:gs-duration-0.7 load:gs-ease-[0.44,0.01,0,1]`, so every animated element inside
  it is one step, placed at its own time with `gs-at-[...]`.
- **The growing frame:** one element holds one `gs-to`, so four nested wrappers each carry one size step and `gs-target-[.frame]`
  (28 x 20.3vh, 30.8 x 30.8vh, 51.1 x 39.2vh, 58.8 x 53.2vh at 0.75, 1.45, 2.15 and 2.85 s).
- **The flipbook:** 17 stacked photos switch on with `gs-to-[opacity:1] gs-duration-0.01` at times that get closer and closer, from 1.55 s to 4.14 s.
- **The burst:** the video is a full-screen box clipped down to the frame. `gs-to-[--burst:1]` animates one CSS variable that
  opens the `clip-path` to full screen.
- **The labels:** SHOCK and PROOF sit on the frame's opposite corners, so at 0 x 0 they read as one word. An inner span splits them,
  the outer div flies them off.
- **Readable words:** a top layer holds the headline again plus a second copy of the video, multiplied, then inverted with
  `hue-rotate(180deg) invert(1)` and multiplied onto the page. Letters get darker wherever the video behind them is bright.
- **Phone:** `max-[479px]:gs-to-[...]` swaps the frame sizes to vw, like the original's phone version.

Open `index.html` in any modern browser. Everything is in that one file.

## Credits

- Design and motion inspired by [BulletProof](https://www.wearebulletproof.com), Awwwards Site of the Day. The brand name, photos and
  video here are placeholders; none of BulletProof's images or videos are used, and the code is written from scratch with Tweenwind.
- Photos from [Lummi](https://www.lummi.ai) (free licence), loaded from their CDN:
- "Luxury Dropper Bottle on Rocky Surface" by Binks AI - https://www.lummi.ai/photo/QmYyEnMwHSbFkmiJuCiszWnBHiAeq4c3LkysnwJhTj2WsT
- "Elegant Perfume Bottle Amongst White Petals" by Daniel Norin - https://www.lummi.ai/photo/QmaP5YsVUqgEstJ1F3aZmmqrKmrSHeKLnw6KHnotejATfR
- "Abstract Liquid Shapes" by studiomiklus - https://www.lummi.ai/photo/QmWW1ifyBsXGmor3ahjnSuZ27NRWgFFJ9LgfweedcwhTrE
- "Surreal Wave Room Scene" by Santu - https://www.lummi.ai/photo/QmaAzHcGA5yRbH8y5fPqsdSuuAcjrFsRojuNKtsy1Y3qA9
- "Dramatic Red Soda Can Liquid Splash" by Patrick Venegas - https://www.lummi.ai/photo/QmeR1uQndqiZ8dvtSgbAC5brD1isMQ2GTC2xeVuBfmsyvK
- "Elegant Glass Bottle with Blue Liquid" by PZF - https://www.lummi.ai/photo/QmVeM5Xs9s8vA47nNncS2f8wNJE1P2gTN4ySEJDU4Cb417
- "Joyful Woman with Drink" by Gabs - https://www.lummi.ai/photo/QmRWrXUJvjSBYGN1LW7onsBMovegsw69e7UKQV5ckBmRfY
- "Futuristic Glowing Cube" by Kuba - https://www.lummi.ai/photo/QmUdkkqLHUgwzsiHZGBLu1Nzobc4Xam229C5a8GAWMWugg
- "Spoon with Chocolate Spread" by Umut Hasanoglu - https://www.lummi.ai/photo/QmWogeFxnBgTuEq5oSecSQHWcaAe2pKWAZT2YnaCMK2E84
- "Energetic Asian Basketball Player in Action" by Viri Gutiérrez - https://www.lummi.ai/photo/QmRoxFeWkLpHXGh97QF5vtiqDkMizFBHLs2NqPzEdGeUWR
- "Elegant Perfume Bottle" by Ibis Design - https://www.lummi.ai/photo/QmPTQCqyA1UVH7RSFVFZHNaTtrcufUHivfBqd47MZfigrw
- "Surfer Riding a Wave" by Cayetano Gros - https://www.lummi.ai/photo/QmUHccwzcT92YB6VTCzzPALYJM4qzVPmjBLk4KJ4XDSXxD
- "Artisanal Dark Chocolate Display" by SHIHO - https://www.lummi.ai/photo/QmRArZ6QinpGc1So8jzo5ksYsJNpAW1QP9Fv8wko99gB33
- "Futuristic Elegance" by Axel Photography - https://www.lummi.ai/photo/QmeVv8fLuYrCuRgU4nGYqDCifZVmP4Z9U3c2dWD4YSGfYk
- "Golden Flask Display" by Sam Schwartz Creations - https://www.lummi.ai/photo/QmWqTA3mbEcQMBtj2r6HP1DvAjqMCDAdjKriRAb6wwqGoj
- "Vibrant Orange Popsicle in Water" by Amino - https://www.lummi.ai/photo/QmPcmA7YkToEnpQRc4E1bts8CKBoKHdA422gwZ3LZR5JWJ
- "Dynamic Velocity Sprinter" by Pablo Stanley - https://www.lummi.ai/photo/QmNbPCTeJzkvuGxrHMuSGkonecoy2prUei7d8iL1NyngEf
- "Warm Glow of Sophistication" by Mariana Pedroza - https://www.lummi.ai/photo/QmbT3naf6RqyYPse4HQQW7dRr5TsskbNP84VTynvzA3Jud
- Video: "Dancer in the dark back view" from [Mixkit](https://mixkit.co/free-stock-video/dancer-in-the-dark-back-view-1038/) (Mixkit License), loaded from their CDN.
- Fonts: [Archivo](https://fonts.google.com/specimen/Archivo) and [Cabin](https://fonts.google.com/specimen/Cabin) (SIL OFL).
