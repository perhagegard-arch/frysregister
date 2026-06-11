# 🗺️ Roadmap – Frysregister

## Genomfört

**Fas 1 – Grunden (v1–v2)**
Grundläggande inventering med tre frysar, kategorier, sök och filtrering. Snabbknappar ＋/− på varje vara, automatisk historiklogg, statistikvy med kg per djurslag, “Ät detta först”-banner, redigerbara frysnamn samt säkerhetskopiering (JSON) och CSV-export.

**Fas 2 – Hållbarhet (v3)**
Individuella frystidsrekommendationer per kategori enligt Livsmedelsverket m.fl. Nya kategorier (Lagad mat, Chark & Korv, Bröd & Bak). Automatisk igenkänning av feta varor. Varningar relativa till varje varas egen rekommenderade tid. Möjlighet till egen gräns per vara.

**Fas 3 – Viltanpassning (v4–v6)**
Styckningsdetaljer som rullista (innanlår, ytterlår, fransyska, rostbiff, rulle, filé, ryggbiff, revben, färs, bog). Filtrering på styckningsdel. Automatiskt varunamn för vilt (djurslag + detalj). Benchmark mot NoWaste, KitchenPal m.fl.

**Fas 4 – Recept & AI (v7–v8)**
Inbyggd offline-receptbank (12 recept för vilt, fågel, fisk, bär) med matchning mot frysinnehållet och vintips per rätt. AI-kocken via Anthropic API med stöd för egen API-nyckel.

**Fas 5 – Publicering**
Hosting på GitHub Pages, hemskärmsapp på iPad och iPhone, API-nyckel aktiverad, rutiner för uppdatering etablerade.

**Fas 6 – Premiumfunktioner (v9–v11)**
Sammanställningsvy med frysväljare och utskrift/PDF. Middagskomponören med webbsökning och inköpslista. Michelin-persona med uppläggningsförslag. Sparade recept i lokal receptbank. Egen logga i appen.

## Framtid

**Nästa steg (förslag, i prioritetsordning)**

1. **Vinkällar-kopplingen** 🍷 – Integrera vinkällarregistret så att AI-kockens vintips matchas mot flaskor som faktiskt finns hemma (“du har 2 flaskor Pinot Noir som passar”). Antingen som sammanslagen app med två flikar eller via import av vinkällarens data. *Naturligt nästa steg – loggan heter ju Pers Kök & Vinkällare.*
1. **Molnsynk** ☁️ – En liten gratis molndatabas (t.ex. Supabase) så att iPad, iPhone och dator ser samma frysar i realtid, och hela hushållet kan bocka av uttag. Löser även risken att Safari rensar lokal data. *Rekommenderas efter någon månads vardagstestning av nuvarande lösning.*
1. **Inköpslista som egen vy** 🛒 – Spara inköpslistor från middagskomponören, bocka av i butiken, lägg till egna rader.

**Längre fram (idébank)**

- **QR-etiketter** – Skriv ut QR-koder att tejpa på fryspåsarna; skanna med kameran för att se innehåll och datum, eller bocka ut varan direkt
- **Notiser** – Påminnelser när varor närmar sig sin gräns (kräver att appen görs till PWA med service worker, eller molnlösning)
- **Säsongsstatistik för jakten** – Jämför år för år: hur många kilo älg togs in 2026 vs 2027, hur snabbt förbrukas det
- **Foton på varor** – Bild per vara, praktiskt för udda styckdetaljer
- **Familjedelning med roller** – När molnsynk finns: flera användare, se vem som tog sista älgfärsen
- **Streckkodsskanning** – För köpt mat med streckkod (mindre relevant för vilt)

## Beslutslogg

|Beslut                       |Motivering                                                           |
|-----------------------------|---------------------------------------------------------------------|
|En HTML-fil utan ramverk     |Enkelt att underhålla, uppdatera och förstå för en icke-programmerare|
|localStorage före molndatabas|Noll kostnad och komplexitet; molnet byggs när behovet bevisats      |
|GitHub Pages som hosting     |Gratis för alltid, enkel uppdatering, ägaren har redan GitHub        |
|API-nyckel per enhet         |Säkrast utan backend; nyckeln lämnar aldrig enheten                  |
|Inbyggd receptbank + AI      |Offline-recept funkar i jaktstugan utan täckning; AI:n tar resten    |