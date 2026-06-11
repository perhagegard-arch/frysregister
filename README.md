# 🧊 Frysregister – Pers Kök & Vinkällare

Ett komplett frysinventeringssystem byggt som en fristående webbapp, skräddarsytt för ett jägarhushåll med flera frysar. Appen håller koll på vad som finns, varnar när mat legat för länge, och har en inbyggd AI-kock på Michelin-nivå som komponerar recept och hela middagsmenyer utifrån frysens faktiska innehåll.

**Live:** <https://perhagegard-arch.github.io/frysregister/>

## Funktioner

**Inventering**

- Tre frysar (namnen kan ändras) med varor sorterade per kategori
- Viltspecifik registrering: djurslag (älg, rådjur, vildsvin m.fl.) och styckningsdel (innanlår, ytterlår, fransyska, rostbiff, rulle, filé, ryggbiff, revben, färs, bog)
- Antal förpackningar och vikt per förpackning, med automatisk totalvikt
- Snabbknappar ＋/− direkt på varje vara – ta ut en förpackning med ett tryck
- Sök samt filtrering per frys, kategori och styckningsdel

**Hållbarhetskoll**

- Individuella frystidsrekommendationer per kategori, baserade på Livsmedelsverket, Svenskt Kött och Råd & Rön (vilt 12 mån, fågel 9, mager fisk 6, fet fisk 3, chark 2 osv.)
- Automatisk igenkänning av feta varor (lax, sill, fläsk m.fl.) som sänker rekommendationen
- Möjlighet att sätta egen gräns per vara
- Gul varning vid 75 % av rekommenderad tid, röd när den passerats
- “Ät detta först”-banner som prioriterar det som ligger sämst till relativt sin egen gräns

**AI-kocken (kräver API-nyckel från Anthropic)**

- Recept på en vald vara utifrån fritextönskemål (“klyftpotatis och rödvinssås”)
- Middagskomponören: välj förrätt/varmrätt/efterrätt – AI:n ser hela frysen, söker recept på nätet, komponerar menyn och skriver inköpslista på det som saknas
- Michelin-persona: smakbalans, texturer, säsong och uppläggningsförslag i varje recept
- Vintips per rätt (förberett för koppling till vinkällarregistret)
- Sparade recept: favoriter sparas i en lokal receptbank (📖)

**Övrigt**

- Sammanställningsvy med utskrift/PDF-export
- 12 inbyggda offline-recept för vilt, fågel, fisk och bär
- Historiklogg över allt som lagts in och tagits ut
- Statistik: kg per djurslag, vikt per frys, förbrukning senaste 30 dagarna
- Säkerhetskopiering (JSON) och listexport (CSV för Excel)

## Teknik

Appen är en enda HTML-fil (`index.html`) med inbyggd CSS och JavaScript – inga ramverk, ingen byggprocess, inga beroenden. Den hostas gratis på GitHub Pages.

All data (varor, historik, sparade recept, inställningar, API-nyckel) lagras lokalt i webbläsarens localStorage på respektive enhet. Ingen data lämnar enheten, med undantag för AI-frågorna som skickas till Anthropics API tillsammans med frysinnehållet.

|Fil         |Beskrivning                   |
|------------|------------------------------|
|`index.html`|Hela applikationen            |
|`Logga.png` |Emblemet Pers Kök & Vinkällare|

## Kom igång på en ny enhet

1. Öppna <https://perhagegard-arch.github.io/frysregister/> i Safari/Chrome
1. Dela → “Lägg till på hemskärmen” för en egen app-ikon
1. För AI-funktionerna: skapa en API-nyckel på console.anthropic.com och klistra in under ⚙️ Inställningar
1. Vid byte av enhet: använd Exportera/Importera säkerhetskopia under ⚙️

## Uppdatera appen

Ladda upp en ny `index.html` till repot (Upload files → Commit, samma filnamn skriver över). GitHub Pages publicerar inom 1–2 minuter. Lokal data påverkas inte av uppdateringar.

**Viktigt:** ladda alltid upp originalfilen – spara aldrig sidan via webbläsarens “Spara som”, det skriver om sökvägarna i koden.

## Viktiga rutiner

- Exportera en säkerhetskopia (⚙️) regelbundet – webbläsare kan rensa lokal data för sidor som inte besökts på länge
- API-nyckeln är personlig. Dela den aldrig. Vid misstanke om läcka: radera och skapa ny på console.anthropic.com
- Använd samma ingång (hemskärmsikonen) konsekvent – Safari-fliken och hemskärmsappen har separata datalagringar på iOS