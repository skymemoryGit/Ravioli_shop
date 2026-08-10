# Prompt: sito web "KX Ming Ravioli"

Copia-incolla questo prompt in un tool di generazione siti (Lovable, v0, Bolt, Cursor, Claude Code, ecc.) o consegnalo a uno sviluppatore/agenzia.

---

## PROMPT

Costruisci un sito web one-page per **"KX Ming Ravioli"**, una ravioleria artigianale specializzata in ravioli al vapore. Il sito deve avere un forte effetto "wow" iniziale basato su un'animazione scroll-driven cinematografica, in stile ai siti awwwards con reveal a strati (es. i siti che mostrano un burger che si assembla pezzo per pezzo mentre si scrolla).

### 1. Concept dell'animazione di apertura (elemento centrale del sito)

L'intera hero section è un'animazione **agganciata allo scroll** (scroll-scrubbed, non autoplay) divisa in 4 fasi. Lo scroll dell'utente controlla il tempo dell'animazione, non la fa solo comparire.

**Fase 1 — Vaporiera chiusa**
Inquadratura frontale di una vaporiera di bambù (steamer) chiusa, con vapore leggero che sale, su sfondo scuro/materico (legno, marmo). Il logo "KX Ming Ravioli" appare in overlay, minimale, poi sfuma per lasciare spazio allo scroll.

**Fase 2 — Apertura a strati**
Continuando a scrollare, il coperchio si solleva e ruota via. I cestelli della vaporiera si separano uno dall'altro (effetto stacking/parallasse in 3D o pseudo-3D), rivelando che sono impilati più livelli, ognuno con un tipo diverso di ravioli.

**Fase 3 — Reveal dei tipi di ravioli**
Man mano che ogni cestello si apre, la camera/il focus si sposta su di esso e appaiono, in sequenza:
- cestello 1: ravioli **al ripieno di carne** (impasto naturale)
- cestello 2: ravioli **al ripieno di pollo**
- cestello 3: ravioli **colorati** (impasto tinto naturalmente: rosso barbabietola, verde spinaci, giallo curcuma, viola cavolo)

Accanto a ogni cestello compaiono micro-etichette/tag animate con nome del ripieno e 2-3 ingredienti chiave, in stile "info-pin" che si agganciano al prodotto mentre scorre (simile alle etichette ingredienti del video di riferimento).

**Fase 4 — Confezionamento e delivery**
Gli stessi ravioli si "raccolgono" e vengono impacchettati in una box da delivery che si chiude in scena. Sul coperchio della box appare, in un lettering elegante ed essenziale, la scritta **"KX Ming Ravioli"**. La box resta ferma al centro come chiusura della hero, con una CTA che appare sotto ("Ordina ora" / "Scopri il menu").

**Note tecniche sull'animazione:**
- Usare scroll-scrubbing (GSAP ScrollTrigger o equivalente) su una sequenza di immagini/frame oppure su livelli con transform 3D (translateZ, rotateX/Y, opacity), non video autoplay.
- L'animazione deve occupare più viewport di scroll (es. 400-600vh) prima di sbloccare lo scroll normale della pagina.
- Su mobile: versione semplificata (meno frame, transizioni più rapide, eventualmente sostituire il layer-stacking 3D con crossfade tra fasi) per garantire fluidità.
- Precaricare gli asset dell'animazione con un loader iniziale leggero (es. barra di caricamento minimale con il logo) per evitare scatti.
- Prevedere `prefers-reduced-motion`: fallback statico con le stesse info in formato più semplice (fade-in classico).

### 2. Identità visiva

- Palette: toni caldi e naturali (bambù, terracotta, crema) con un accento vivace ripreso dai colori dei ravioli colorati (rosso, verde, giallo/senape).
- Font: un sans-serif moderno per i testi, con un font più artigianale/calligrafico per il logo "KX Ming Ravioli".
- Fotografia/illustrazione: still-life food fotografico di alta qualità, texture legno/bambù/carta da forno, vapore, mani che lavorano l'impasto.
- Mood: artigianale ma contemporaneo, non "ristorante cinese cliché" — più vicino a un brand food premium/delivery moderno.

### 3. Struttura del sito (dopo la hero animata)

Come riferimento per struttura contenuti e taglio "delivery-friendly", prendi spunto da **ravioleria-ging.it/#menu** (microsite JustEat di una ravioleria reale a Verona) e adattalo all'identità di KX Ming Ravioli:

1. **Hero animata** (descritta sopra)
2. **Chi siamo** — breve storia del brand, artigianalità, ravioli fatti a mano
3. **Recensioni** — riprendi il pattern di Ging: badge con rating aggregato (es. stelle + numero di recensioni) subito sotto l'hero/header, con eventualmente una carosello di 3-4 recensioni reali/fittizie in evidenza
4. **Menu** — sezione centrale del sito, organizzata **per categorie** con card prodotto (nome, breve descrizione ingredienti, prezzo, foto). Struttura consigliata, ispirata a Ging ma centrata sui ravioli:
   - **Ravioli al Vapore** (il cuore del menu): carne, pollo, manzo, gamberi, verdure/vegetariani, colorati (barbabietola, spinaci, curcuma) — indicare sempre il numero di pezzi per porzione (es. "4 pezzi")
   - **Ravioli alla Griglia/Padella** — stesse varianti, versione grigliata
   - **Bao** — se previsti nel menu, pane al vapore ripieno (salato/dolce)
   - **Antipasti** — es. involtini, edamame, insalata di alghe, pane al vapore
   - **Zuppe**
   - **Salse** — extra a piccolo prezzo (soia, piccante, agrodolce)
   - **Bevande**
   Ogni voce con nome piatto, breve descrizione ingredienti (es. "ripieno di manzo, zenzero e cipollotto"), prezzo in €. Card cliccabile/hover con foto ravvicinata del piatto.
5. **Come nascono i ravioli** — sezione con step (impasto → ripieno → chiusura a mano → cottura al vapore), micro-animazioni on-scroll leggere
6. **Ordina/Delivery** — CTA verso ordinazione online (integrazione JustEat/Deliveroo/Glovo o ordine diretto), replicando da Ging il blocco "Ordina online" ben visibile in header/hero
7. **Galleria/Instagram feed**
8. **Trovaci** — indirizzo, mappa, **orari di apertura** distinti per "Consegna" e "Ritiro al locale" (tabella giorno per giorno, come su Ging), zona/CAP di consegna
9. **Contatti**
10. **Footer** con logo, social, newsletter

### 4. Note sul tono/contenuti presi da Ging

Dal sito di riferimento porta con te questi pattern, adattandoli al brand:
- rating/recensioni in evidenza vicino al nome del locale
- pulsante "Ordina online" sempre raggiungibile (header sticky)
- descrizioni piatto brevi e concrete (ingredienti, non aggettivi)
- indicazione pezzi per porzione sui ravioli
- tabella orari apertura separata per consegna e ritiro
- indicazione chiara della zona di consegna (CAP/area coperta)

### 5. Stack tecnico consigliato

- Next.js (o Vite + React) + Tailwind CSS
- GSAP + ScrollTrigger per l'animazione principale
- Lenis o Locomotive Scroll per lo smooth scroll
- Immagini in WebP/AVIF, lazy loading su tutto ciò che è sotto la fold
- Ottimizzato per Core Web Vitals nonostante l'animazione pesante (asset compressi, sequenza immagini ridimensionata per viewport)

### 6. Tono dei testi

Caldo, diretto, un po' giocoso ma senza scadere nel cliché. Frasi brevi. Il nome "KX Ming Ravioli" deve comparire come firma ricorrente (hero, footer, box di delivery).

---

*Nota: l'animazione descritta richiede asset dedicati (sequenza di foto/render della vaporiera che si apre a strati, dei ravioli e della box). Se non esistono ancora, vanno commissionati a un fotografo/3D artist food, oppure realizzati come illustrazione/render 3D stilizzato invece che fotografia reale.*
