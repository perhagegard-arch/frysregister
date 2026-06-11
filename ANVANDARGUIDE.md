# 📘 Användarguide – Frysregister

En praktisk handbok för vardagsanvändningen. Appen finns på <https://perhagegard-arch.github.io/frysregister/> – lägg till den på hemskärmen och använd alltid den ikonen.

## Vardagsflödet

**Lägga in mat:** Tryck “＋ Lägg till vara”. För vilt väljer du bara djurslag och styckningsdel – namnet skapas automatiskt (“Älg – Färs”). Ange antal förpackningar och gärna vikt per förpackning, så räknas totalvikten ut. Datumet är förifyllt med idag.

**Ta ut mat:** Tryck på **−** på varans kort när du tar en förpackning. Tar du den sista försvinner varan automatiskt och loggas i historiken. Lade du tillbaka något? Tryck **＋**.

**Hitta något:** Använd sökrutan (söker namn, djurslag, styckningsdel och anteckningar) eller filtrera per frys, kategori och – för vilt – styckningsdel.

**Tyda färgerna:** Gul kant = varan har passerat 75 % av sin rekommenderade frystid. Röd kant = tiden har passerats. Kom ihåg: maten blir aldrig farlig av lång frystid, det är smak och konsistens som försämras – lukta och bedöm själv. Bannern “Ät detta först” visar vad som bör prioriteras.

## Vyerna (knapparna uppe till höger)

|Knapp|Vy             |Används till                                                                             |
|-----|---------------|-----------------------------------------------------------------------------------------|
|📋    |Sammanställning|Hela innehållet grupperat, per frys eller totalt. Härifrån skriver du även ut/sparar PDF.|
|🍳    |Recept         |Middagskomponören, AI-kocken och de inbyggda recepten                                    |
|📖    |Sparade recept |Din receptbank med favoriter från AI-kocken                                              |
|📊    |Statistik      |Kg per djurslag, vikt per frys, förbrukning senaste 30 dagarna                           |
|📜    |Historik       |Logg över allt som lagts in och tagits ut                                                |
|⚙️    |Inställningar  |Frysnamn, API-nyckel, frystidstabell, säkerhetskopiering                                 |

## AI-kocken

**Recept på en vara:** 🍳 → “Fråga AI-kocken” → välj vara → skriv vad du är sugen på (“klyftpotatis och en rödvinssås”) → ✨. Receptet visar vad som tas ur frysen (✓), tillagning, uppläggningstips och vinval.

**Komponera en middag:** 🍳 → bocka i förrätt/varmrätt/efterrätt → ev. önskemål (“festmiddag för 6, gärna älgen”) → Komponera meny. AI:n ser hela frysen, söker recept på nätet och avslutar med en inköpslista du kan kopiera. Tar 30–60 sekunder.

**Spara favoriter:** Blev det gott? Tryck 💾 Spara recept på kortet så hamnar det i 📖.

**Kostnad:** Ett enkelt recept kostar runt 5–10 öre, en hel meny med websökning 25–50 öre. Saldo fylls på via console.anthropic.com.

## Viktigt att veta om datalagring

All data sparas **lokalt på den enhet du använder**. Det betyder:

- iPad, iPhone och dator har **var sin** lista – de synkas inte (ännu)
- Använd iPaden som huvudenhet och flytta data vid behov med Exportera/Importera under ⚙️
- På iPhone/iPad: hemskärmsappen och Safari-fliken har **separata** minnen – håll dig till hemskärmsikonen
- **Exportera en säkerhetskopia regelbundet** (t.ex. varje söndag). Webbläsaren kan i sällsynta fall rensa lokal data.

## API-nyckeln

Nyckeln skapas på console.anthropic.com (API Keys → Create key) och visas **bara en gång** – kopiera direkt. Klistra in under ⚙️ på **varje enhet** som ska använda AI:n. Dela aldrig nyckeln; vid misstänkt läcka raderar du den i konsolen och skapar en ny.

## Felsökning

|Problem                                |Lösning                                                                                                                          |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
|“Kunde inte nå AI:n” med HTTP 401      |Fel/ogiltig nyckel – klistra in på nytt, utan mellanslag                                                                         |
|“Failed to fetch”                      |Nätverket blockerar (vanligt på jobbnätverk) – testa mobilnät                                                                    |
|Ny funktion syns inte efter uppdatering|Hård omladdning: stäng appen helt och öppna igen, eller Ctrl+Shift+R på dator                                                    |
|Data/inställningar “försvann”          |Du är troligen på en annan enhet eller ingång (Safari vs hemskärm) – datan finns kvar där den skapades. Flytta med export/import.|
|Loggan syns inte                       |Kontrollera att `Logga.png` ligger i repot och att index.html är originalfilen (aldrig sparad via “Spara som”)                   |