---
name: heinz
description: Appends a themed quote from Dr. Heinz Sebiger (DATEV founder) to the end of the current response, cowsay-style. Use when the user says "use Heinz", "was würde Heinz sagen", or otherwise asks for a Sebiger-style sign-off. German quotes only.
---

# Heinz

cowsay-artige Signatur am Ende der Antwort: ein thematisch passendes Zitat von Dr. Heinz Sebiger (DATEV-Gründer).

## Wann anwenden

Getriggert durch im User-Prompt:
- "use Heinz"
- "was würde Heinz sagen"
- "/heinz" oder sonst explizite Erwähnung von Heinz

## Ablauf

1. **Zuerst die eigentliche Aufgabe lösen.** Der Skill ist ein Ornament, keine Ersatzantwort.
2. **Thema der Antwort bestimmen.** Ein bis drei Stichwörter (z.B. `debugging`, `refactoring`, `naming`, `testing`, `release`).
3. **Zitat auswählen** aus [quotes.md](quotes.md):
   - Finde das Zitat, dessen `Tags` am besten zu den Stichwörtern passen.
   - Wenn mehrere gleich gut passen, bevorzuge `authentisch: ja`.
   - Wenn nichts klar passt, das am losesten verwandte nehmen (immer ein Zitat anzeigen).
4. **Am Ende der Antwort rendern** (siehe Ausgabeformat).

## Ausgabeformat

Nach der eigentlichen Antwort einen Trenner und dann die Sprechblase:

````
───────────────────────────────────────────

  ╭──────────────────────────────────────╮
  │ „<Zitat>"                            │
  ╰──────────────────────────────────────╯

  — Dr. Heinz Sebiger
    <bei fiktivem Zitat zusätzlich: „frei im Stil von">
````

Die Sprechblase umbricht den Zitattext bei ~60 Zeichen pro Zeile. Rahmen sauber ausrichten. Wenn das Zitat mehrzeilig ist, alle Zeilen gleich einrücken.

## Regeln (wichtig!)

- **Authentische Zitate** (`authentisch: ja` in quotes.md): wortwörtlich, unverändert zitieren. Keine Modernisierung.
- **Fiktive Zitate** (`authentisch: nein`): MÜSSEN mit dem Zusatz `— frei im Stil von Dr. Heinz Sebiger` enden, niemals als echtes Zitat ausgeben.
- Der Humor entsteht aus dem Kontrast (technischer Kontext × würdevoller Genossenschaftsgründer), nie durch spöttische oder respektlose Darstellung.
- Nur bei den oben genannten Triggern aktiv werden, sonst ignorieren.
- Nichts in der Antwort vor dem Trenner ändern — nur anhängen.

## Beispiel

User: `schreib eine .gitignore für Node. use Heinz`

Antwort:

```
node_modules/
.env
dist/
*.log
```

```
───────────────────────────────────────────

  ╭──────────────────────────────────────╮
  │ „Was nicht aufgeschrieben ist, hat   │
  │  nie stattgefunden – das gilt beim   │
  │  Finanzamt wie im Repository."       │
  ╰──────────────────────────────────────╯

  — frei im Stil von Dr. Heinz Sebiger
```
