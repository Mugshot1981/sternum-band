# sternum-band
Bandpage van Sternum
# Sternum website — project context

## Doel van de site
De website is een visuele, donkere, moderne bandsite voor **Sternum** uit Arnhem.  
De site moet niet voelen als een blog of standaard portfolio, maar als een **strakke band-landingpage** met sterke hero, release-video, shows en about-sectie.

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

YouTube release-video:
- Video ID: `8SoVOSPKfFM`
- Wordt geladen via de YouTube Iframe API
- Autoplay muted
- Eigen sound toggle knop erboven

---

## Visuele richting / stijl
### Algemeen
- Zwarte/donkere basis
- Witte tekst
- Donkerrood accent
- Geen drukke kleurrijke UI
- Geen vrolijke of generieke webstijl
- Doel = strak, heavy, geloofwaardig, volwassen

### Kleurgebruik
Gebruik deze variabelen:
- `--bg: #0b0b0b`
- `--bg-soft: #111111`
- `--bg-deep: #070707`
- `--text: #eaeaea`
- `--text-soft: #cfcfcf`
- `--text-muted: #a8a8a8`
- `--accent: #8b0000`
- `--accent-hover: #b52b2b`

Regel:
- 90% zwart/wit
- 10% accentkleur
- rood alleen voor highlights, hover, subtiele glow, kleine details

---

## Lettertypes
Gebruikte Google Fonts:
- `Bebas Neue` → headings, tour dates, knoppen, menu
- `Inter` → body text

Richtlijn:
- `Bebas Neue` voor krachtige, uppercase visuele onderdelen
- `Inter` voor normale leesbaarheid

---

## Structuur van de site
De site bevat op dit moment deze hoofddelen:

1. **Fixed navbar**
2. **Hero**
3. **Release** (video)
4. **Shows**
5. **About**
6. **Footer**

Daarnaast:
- scroll dots rechts op het scherm
- about modal popup
- video sound toggle

---

## UX-beslissingen

### 1. Fixed top navigation
Er staat een vaste navbar bovenaan.
Deze blijft zichtbaar tijdens scrollen.

Navbar bevat:
- logo links (`logo.png`)
- links rechts:
  - Home
  - Release
  - Shows
  - About

Doel:
- altijd navigatie zichtbaar
- professionele site feel
- niet afhankelijk van terugscrollen

### 2. Scroll dots rechts
Er staan rechts bolletjes die tonen in welke sectie je zit.
Actieve dot:
- groter
- witter

Belangrijk:
- aantal dots moet gelijk blijven aan aantal `.panel` secties

### 3. Scrollgedrag
De site gebruikt section/panel scroll snapping.

Desktop:
- `scroll-snap-type: y mandatory`

Mobiel:
- `scroll-snap-type: y proximity`

Reden:
- op desktop mag het strakker voelen
- op mobiel moet het minder dwingend zijn

---

## Hero-sectie
### Functie
De hero is de eerste grote visuele indruk van de band.

### Assets
- Desktop: `herobanner.jpg`
- Mobiel: `herobanner-mobile.jpg`

### Belangrijke keuzes
- Hero moet fullscreen blijven
- Geen extra tekst over het grote Sternum-logo in de hero
- Alleen een CTA-knop:
  - `LISTEN NOW`

### CTA
De knop linkt naar `#release`.

### Belangrijke notitie
De hero mag niet “volgeschreven” worden.
Het beeld moet dominant blijven.

---

## Release-sectie
### Functie
Direct onder de hero staat de eerste release/video van de band.

### Technische keuze
De release is gebouwd met de **YouTube Iframe API**, niet met alleen een standaard iframe.
Reden:
- autoplay muted
- sound on/off knop
- meer controle dan een gewone embed

### Video instellingen
- autoplay = aan
- mute = aan bij laden
- controls = uit
- looping = aan
- eigen sound knop erboven

### Sound button
Er staat een knop boven de video:
- start als `SOUND ON`
- na klik → `SOUND OFF`
- toggelt mute/unmute via YouTube API

### Release layout
Belangrijke ontwerpkeuze:
- video is **geframed**, niet fullscreen
- hij staat iets overlappend onder de hero
- niet helemaal beeldvullend, want dat voelde te zwaar en te rommelig
- framed versie is strakker en professioneler

### Video positionering
De video moest visueel gecentreerd worden omdat de YouTube iframe anders te veel bovenkant liet zien.
Daarom is de iframe binnen `.video-wrapper` ingezoomd/gepositioneerd.

Belangrijke regel:
- de YouTube iframe wordt intern gecropt / vergroot

### Release-section offset
Er is rekening gehouden met de fixed navbar:
- `#release { scroll-margin-top: 110px; }`

Dat voorkomt dat de section te ver onder de header schuift.

---

## Shows-sectie
### Functie
Shows moet geloofwaardig en professioneel aanvoelen.
Niet als losse flyer-gallery, maar als **tour style lijst**.

### Belangrijk besluit
De eerdere aanpak met kaarten/posters was rommelig.
Definitieve richting:
- **tour style**
- grote datum links
- venue en line-up info rechts
- geen posterknoppen in de lijst

### Achtergrond
Shows gebruikt:
- `background-setlist.jpg`
- met donkere overlay

Doel:
- sfeer
- niet te druk
- tekst moet leesbaar blijven

### Inhoud
De shows zijn handmatig gebaseerd op concrete aanwijzingen/posters/teksten die tijdens het project verzameld zijn.

Volgorde is chronologisch gezet als:

1. 19 NOV ’25 — Willemeen — Arnhem · met Uncentered + DANA
2. 13 DEC ’25 — Godfest — Willemeen — Arnhem · line-up show
3. 30 JAN ’26 — Café Kroon — Arnhem · met Baardvader · sold out
4. 04 FEB ’26 — Willemeen — Arnhem · Blackout / Mokrypse / Sternum
5. 21 MAR ’26 — Nest Fest — Café Bosch — Arnhem · met meerdere bands

### Belangrijke ontwerpregel
Deze sectie moet:
- groot
- scanbaar
- rustig
- geloofwaardig

Niet doen:
- fake venues
- placeholder data
- poster chaos direct in de lijst

### Mogelijke volgende stap
Later kan dit worden opgesplitst in:
- komende shows
- afgelopen shows

---

## About-sectie
### Functie
Niet te veel tekst in één keer.
Eerst identiteit, daarna verdieping.

### Asset
- `sternum1.png`

### Belangrijke ontwerpkeuze
De foto moet dominant zijn.
Daarom is gekozen voor:
- grote foto bovenaan
- korte intro eronder
- knop `LEES MEER`
- popup/modal voor langere tekst

### Waarom
De variant met tekst naast de foto voelde te standaard.
De variant met veel tekst direct onder de foto verloor leesbaarheid.
Modal-oplossing is beter:
- houdt de sectie clean
- maakt de foto belangrijk
- geeft toch ruimte voor meer tekst

### About modal
Modal bevat:
- titel
- meerdere tekstblokken
- sluiten via:
  - kruisje
  - klik op backdrop
  - Escape-toets

---

## Footer
Footer is op dit moment simpel gehouden:
- “Follow Sternum”
- Instagram | Spotify | YouTube

Deze sectie kan later echte links krijgen.

---

## Responsive gedrag
### Desktop
- hero fullscreen
- scroll snap mandatory
- fixed navbar
- shows ruim opgezet

### Tablet / kleine laptop
- iets kleinere spacing
- iets kleinere typegroottes
- content blijft gecentreerd

### Mobiel
- aparte hero image
- scroll snap proximity
- navbar compact
- show rows onder elkaar
- about modal smaller
- CTA-knop lager in hero

---

## Belangrijke technische keuzes / lessen uit het proces

### 1. Niet te veel tegelijk aanpassen
Er zijn veel iteraties geweest.
Belangrijkste les:
- telkens één visuele of structurele wijziging tegelijk
- anders breekt layout op meerdere plekken tegelijk

### 2. Hero en release moeten niet even zwaar zijn
De hero is de hoofdingang.
De release is secundair.
Dus:
- hero fullscreen
- release framed

### 3. YouTube heeft beperkingen
YouTube branding/UI kan niet volledig verwijderd worden.
Je kunt verminderen, maar niet volledig uitschakelen.
Als later een volledig schone videopresentatie nodig is:
- overstappen op een eigen gehoste mp4/video-element

### 4. Niet vertrouwen op losse chatcontext
Belangrijke ontwerp- en codebeslissingen moeten in dit README blijven staan.
Bij vervolgwerk moet eerst dit bestand gelezen worden.

---

## Huidige open punten / mogelijke volgende stappen
1. Navbar actieve state per sectie
2. Echte links in footer
3. Shows eventueel splitsen in:
   - upcoming
   - past shows
4. Popup/modal per show met poster of detailinfo
5. About-tekst inhoudelijk sterker maken
6. Social links en contact/bookings toevoegen
7. Eventueel subtle reveal animaties bij scroll
8. Eventueel tour rows klikbaar maken
9. Eventueel loading/performance optimalisatie van hero/video

---

## Werkwijze voor vervolg
Als je in een nieuwe chat verder werkt aan dit project:

1. Laat eerst dit README lezen
2. Werk daarna per sectie
3. Verander maar één onderdeel tegelijk
4. Bij codewijzigingen:
   - altijd exact aangeven wat vervangen moet worden
   - geen globale “probeer dit eens” instructies

---

## Huidige projectidentiteit in één zin
Sternum-site = een donkere, visueel sterke, moderne band-landingpage met fullscreen hero, framed release-video, strakke tour-style shows en een image-first about-sectie.
