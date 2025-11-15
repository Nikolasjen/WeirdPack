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

### 3. Tilføj lyde

Minecraft har per standard nogle lyde til alt i spillet. Disse lyde har nogle specifikke navne og placeringer i ResourcePack-strukturen, som du skal følge for at overskrive Minecrafts standardlyde (dette kan også gøres programmerisk - se afsnit 3.1).

*For at holde denne resource pack så lille som muligt, samt for ikke at overskrive lyde unødigt, indeholder denne pakke kun et udvalg af lyde. Dette betyder, at du skal tilføje eller ændre lyde manuelt, samt de mapper hver lyd skal ligge i per Minecrafts struktur - See også '[All Vanilla Sounds](https://www.curseforge.com/minecraft/texture-packs/all-vanilla-sounds)' for en liste over alle vanillelyde fra eks. 1.18.2.*

For at ændre en lyd i Minecraft:

* Naviger til mappen `resourcepack/assets/minecraft/sounds/` og find den lydfil du vil ændre -- hvis du ikke kan finde en allerede eksisterende lydfil, kan du blot oprette en ny, i en undermappe der passer til den lyd du forsøger at redigere.
* Sørg for at lydfilen er i `.ogg`-format og har et unikt navn -- følger du Minecrafts konventioner, vil det gøre det lettere at finde og identificere lydene senere.


### 3.1. Opdater `sounds.json`

Der er flere muligheder for tilpasning af lyde i Minecraft. Den ene er beskrevet ovenfor, hvor du eks. erstatter en lydfil direkte. Den anden metode er at opdatere `sounds.json`-filen for at definere nye lyde eller ændre eksisterende lyde. Det er dog vigtigt at bemærke, at hvis du kun tilføjer nye lyde uden at opdatere `sounds.json`, vil Minecraft ikke vide, hvordan eller hvornår disse lyde skal afspilles.

Du kan her tage udgangspunkt i den eksisterende `sounds.json`-fil i mappen `assets/minecraft/` og tilføje dine egne lyddefinitioner, og du kan læse mere om dette [her](https://minecraft.wiki/w/Sounds.json).

<!-- Tilføjer du en ny lyd, skal du opdatere filen `sounds.json` i mappen `assets/minecraft/` for at sikre, at Minecraft genkender og bruger de nye lyde. -->

## Guide til `sounds.json`

I Minecraft ResourcePacks bruges filen `sounds.json` til at definere hvilke lyde, der skal afspilles for bestemte events i spillet. Denne fil indeholder en liste over lydnavne og deres placeringer i pakken.

### Eksempel på en `sounds.json` fil:

```json
{
  "entity.creeper.primed": {
        "category": "hostile",
        "replace": "true",
        "sounds": [
            "custom/creeper_fuse"
        ],
        "subtitle": "subtitles.entity.creeper.primed"
    },
}
```

I eksemplet ovenfor:
* `entity.creeper.primed` er navnet på lyd-`eventet`, som bruges, når en creeper er ved at eksplodere.
* `category` angiver lydkategorien (f.eks. `hostile`, `ambient`, `block`, etc.).
* `replace` angiver, om denne lyd skal erstatte den eksisterende lyd i spillet.
* `sounds` er en liste over lydfiler, der skal afspilles for dette event (uden filendelse).
* `subtitle` angiver den tekst, der vises som undertekst, når lyden afspilles.

<!-- ### Hvordan man opretter en ny lyd-`event`

1. Opret et unikt lydnavn i `sounds.json` (f.eks. `"my_custom.sound"`)
2. Tilføj en lydfil med samme navn som eventet (f.eks. `custom/my_sound`).
3. Hvis du vil ændre eksisterende spillyde, skal du finde det relevante eventnavn i den officielle Minecraft-dokumentation eller i den eksisterende `sounds.json`-fil og ændre filstien. -->

## Bidrag

Hvis du vil hjælpe med at udvikle WeirdPack, så vær venlig at følge disse retningslinjer:

1. Opret en ny branch til dit bidrag.
2. Lav dine ændringer, og tilføj nye lyde eller opdater `sounds.json`-filen.
3. Send en pull request til hovedrepoen med en beskrivelse af de ændringer, du har lavet.

## Licens

Dette projekt er licenseret under **GNU General Public License v3.0**. Se LICENSE-filen for detaljer.

---

### Yderligere Ressourcer:

* **Minecraft ResourcePack guide**: [Official Minecraft Wiki - Resource Packs](https://minecraft.gamepedia.com/Resource_pack)
* **Creating a Resource Pack**: [Minecraft Wiki - Creating a Resource Pack](https://minecraft.wiki/w/Tutorial:Creating_a_resource_pack)
