# sternum-band
Bandpage van Sternum

# Sternum website — project context

## Doel van de site
De website is een visuele, donkere, moderne bandsite voor **Sternum** uit Arnhem.  
De site moet niet voelen als een blog of standaard portfolio, maar als een **strakke band-landingpage** met sterke hero, media, shows en about-sectie.

De site is gebouwd als een **single page** met fullscreen/panel-achtige secties.

---

## Technische basis
- Statische site
- Eén hoofdbestand: `index.html`
- HTML + CSS + kleine stukjes JavaScript
- Geen framework
- Hosting via GitHub Pages

Bestandsnamen die gebruikt worden:
- `herobanner.jpg` → desktop hero
- `herobanner-mobile.jpg` → mobile hero
- `logo.png` → logo in fixed navbar
- `sternum1.png` → grote bandfoto in about
- `background-setlist.jpg` → achtergrond van de shows-sectie

YouTube video:
- Video ID: `8SoVOSPKfFM`
- Wordt geladen via de YouTube Iframe API
- Autoplay muted
- Eigen sound toggle knop

---

## Structuur van de site
De site bevat op dit moment deze hoofddelen:

1. **Fixed navbar**
2. **Hero**
3. **Media** (video + Spotify)
4. **Shows**
5. **About**
6. **Footer**

Daarnaast:
- scroll dots rechts op het scherm
- about modal popup
- booking modal
- video sound toggle

---

## Media-sectie (UPDATE)

### Functie
Direct onder de hero staat de video + Spotify embed.

### Opbouw
- framed YouTube video
- custom sound knop
- video selector
- Spotify embed

### Belangrijke keuzes
- video is **niet fullscreen**
- bewust gecentreerd en begrensd (max-width)
- visueel rustiger dan fullscreen video

### Padding / spacing
- extra ruimte onder Spotify toegevoegd
- voorkomt dat “Shows” te abrupt begint

---

## Shows-sectie (UPDATE)

### Structuur
Bestaat uit 2 delen:
1. **Upcoming**
2. **Full agenda**

### Layout
- tour-style (geen kaarten)
- grote datum links
- info rechts

### Mobile gedrag
- stacked layout (geen grid)
- betere leesbaarheid

### Belangrijk
Deze sectie moet:
- strak
- scanbaar
- geloofwaardig

---

## About-sectie (UPDATE)

### Opbouw
- grote foto bovenaan
- korte intro
- knop → modal

### Modal (nieuw gedrag)
- scrollable (max-height + overflow)
- sticky header
- close-knop blijft zichtbaar

### Structuur in modal
- kopjes toegevoegd (DE BAND, ONTSTAAN, etc.)
- betere leesbaarheid
- geen lange lap tekst

### Belangrijke fix
Probleem:
- tekst ging onder navbar bij scroll

Oplossing:
- padding-top toegevoegd in modal-content
- sticky header correct afgezet

---

## Modals (UPDATE)

### About modal
- scrollable content
- sticky header
- close knop altijd zichtbaar

### Booking modal
- formulier aanwezig
- werkt nu via `mailto:` fallback

---

## Booking (BELANGRIJKE UPDATE)

Huidige status:
- mailto (onbetrouwbaar)

Geplande oplossing:
→ **FormSubmit (zonder backend)**

Waarom:
- werkt op GitHub Pages
- geen server nodig
- betrouwbaarder dan mailto

Nog te doen:
- form action instellen
- test op live domein

---

## Responsive gedrag (AANGEPAST)

### Desktop
- alles gecentreerd
- media breder gemaakt
- shows aligned met rest

### Mobile
- navbar aangepast (rechts uitlijnen)
- hero afbeelding lager gepositioneerd
- shows volledig herbouwd voor mobile
- extra spacing fixes (media → shows)

---

## Belangrijke technische lessen (UPDATE)

### 1. Layout consistency
Alles moet dezelfde max-width / alignment gebruiken  
→ anders krijg je “links hangende” secties (zoals bij shows probleem)

### 2. Fixed + sticky = risico
Navbar + modal + sticky header kunnen botsen  
→ altijd spacing/padding testen

### 3. Mobile is aparte layout
Niet alleen schalen  
→ vaak echt opnieuw structureren (zoals shows)

---

## Huidige open punten / volgende stappen (UPDATED)

1. Booking form (FormSubmit implementeren)
2. Navbar active states
3. Footer echte links
4. Shows filtering (future/past)
5. Performance optimalisatie (images/video)
6. Kleine mobile spacing fixes
7. Eventueel animaties bij scroll

---

## Werkwijze voor vervolg
Als je in een nieuwe chat verder werkt:

1. Laat eerst dit README lezen
2. Werk per sectie
3. Verander maar één onderdeel tegelijk
4. Geef altijd exacte code replacements

---

## Huidige projectidentiteit
Sternum-site = een donkere, visueel sterke, moderne band-landingpage met fullscreen hero, gecentreerde media, tour-style shows en image-first about met modal verdieping.
