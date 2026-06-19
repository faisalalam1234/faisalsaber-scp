# Download Setup — VS Code mein kya karna hai

Maine site ka code change kar diya hai. Ab **Plugins** card ke alawa baaki HAR card
(Twixtor, Zoom, Shake, Transitions, Text Animation, Glow, PNG, Overlays, CC,
Sound Effects, Fonts, Icons, AE Scripts, Motion Graphics) ka **Download** button
seedha user ke browser/system mein file download karega — Mediafire par redirect
nahi karega.

**Plugins** card jaisa tha waisa hi rahega — Download button click karne par user
ek naye tab mein official plugin website (Video Copilot / RevisionFX etc.) par
redirect ho jayega.

---

## Folder structure jo VS Code project mein banana hai

Project ke root mein (jahan ye HTML file hai), ek `files` naam ka folder banao,
aur uske andar har category ka apna sub-folder:

```
your-project/
├── FINAL_VERDICT_2_updated.html
└── files/
    ├── twixtor/
    ├── zoom/
    ├── shake/
    ├── transition/
    ├── textanim/
    ├── glow/
    ├── png/
    ├── overlay/
    ├── cc/
    ├── sfx/
    ├── fonts/
    ├── icons/
    └── aescripts/
```

(Maine ye empty folders already bana diye hain — agar aapne ZIP/files yahin se
download kiya hai to seedha use kar lo.)

## File ka naam kya rakhna hai?

Har item ka naam automatically ek "slug" filename ban jaata hai. Jaise:

- "Smooth Twixtor" → `smooth-twixtor.zip` → rakhna hoga: `files/twixtor/smooth-twixtor.zip`
- "Neon Glow" → `neon-glow.zip` → `files/glow/neon-glow.zip`
- "Lightning PNG" → `lightning-png.zip` → `files/png/lightning-png.zip`

**Sound Effects (sfx) thoda alag hai** — usme already audio filename diya hua hai
code mein (jaise `whoosh-sfx.mp3`, `IMPACT.mp3`). Wahi exact file
`files/sfx/` ke andar daalo, e.g. `files/sfx/whoosh-sfx.mp3`.
Isi file se preview (play button) bhi chalega aur download bhi hoga — ek hi file,
do kaam.

## Agar koi filename match nahi karna chahte (custom naam rakhna hai)

Code mein jis item ka naam custom rakhna ho, usme bas ek extra field add kar do:

```js
{ name: 'Smooth Twixtor', desc: '...', badge: 'popular', dl: '3.2K',
  file: 'my-custom-name.zip',   // <-- ye line add kardo
  mediafire: '...' }
```

Phir wahi file `files/<category-id>/my-custom-name.zip` par rakhni hogi.
(`mediafire` field ko hata nahi raha, woh waise hi reference ke liye pada
rahega, ab use ho nahi raha — koi nuksaan nahi.)

## Ye free hosting (GitHub Pages / Netlify / Vercel free) par chalega?

Haan, 100%. Kyunki ye sirf normal static files hain (`<a href="..." download>`),
koi server/backend/database ki zaroorat nahi. Jahan bhi HTML file host hogi,
wahi `files/` folder bhi upload kar dena — bas itna kaafi hai.

## Quick checklist
1. `files/<category>/` folder banao (already bana diya hai).
2. Har preset/sound/font ki real zip/mp3 file us folder mein daalo, naam slug se match karo.
3. Site ko publish/upload karo (HTML + files folder dono).
4. Test: kisi bhi card par "Browse" → "Download" click karke check karo file download ho rahi hai.
5. Plugins card test karo — wo external site par redirect hona chahiye (jaisa pehle tha).
