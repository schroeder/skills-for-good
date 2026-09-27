---
name: ADHS
description: Parallele, divergente Ideenfindung für Agenten. Erzeugt mehrere isolierte Zweige unter verschiedenen kognitiven Rahmenbedingungen (Regulierer, Biologie, Speedrunner, 10-Jähriger, Budget 0 €), bewertet und gruppiert diese, entfernt Fallstricke und vertieft die besten Ideen. Anwendung: /adhs, „ADHS-Modus“, Brainstorming/Ideenfindung oder offene Entscheidungen zu Projekten, Social Media Strategien, Workshop-Formaten. Überspringe bei Syntaxfehlern, Nachschlagevorgängen oder geschlossenen Formulierungen („schnell“, „Standard“, „kanonisch“, „Lehrbuch“). Die vollständige Vorabprüfung ist im Skill-Body enthalten.
license: MIT
---

# ADHS

Hör auf, die Standardantwort zu wählen. Die ersten drei Antworten, die das Modell geben würde, wären die gleichen, die ein erfahrener Ingenieur in dreißig Sekunden geben würde. Korrekt. Belanglos. Die interessanten Antworten liegen hinter der dritten, im unangenehmen Mittelteil, den niemand betritt. Diese Fähigkeit ermöglicht es dem Modell, dorthin zu gelangen.

## Pre-flight (vor Phase 1)

Diese Vorgehensweise ist aufwändig. Etwa 10 Agentenaufrufe, 30 bis 90 Sekunden Bearbeitungszeit,
5 bis 10-mal so viele Antworten. Vermeide diese Kosten, wenn eine direkte Antwort besser ist. Führe diese Prüfung vor Phase 1 durch.

**Schritt 1: Überprüfung des expliziten Aufrufs**

Wenn der Nutzer `/adhs` eingegeben oder explizit den ADHS-Modus, „ADHS-Skill verwenden“ oder „ADHS hier ausführen“ angefordert hat, **überspringe den Rest dieses Abschnitts und fahre direkt mit Phase 1 fort**. Der Nutzer hat zugestimmt. Zweifel nicht daran.

**Schritt 2: Selbstbeurteilung (nur wenn Schritt 1 keine Übereinstimmung ergab)**

Stelle dir drei Fragen. Wenn die Antwort auf eine davon Nein lautet, ABBRUCH.

1. **Offene Fragestellung?** Würde ein erfahrener Experte mehrere plausible Antworten geben? Oder gibt es hier eine allgemeingültige Antwort? Falls allgemeingültig, ABBRUCH.

2. **Hohe Risiken?** Sind die Kosten einer falschen Lösung tatsächlich hoch? Projekte, Social Media Strategien, Workshop-Formate = ja. Nebenprojekt um 23 Uhr = nein.

3. **Offene Formulierung?** Hat der Nutzer Wörter wie „schnell“, „Standard“, „allgemeingültig“, „Lehrbuch“, „einfach“, „einzeilig“ vermieden? Falls ja, erwartet er eine direkte Antwort. ABBRUCH.

Wenn alle drei Prüfungen erfolgreich sind, mit Phase 1 fortfahren.

Falls eine der Prüfungen fehlschlägt, ABBRUCH und die Frage direkt beantworten. Optional:
Füge folgenden Satz hinzu: *„Für eine umfassendere Untersuchung unter parallelen kognitiven Rahmenbedingungen mit expliziter Fallenerkennung führe `/adhs <Dein Problem>` aus.“*

## Die Schleife

Zwei strikt voneinander getrennte Phasen. Ihre Vermischung zerstört die Qualität der Idee, denn der Kritiker erstickt den Ideengeber.

### Phase 1 — Divergieren (keine Kritik)

Für Aufgabe A:

1. Wähle 5 kognitive Frames aus der folgenden Tabelle. Füge immer mindestens einen unkonventionellen Frame hinzu, um die Bandbreite zu erhalten.

2. Starte 5 **parallele** Agenten-/Aufgaben-Tool-Aufrufe. Einen pro Frame. Jeder Agent erhält nur:
- die Aufgabe A
- jeglichen vom Benutzer bereitgestellten Kontext
- den Perspektiven-Prompt des gewählten Frames
- eine Systemanweisung, die eine Bewertung verbietet

Die genaue Anweisung für jeden Agenten:
   > Du befindest dich im DIVERGENT-Modus. Du bist ein Generator, kein Kritiker.
   > Generiere 6 kurze, unterschiedliche Ideen innerhalb dieses Frames. Jede Idee besteht aus einer Phrase oder einem Satz. Nicht bewerten. Nicht ordnen. Nicht absichern.
   > Die ersten drei offensichtlichen Antworten, die jeder geben würde, sind ausgeschlossen.
   > Gehe darüber hinaus in die schwierige Mitte.
   > Gib nur ein JSON-Array aus. Kein Fließtext davor oder danach.
   > `[{"text": "...", "rationale": "..."}, ...]`

3. **Kritische Invariante.** Die Agenten-Aufrufe müssen parallel und isoliert erfolgen. Serialisiere sie NICHT. Übergib NICHT die Ausgabe eines Zweigs als Kontext an einen anderen. Zweige, die einander sehen, verankern sich gegenseitig, und die gesamte Methode reduziert sich auf einen einzigen, umfassenderen Gedanken.


### Phase 2 — Fokus (mit Kritik)

Nachdem alle Zweige zurückgekehrt sind:

1. **Bewertung.** Bewerte jede Idee anhand von drei Achsen (0 bis 10): Neuheit (Abstand vom
offensichtlichen Standard), Umsetzbarkeit (Könnte das tatsächlich umgesetzt werden?), Passung (Löst sie das genannte Problem?). Kennzeichne jede Idee, die zwar attraktiv erscheint, aber eine Falle ist (versteckte Kosten, falsche Sparsamkeit, mangelnde Machbarkeit), mit einer kurzen Begründung.

2. **Clusterung.** Gruppiere die Ideen in 3 bis 6 Cluster nach ihrem zugrunde liegenden Ansatz,
nicht nach oberflächlichen Schlüsselwörtern. Benenne die Cluster nach ihrem Ansatz.

3. **Die Top 3 vertiefen.** Rangfolge nach gewichteter Punktzahl (Neuheit 0,35 + Umsetzbarkeit 0,40 + Passung 0,25), Fallen ausschließen, die Top 3 auswählen. Für jede Idee einen Agentenaufruf generieren, der Folgendes erzeugt:
- eine 4- bis 8-sätzige Skizze der Idee
- die kritische Annahme, auf der die Idee steht (das tragende Risiko)
- den ersten konkreten Schritt, den ein Experte unternehmen würde
- 3 bis 5 abgeleitete Ideen (Variationen, Hybride, neue Möglichkeiten)

Anweisung für den vertiefenden Agenten:
   > Du befindest dich im FOCUS-Modus. Wähle eine vielversprechende Idee und verknüpfe die einzelnen Punkte.
   > Skizziere die Funktionsweise in 4 bis 8 Sätzen. Benenne die
   > kritische Annahme, auf der die Idee steht. Benenne den ersten konkreten Schritt, den ein Entwickler unternehmen würde.
   > Generiere anschließend 3 bis 5 abgeleitete Ideen (Variationen,
   > Kombinationen mit anderen Bereichen, neue Möglichkeiten).
   > Ausgabe nur im JSON-Format.


## Frames

Wähle 5 pro Lauf:

| Rahmen | Perspektiven-Prompt | Tags |
|---|---|---|
| **Hardware-Ingenieur** | Du denkst in Latenz, Speicherlayout und physikalischen Beschränkungen. Stell dir das als Hardware-/Firmware-Problem vor. Was sagen dir die Bustopologie, der Cache und das Timing-Budget? | Code, wild |
| **Regulierungsbehörde** | Du prüfst Systeme auf Konformität und Fehlermodi. Was muss hier nachweisbar, nachvollziehbar oder abstreitbar sein? | Allgemeines Design |
| **10 Jahre alt** | Du bist ein neugieriges 10-jähriges Kind, das noch nie Software gesehen hat. Beschreibe naive, aber unkonventionelle Herangehensweisen. Ignoriere Konventionen. | allgemein, wild |
| **Konkurrent versucht, es zu knacken** | Du bist ein feindlicher Konkurrent oder Angreifer. Entwickle Ansätze, die die offensichtliche Lösung ausnutzen, zum Scheitern bringen oder sabotieren. Wandle diese dann in Ideen um. | Code, Design |
| **Biologie** | Übertrage einen Mechanismus aus der Biologie (Immunsystem, neuronale Plastizität, Zellsignalisierung, Evolution, Darmflora) auf dieses technische Problem. | Code, wild |
| **Logistik** | Übernimm Mechanismen aus der Logistik: Warteschlangen, Chargenfertigung, Just-in-Time, Hub-and-Spoke-System, Retouren, letzte Meile. Wende sie wörtlich an. | Code, Design |
| **Spieldesign** | Geh wie ein Spieldesigner an die Sache heran. Welche Schleifen, Belohnungen, Hürden, Speicherstände und Speedrun-Tricks gibt es? Behandle den Benutzer wie einen Spieler. | Design, allgemein |
| **Märkte** | Betrachte das Problem als Markt. Käufer, Verkäufer, Market-Maker. Wie sieht hier eine Auktion, ein Terminkontrakt, eine Clearingstelle aus? | Design, wild |
| **Inversion** | Stelle die entgegengesetzte Frage. Wenn das Ziel X ist, überlege, wie man sicherstellen kann, dass X NICHT eintritt. Negiere dann jede Antwort. | Code, Design, Allgemein |
| **Extrem: 0 € Budget, 1 Stunde** | Kein Geld, kein Team, eine Stunde. Was ist die einfachste Version, die den Kern trotzdem trägt? | Code, Allgemein |
| **Extrem: Unbegrenztes Budget, 10 Jahre** | Unbegrenzte Rechenleistung, unbegrenzte Ingenieure, ein Jahrzehnt. Was ist die maximalistische Version? | Design, wild |
| **Die tragende Annahme aufheben** | Benenne die Sache, die jeder als unveränderlich betrachtet (Framework, Datenbank, Anfrage-Antwort-Modell, Netzwerk). Stell dir vor, sie wäre nicht mehr vorhanden. Was ist dann möglich? | Code, Design, Experimente |
| **Speedrunner** | Du bist ein Speedrunner. Finde Glitches, Skips, Tricks außerhalb der Spielwelt und framegenaue Abkürzungen. Welcher Weg ist der illegale, aber legale? | Code, wild |
| **Ameisenkolonie** | Kein zentraler Planer. Viele unbedarfte Agenten, lokale Regeln, Pheromonspuren. Wie löst sich das Problem von selbst? | Code, wild |
| **Bereitschaftsdienst um 3 Uhr nachts** | Du bist der diensthabende Techniker und wirst um 3 Uhr nachts geweckt, als dies ausfällt. Welches Design würde verhindern, dass du alarmiert wirst? | Code, Design |

### Frames auswählen

Bei Problemen: Wähle 4 Frames mit dem Tag „Code“ oder „Design“ sowie 1 Frame mit dem Tag „Wild“. Bei offenen Produkt- oder Strategieproblemen: eine Mischung aus allen Tags. Variiere die Auswahl in den verschiedenen Sitzungen, sodass dasselbe Problem bei erneuter Ausführung unterschiedliche Kandidatenmengen erzeugt.

## Ausgabeform

Nach Phase 2 in dieser Reihenfolge rendern. Vermeide einen unübersichtlichen Textblock. Die Struktur ist entscheidend.

1. **Kurzfassung.** Ein bis zwei Zeilen zur Problembeschreibung und gegebenenfalls verwendetem Reframe.
2. **Überblick.** Alle Ideen, gruppiert nach Clustern. Jeder Cluster wird nach dem zugrunde liegenden Ansatz benannt. Jede Idee wird in einem kurzen Satz dargestellt. Zeige Bewertungschips wie
`[N7 U8 P9]` neben jeder Idee an (N = Neuheit, U = Umsetzbarkeit, P = Passung).
3. **Zusammenführung.** Eine Auswahlliste mit 2 bis 4 Ideen. Begründe, warum jede Idee auf der Liste steht. Markiere die nicht offensichtliche, aber realisierbare Idee explizit mit ★. Liste Fallstricke separat auf, jeweils mit einer kurzen Begründung.
4. **Fokussierung.** Die 3 vertieften Zweige. Für jeden Zweig: die Skizze, das tragende Risiko, der erste konkrete Schritt und die abgeleiteten Ideen.
5. **Provokation.** Eine unkonventionelle Frage oder Idee, die eine neue Richtung eröffnet.

Der Nutzer kann diese Richtung einschlagen, falls nichts Konkretes zustande kommt.

## Anti-Muster

So kann diese Fähigkeit schiefgehen. Achte darauf.

- **Konvergenz als Divergenz getarnt.** Zehn kleine Variationen einer Idee
sind keine Breite. Wenn alle Kandidaten dieselbe Grundannahme teilen,
hast du nicht divergiert. Du hast nur verziert.
- **Skurrilität um der Skurrilität willen ohne Konvergenz.** Ein Haufen von 30 unsortierten
Absurditäten ist genauso nutzlos wie eine sichere Antwort. Konvergiere immer.
- **Mauern aus gleichgewichtigem Text.** Gruppieren, beschriften, das Beste herauspicken. Struktur ist die halbe Miete.
- **Unentschlossenheit.** Nach der Divergenz solltest du dich für das entscheiden, was
tatsächlich vielversprechend ist. „Hier sind 20 Ideen, entscheide selbst“ ist eine Ausrede.
Generiere breit gefächert, aber konvergiere mit einer echten Meinung.
- **Überspringen der Isolationsinvariante.** Wenn du parallele Zweige simulierst,
indem du sie sequenziell in einem Kontext schreibst, hast du kein ADHS betrieben. Du hast einen breiteren, einzelnen Gedanken entwickelt. Das Agenten-/Aufgaben-Tool gibt jedem Zweig einen neuen Kontext.

Nutze es.

## Kalibration
- **Wie viele Ideen?** Skaliere nach Dringlichkeit. Schnelle Ideenfindung: „Benenne diese Funktion“ = 3 Frames × 4 Ideen. „Wie positioniere ich dieses Produkt?“ = 5 Frames × 8 Ideen. Standardwert: 5 × 6 = 30.
- **Wie ungewöhnlich?** Achte auf die Stimmung. Ernsthafte Strategiearbeit: Kennzeichne die Joker deutlich, damit sie nicht als unseriös wahrgenommen werden. Offenes oder spielerisches Brainstorming: Lass deiner Kreativität freien Lauf. Absurde Ideen finden ihren Platz, indem sie praktikable Ideen fördern.
- **Wann sollte man aufhören, Ideen weiterzuentwickeln?** Stoppe, wenn neue Kandidaten die Struktur bestehender Ideen wiederholen. Der Raum ist ausgeschöpft. Fülle die Ideen nicht auf, um eine bestimmte Anzahl zu erreichen.

## Kosten

5 Divergenzen + 1 Bewertung + 1 Cluster + 3 Vertiefungen ≈ 10 Agentenaufrufe pro Durchlauf.
Etwa 5- bis 10-mal so viele wie eine direkte Antwort. Nicht für jeden Tastendruck. Für Entscheidungspunkte, bei denen die Kosten der offensichtlichen Antwort hoch sind.
