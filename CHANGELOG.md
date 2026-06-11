# 📜 Changelog – Frysregister

Alla betydande ändringar dokumenteras här. Versionsnumren följer utvecklingsordningen.

## v11 – 2026-06-11

- AI-kocken uppgraderad till Michelin-persona: smakbalans, texturer, säsong och menytänk
- Nytt fält i alla AI-recept: 🎨 Uppläggning
- Sparade recept: 💾-knapp på alla AI-recept och menyrätter, ny 📖-vy med receptbanken
- Egen logga (Pers Kök & Vinkällare) i appens header, med emoji-reserv om bilden saknas

## v10.2 – 2026-06-11

- **Buggfix:** uppdaterat modellnamn till `claude-sonnet-4-6` (gamla namnet gav HTTP 404)
- **Buggfix:** borttagen duplicerad middagskomponör-panel med krockande kod

## v10.1 – 2026-06-11

- Förbättrad felhantering: AI-fel visar nu exakt felmeddelande (HTTP-status m.m.) med felsökningstips

## v10 – 2026-06-11

- 🍽️ Middagskomponören: välj förrätt/varmrätt/efterrätt, AI:n ser hela frysen, söker recept på nätet (webbsökverktyg aktiverat i API-anropet), komponerar meny och skriver inköpslista med kopiera-knapp

## v9 – 2026-06-11

- 📋 Sammanställningsvy: allt innehåll grupperat per kategori och djurslag, med frysväljare, delsummor och totaler
- Utskrift/PDF-export med ren utskriftslayout

## v8 – 2026-06-10

- 🤖 AI-kocken: recept på vald vara utifrån fritextönskemål, via Anthropic API
- Stöd för egen API-nyckel (sparas lokalt), hantering under ⚙️ Inställningar
- AI-recepten markerar vilka ingredienser som tas ur frysen

## v7 – 2026-06-10

- 🍳 Receptvy med inbyggd receptbank: 12 viltanpassade recept (älggryta, rådjursinnanlår, viltfärsbiffar, vildsvinsstek, harragu, vildfågel, insjöfisk, bärpaj m.fl.)
- Matchning mot faktiskt frysinnehåll med “✓ finns i frysen”-markering
- Vintips per recept (förberedelse för vinkällar-koppling)

## v6 – 2026-06-10

- Namnfältet döljs för vilt – namnet byggs automatiskt av djurslag + styckningsdel
- Benchmark mot marknadens appar (NoWaste, KitchenPal m.fl.) genomförd

## v5 – 2026-06-10

- Filtrering på styckningsdel (visas när Vilt-filtret är aktivt)

## v4 – 2026-06-10

- Styckningsdel som rullista: Innanlår, Ytterlår, Fransyska, Rostbiff, Rulle, Filé, Ryggbiff, Revben, Färs, Bog + Annat

## v3 – 2026-06-10

- Individuella frystider per kategori enligt Livsmedelsverket, Svenskt Kött och Råd & Rön
- Nya kategorier: Lagad mat (3 mån), Chark & Korv (2 mån), Bröd & Bak (3 mån)
- Automatisk igenkänning av feta varor (lax, sill, fläsk…) → max 3 mån
- Varningar relativa till varje varas egen gräns (gul vid 75 %, röd vid passerad)
- Egen frystidsgräns per vara
- Referenstabell över frystider under ⚙️

## v2 – 2026-06-10

- Snabbknappar ＋/− på varje varukort, sista förpackningen tar bort varan
- Automatisk historiklogg (📜) över in- och uttag
- Statistikvy (📊): kg per djurslag, vikt per frys, förbrukning 30 dagar
- “Ät detta först”-banner med de äldsta varorna
- Redigerbara frysnamn
- Säkerhetskopiering: export/import (JSON) samt CSV-export för Excel
- Vikt per förpackning med automatisk totalvikt

## v1 – 2026-06-10

- Första versionen: tre frysar, kategorier, lägg till/ta bort varor, sök, kategorifiltrering, grundstatistik, varningar för gamla varor, mörkt tema optimerat för iPad

## Driftshändelser

|Datum     |Händelse                |Lösning                                                                                                                               |
|----------|------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|2026-06-11|Loggan visades inte     |index.html hade sparats via webbläsarens “Spara som”, vilket skrev om sökvägen till `./index_files/`. Originalfilen uppladdad på nytt.|
|2026-06-11|AI-fel HTTP 404         |Föråldrat modellnamn i koden. Uppdaterat.                                                                                             |
|2026-06-11|Dubbla komponera-paneler|Äldre kodversion låg kvar parallellt i filen. Bortstädad.                                                                             |
|2026-06-11|Frysnamn återställdes   |iOS ger hemskärmsappar och Safari-flikar separata datalagringar. Rutin: använd alltid hemskärmsikonen.                                |