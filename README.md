# Skills for Good

Kreativitäts- und Denkwerkzeuge für KI-Chats — gemacht für gemeinnützige
Organisationen, Vereine und Ehrenamtliche.

Dieses Projekt sammelt vier kleine Helfer, mit denen eine KI (zum Beispiel
ChatGPT, Claude oder Gemini) dir bei typischen Aufgaben im Gemeinwohlbereich
hilft: Ideen finden, Entscheidungen schärfen, deinen Schreibstil treffen und
Bilder planen. Du brauchst dafür **keine Technikkenntnisse**. Wenn du einen
Chat mit einer KI öffnen kannst, kannst du diese Werkzeuge nutzen.

Es gibt sie in zwei Varianten:

- **Prompts** — Text kopieren, in den Chat einfügen, fertig. Funktioniert
  überall und sofort.
- **Skills** — eine Datei, die du einmal in dein KI-Tool hochlädst. Danach
  steht das Werkzeug dauerhaft bereit.

---

## Die vier Werkzeuge

| Werkzeug | Wofür es gut ist |
|----------|------------------|
| **Prisma** | Viele ungewöhnliche Ideen zu einer Frage finden — über die naheliegenden hinaus. Gut für Kampagnen, Projekte, Fundraising. |
| **Grill mich** | Eine Idee oder Entscheidung durch gezielte Rückfragen schärfen. Die KI „grillt" dich, bis der Plan rund ist. |
| **Triff den Ton** | Aus vorhandenen Texten deinen Schreibstil ableiten und daraus eine Anleitung für Social-Media-Posts bauen. |
| **Eingebildert** | Bildideen und fertige Prompts für Bild-KIs erstellen — passend zu deinem Social-Media-Post. |

---

## Variante 1: Prompten (am einfachsten)

So einfach wie Kopieren und Einfügen. Es funktioniert in jedem KI-Chat.

1. Öffne die passende Datei im Ordner [`Prompts/`](./Prompts).
2. Markiere den gesamten Text und **kopiere** ihn.
3. Öffne deinen KI-Chat (ChatGPT, Claude, Gemini …).
4. **Füge den Text ein**, schreibe dein eigentliches Anliegen dahinter und
   schick die Nachricht ab. Los geht's.

**Beispiel:** Du kopierst den Text aus `Prompts/prisma.md`, fügst ihn in den
Chat ein und schreibst darunter:

> Wie sammeln wir 5.000 € für unsere Kampagne gegen Rassismus? Wir sind ein
> kleiner Verein mit 10 Ehrenamtlichen und wollen viele Menschen erreichen.

Die KI arbeitet dann nach der Anleitung aus dem Prompt.


---

## Variante 2: Skills verwenden

Ein Skill ist eine Datei, die du einmal in dein KI-Tool hochlädst. Danach kennt
die KI das Werkzeug dauerhaft — du musst nicht jedes Mal den Text einfügen.

Die Skill-Dateien liegen im Ordner [`Skills/`](./Skills). Jede heißt
`SKILL.md` und steckt in einem eigenen Unterordner (z. B.
`Skills/prisma/SKILL.md`).

**So geht's grundsätzlich:** Datei herunterladen bzw. kopieren und im KI-Tool
dort hochladen, wo Skills, Projektdateien oder Anweisungen verwaltet werden.
Die genaue Stelle unterscheidet sich je nach Anbieter:

- **Claude (claude.ai / Claude Code):** Skills werden direkt unterstützt. Lade
  den Skill-Ordner in den Bereich für Skills bzw. in dein Projekt.
- **ChatGPT:** Lege ein eigenes „GPT" an oder nutze ein Projekt und füge den
  Inhalt der `SKILL.md` als Anweisung bzw. als hochgeladene Datei hinzu.
- **Gemini:** Nutze „Gems" (eigene Assistenten) und füge den Inhalt der
  `SKILL.md` als Anweisung ein.
- **Andere Tools (z. B. Microsoft Copilot, Mistral Le Chat):** Überall, wo du
  eigene Anweisungen oder Dateien hinterlegen kannst, funktioniert derselbe
  Weg: Inhalt der `SKILL.md` dort einfügen.

> Tipp: Wenn dein Tool keine Skills kennt, nimm einfach Variante 1 (Prompten).
> Du kannst den Inhalt einer `SKILL.md` auch direkt in den Chat kopieren.

### Die `/`-Kurzbefehle

In den Prompts tauchen Kurzbefehle wie `/prisma`, `/grill-mich`,
`/triff-den-ton` auf. Das ist einfach eine kurze Art, das Werkzeug zu starten,
statt den ganzen Text zu erklären. Manche Tools erkennen solche Befehle direkt.
Falls deins das nicht tut, kopierst du einfach den vollen Prompt-Text — das
Ergebnis ist dasselbe.

| Befehl | Werkzeug | So nutzt du ihn |
|--------|----------|-----------------|
| `/prisma` | Prisma | `/prisma` + deine Frage, z. B. `/prisma Wie gewinnen wir neue Mitglieder?` |
| `/grill-mich` | Grill mich | `/grill-mich` + deine Idee, z. B. `/grill-mich Wir wollen eine jährliche Spendengala einführen.` |
| `/triff-den-ton` | Triff den Ton | `/triff-den-ton` + 3–5 Links zu euren Texten |
| `/eingebildert` | Eingebildert | `/eingebildert` + Beschreibung des gewünschten Bildes |


---

## Welche Variante soll ich nehmen?

- **Nur mal ausprobieren oder gelegentlich nutzen?** → **Prompten.** Schnell,
  ohne Einrichtung.
- **Ein Werkzeug immer wieder nutzen?** → **Skill.** Einmal einrichten, dann
  immer griffbereit.

---

## Quellen und Inspiration

- **Prisma** — inspiriert von Udit Akhouri Raj
  ([adhdstack.github.io](https://adhdstack.github.io/))
- **Grill mich** — inspiriert von AI Hero
  ([aihero.dev/s/skills-newsletter](https://www.aihero.dev/s/skills-newsletter))

---

## Lizenz

Veröffentlicht unter der [MIT-Lizenz](./LICENSE). Du darfst die Inhalte frei
nutzen, anpassen und weitergeben.
