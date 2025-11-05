For at gøre din README mere tilgængelig for nybegyndere, som måske ikke er vant til at arbejde med Git eller Minecraft ResourcePacks, kan vi udvide den med klare trin og forklaringer. Jeg vil også inkludere en simpel guide til at arbejde med lyde i Minecraft, hvordan man laver/ændrer en ResourcePack, samt en oversigt over strukturen i `sounds.json` og nogle referencer til base game-lyde.

Her er den opdaterede version af din README:

---

# WeirdPack

WeirdPack er et Minecraft ResourcePack, hvor vi erstatter de standardlyde i spillet med underlige og sjove lyde. Her kan du finde og tilføje dine egne lyde til spillet, ændre eksisterende lyde og hjælpe med at udvikle denne pakke.

## Installation

1. **Download den nyeste version af WeirdPack**
   Gå til [releasesiden](https://github.com/WeirdPack/releases) og download den nyeste version af WeirdPack som en ZIP-fil.

2. **Udpak filen**
   Flyt ZIP-filen til din Minecraft **ResourcePack**-mappe. Du kan finde denne mappe i Minecrafts indstillinger under:
   `Minecraft > Options > Resource Packs > Open Resource Pack Folder`.

3. **Aktiver ResourcePack i Minecraft**
   Åbn Minecraft, gå til **Options > Resource Packs**, og klik på den ønskede pack for at aktivere den.

## Kom i gang med at udvikle

Hvis du ønsker at bidrage til WeirdPack, kan du følge disse trin:

### 1. Klon repoen (eller download den som ZIP)

Hvis du er bekendt med Git:

* **Klon repoen** ved at køre følgende kommando i dit terminal eller kommandoprompt:

  ```bash
  git clone https://github.com/WeirdPack/WeirdPack.git
  ```

Hvis du ikke er bekendt med Git:

* Du kan downloade repoen som en ZIP-fil ved at klikke på "Code" og derefter "Download ZIP".

### 2. Opret en ny branch

For at arbejde på dit eget bidrag, opret en ny branch:

```bash
git checkout -b min-branch
```

Lav dine ændringer i den nye branch.

### 3. Tilføj eller ændr lyde

For at ændre en lyd eller tilføje en ny lyd:

* Find lydfilerne i mappen `assets/minecraft/sounds/` (lydene skal være i `.ogg`-format).
* Tilføj dine egne lydfiler i mappen, og sørg for, at de har unikke navne.

### 4. Opdater `sounds.json`

Når du tilføjer eller ændrer lyde, skal du opdatere filen `sounds.json` i mappen `assets/minecraft/` for at sikre, at Minecraft genkender og bruger de nye lyde.

## Guide til `sounds.json`

I Minecraft ResourcePacks bruges filen `sounds.json` til at definere hvilke lyde, der skal afspilles for bestemte events i spillet. Denne fil indeholder en liste over lydnavne og deres placeringer i pakken.

### Eksempel på en `sounds.json` fil:

```json
{
  "sounds": {
    "random.click": {
      "category": "random",
      "sounds": [
        {
          "name": "sounds/click_weird",
          "stream": false
        }
      ]
    },
    "entity.zombie.ambient": {
      "category": "ambient",
      "sounds": [
        {
          "name": "sounds/zombie_ambient_weird",
          "stream": false
        }
      ]
    }
  }
}
```

I eksemplet ovenfor:

* `random.click` er et eksisterende spil-event (som når en spiller klikker på noget).
* Lyden af et klik er ændret til `sounds/click_weird`.
* `stream` kan være enten `true` eller `false`. Hvis `true`, streames lyden (godt til store lydfiler), ellers afspilles den som en normal fil.

### Hvordan man opretter en ny lyd-`event`

1. Opret et unikt lydnavn i `sounds.json` (f.eks. `"my_custom.sound"`)
2. Tilføj en lydfil med samme navn som eventet (f.eks. `my_custom/sound.ogg`).
3. Hvis du vil ændre eksisterende spillyde, skal du finde det relevante eventnavn i den officielle Minecraft-dokumentation eller i den eksisterende `sounds.json`-fil og ændre filstien.

### Hvordan virker event-navne i Minecraft?

Minecraft har en masse foruddefinerede lyd-`events`, som du kan finde i filen `sounds.json` i spillets standardpakke. Det er disse `event`-navne, der bestemmer, hvilken lyd der afspilles ved bestemte handlinger (f.eks. når du går, når en mob angriber, etc.).

**Eksempler på standardlyde i Minecraft:**

* `ambient.weather.rain`
* `block.wood.break`
* `entity.zombie.ambient`
* `random.click`

Du kan finde flere standardlyde i Minecrafts `sounds.json` fil, eller ved at kigge på Minecraft Wikiens lydreferencer [her](https://minecraft.fandom.com/wiki/Sound_list).

## Bidrag

Hvis du vil hjælpe med at udvikle WeirdPack, så vær venlig at følge disse retningslinjer:

1. Opret en ny branch til dit bidrag.
2. Lav dine ændringer, og tilføj nye lyde eller opdater `sounds.json`-filen.
3. Send en pull request til hovedrepoen med en beskrivelse af de ændringer, du har lavet.

## Licens

Dette projekt er licenseret under **GNU General Public License v3.0**. Se LICENSE-filen for detaljer.

---

### Yderligere Ressourcer:

* **Minecraft Wiki - Sounds**: [Minecraft Sound List](https://minecraft.fandom.com/wiki/Sound_list)
* **Minecraft ResourcePack guide**: [Official Minecraft Wiki - Resource Packs](https://minecraft.gamepedia.com/Resource_pack)

---

Med denne README vil en nybegynder nu have alle de nødvendige oplysninger for at komme i gang med at tilføje eller ændre lyde i Minecraft, arbejde med Git, og forstå, hvordan `sounds.json` fungerer.
