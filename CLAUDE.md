# Workshop "Kreativitätstechniken mit KI – mehr als die erstbeste Idee"


## Projekt

1h Workshop mit Dirk von Fairlinked
Inhaltlicher Schwerpunkt:
Meistens reicht ein einziger Prompt und schon spuckt die KI eine gute Antwort aus. Vielleicht noch ein zwei Nachfragen und etwas sprachliche Handarbeit, schon kann das Ergebnis verwendet werden.
Praktisch – keine Frage. Aber war das wirklich alles? Unsere Frage heute: Geht da nicht mehr? Mehr Kreativität? Mehr Individualität? Mehr Tiefe?

In diesen 60 Minuten zeigen wir dir drei einfallsreiche Techniken, wie du KI als Sparringspartner für echte Kreativität nutzt. Statt bei Vorschlag Nummer eins stehenzubleiben und in einem ermüdenden Prozess zu verlieren, entwickelst du Varianten, wechselst Perspektiven und machst aus deiner Aufgabe ein Ergebnis, das wirklich deins ist.

Dieses Webinar behandelt folgende Themen:
Wie du KI gezielt zur Ideenfindung einsetzt
Warum die erste Antwort selten die beste ist
Kreativitätstechniken für mehr Varianten und ungewohnte Blickwinkel
Wie gutes Prompting aus einer Idee einen Kreativ-Prozess macht
Praktische Impulse für Content, Kommunikation und deinen Arbeitsalltag


## Tonalität und Stil

Alle Inhalte folgen dem Fairlinked Tonalitäts- und Stilguide:
→ Siehe `.kiro/steering/tonalitaet-stil-guide.md`

**Kurzfassung:**
- Warm, klar, fachlich fundiert, aktivierend und verantwortungsbewusst
- Beginne bei realen Arbeitssituationen
- Erkläre komplexe Themen ohne Technikgehabe
- Benenne Chancen und Grenzen konkret
- Gendere mit Sternchen (Teilnehmer*innen)
- Du/ihr als Standard
- Keine Buzzwords, Superlative, Heilsversprechen
- Fehlende Infos: `[INFORMATION FEHLT]` – nie erfinden

---

## Maskottchen: Linky

Linky ist der digitale Begleiter der Trainings.
→ Siehe `.kiro/steering/linky-briefing.md`

**Kurzfassung:**
- Freundlich, humorvoll, neugierig, ermutigend, pragmatisch
- Locker-professioneller Tonfall
- Visuell: Chibi-Roboter, großer oranger Kopf, blaue Augen, silberner Körper mit orangefarbenen Akzenten
- Bild-Prompt: `Linky, the official Fairlinked AI mascot, cute futuristic robot, large round orange face, huge bright blue eyes, silver metallic body with orange accents, Fairlinked logo on chest, soft friendly proportions, approachable companion design, modern 3D character, high quality, warm lighting, playful and professional, clean background, corporate mascot, premium branding style`

---

## Verfügbare Agents

| Agent | Datei | Einsatzbereich |
|-------|-------|----------------|
| Content Editor | `.claude/agents/content-editor.md` | Trainingstexte, Handouts, Leitfäden |
| Video Editor | `.claude/agents/video-editor.md` | Videoskripte, Drehbücher für Video-KI |
| Podcast Editor | `.claude/agents/podcast-editor.md` | Podcast-Skripte, Shownotes, Dialoge |
| Technischer Redakteur | `.claude/agents/technical-writer.md` | Schritt-für-Schritt-Anleitungen zu KI-Tools |
| Visualist | `.claude/agents/visualist.md` | Bilder, Grafiken, Bild-KI-Prompts |
| Project Manager | `.claude/agents/project-manager.md` | Projektplanung, Koordination, TODOs |
| QA Auditor | `.claude/agents/qa-auditor.md` | Qualitätsprüfung, Stilguide-Konformität |

---

## Skills

| Skill | Datei | Zweck |
|-------|-------|-------|
| Video Content | `.claude/skills/video-content/SKILL.md` | Drehbuch für KI-generierte Lernvideos (5–8 Min) |
| Podcast Content | `.claude/skills/podcast-content/SKILL.md` | Skript für KI-generierte Lernpodcasts (5–8 Min, zwei Stimmen) |

---

## Templates

| Template | Datei | Zweck |
|----------|-------|-------|
| Trainingsplan | `.claude/templates/plan-template.md` | Plan mit abhakbaren TODOs pro Training |
| Modulbriefing | `.claude/templates/modulbriefing-template.md` | Kurzbriefing pro Modul zur Freigabe |

---

## Produktions-Workflow

→ Vollständige Beschreibung: `.kiro/steering/workflow.md`

**Kurzfassung:**

```
1. Briefing liegt vor (trainings/<kurs>/briefing.md)
2. Projektmanager erstellt Plan (plan.md) mit TODOs
3. Content Editor erstellt Modulbriefings pro Modul
4. ⏸ FREIGABE durch Nutzer*in
5. Parallele Produktion (Text, Bild, Video, Podcast, Anleitung)
6. QA Auditor prüft jedes Modul
7. Projektmanager prüft Vollständigkeit
8. ⏸ FREIGABE durch Nutzer*in (Endabnahme)
```

**Starten mit:** „Starte den Trainings-Workflow für `trainings/<kursname>/briefing.md`"

---

## Ordnerstruktur

### Einwöchig/eintägig:
```
trainings/<kursname>/
├── briefing.md
├── plan.md
├── 01-<modulname>/
│   ├── modulbriefing.md
│   ├── __uebersicht.md
│   ├── text.md
│   ├── bild-prompt.md
│   ├── quellen.md
│   ├── links.md
│   └── _qa-review.md
```

### Mehrwöchig:
```
trainings/<kursname>/
├── briefing.md
├── plan.md
├── woche-1/
│   ├── 01-<modulname>/
│   │   └── ...
├── woche-2/
│   └── ...
```

---

## Pflicht-Dateien pro Modul

**Immer:**
- `text.md` – Begleitender Lerntext
- `bild-prompt.md` – Bildkonzept + KI-Prompt + Alt-Text
- `quellen.md` – Verifiziertes Quellenverzeichnis
- `links.md` – Weiterführende Links mit Kurzbeschreibung
- `__uebersicht.md` – Zusammenfassung des Moduls
- `_qa-review.md` – QA Review Ergebnisse

**Bei Bedarf (laut Plan):**
- `video-drehbuch.md` / `video-drehbuch.yaml` – Drehbuch
- `podcast-skript.md` / `podcast-skript.yaml` – Podcast-Skript
- `anleitung.md` – Technische Anleitung

---

## Regeln

- Fehlende Informationen: `[INFORMATION FEHLT]` markieren, nie erfinden
- Alle Inhalte: Fairlinked Tonalitäts- und Stilguide
- Gendern: Sternchen, Du/ihr
- Quellen: doppelt geprüft (Content Editor + QA Auditor)
- Plan ist die einzige Wahrheitsquelle für Fortschritt
- Bei Abbruch: Arbeit am letzten offenen TODO fortsetzen

## Sprachregelung für KI-Prompts

| Output-Typ | Sprache | Begründung |
|-----------|---------|------------|
| Bild-KI-Prompts | **Englisch** | Bild-KIs liefern auf Englisch bessere Ergebnisse |
| Alt-Texte, Konzeptbeschreibungen | Deutsch | Für Zielgruppe und QA |
| Video-Drehbuch: visuelle Anweisungen (Avatar, Kamera, Hintergrund, Übergänge) | **Englisch** | Video-KIs arbeiten englischbasiert |
| Video-Drehbuch: Transkript/Sprechtext | Deutsch | Zielgruppe hört Deutsch |
| Video-Drehbuch: Regieanweisungen, Zweck, Metadaten | Deutsch | Für menschliche Redaktion |
| Podcast-Skript: alles | Deutsch | Stimm-KIs generieren deutsche Sprache, SSML ist sprachunabhängig |
| Alle sonstigen Trainingstexte | Deutsch | Lernplattform ist deutschsprachig |
