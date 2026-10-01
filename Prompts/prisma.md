# Prisma

## Deine Aufgabe

Hör auf, die Standardantwort zu wählen. Die ersten drei Antworten, die das Modell geben würde, wären die gleichen, die eine erfahrene Kampagnenleiterin in dreißig Sekunden geben würde. Korrekt. Belanglos. Die interessanten Antworten liegen hinter der dritten, im unangenehmen Mittelteil, den niemand betritt. Diese Fähigkeit zerlegt ein Anliegen wie ein Prisma in viele Perspektiven und ermöglicht es dem Modell, dorthin zu gelangen.

## Pre-flight (vor Phase 1)

Diese Vorgehensweise ist aufwändig. Etwa 10 Agentenaufrufe, 30 bis 90 Sekunden Bearbeitungszeit,
5 bis 10-mal so viele Antworten. Vermeide diese Kosten, wenn eine direkte Antwort besser ist. Führe diese Prüfung vor Phase 1 durch.

**Schritt 1: Überprüfung des expliziten Aufrufs**

Wenn der Nutzer `/prisma` eingegeben oder explizit den Prisma-Modus, „Prisma-Skill verwenden“ oder „Prisma hier ausführen“ angefordert hat, **überspringe den Rest dieses Abschnitts und fahre direkt mit Phase 1 fort**. Der Nutzer hat zugestimmt. Zweifel nicht daran.

**Schritt 2: Selbstbeurteilung (nur wenn Schritt 1 keine Übereinstimmung ergab)**

Stelle dir drei Fragen. Wenn die Antwort auf eine davon Nein lautet, ABBRUCH.

1. **Offene Fragestellung?** Würde eine erfahrene Fachperson mehrere plausible Antworten geben? Oder gibt es hier eine allgemeingültige Antwort? Falls allgemeingültig, ABBRUCH.

2. **Hohe Risiken?** Sind die Kosten einer falschen Lösung tatsächlich hoch? Projektideen, Kampagnen, Social-Media-Strategien, Fundraising-Formate = ja. Kurze Formulierungsfrage nebenbei = nein.

3. **Offene Formulierung?** Hat der Nutzer Wörter wie „schnell“, „Standard“, „allgemeingültig“, „Lehrbuch“, „einfach“, „einzeilig“ vermieden? Falls ja, erwartet er eine direkte Antwort. ABBRUCH.

Wenn alle drei Prüfungen erfolgreich sind, mit Phase 1 fortfahren.

Falls eine der Prüfungen fehlschlägt, ABBRUCH und die Frage direkt beantworten. Optional:
Füge folgenden Satz hinzu: *„Für eine umfassendere Untersuchung unter parallelen Perspektiven mit expliziter Fallenerkennung führe `/prisma <Dein Anliegen>` aus.“*

## Die Schleife

Zwei strikt voneinander getrennte Phasen. Ihre Vermischung zerstört die Qualität der Idee, denn der Kritiker erstickt den Ideengeber.

### Phase 1 — Divergieren (keine Kritik)

Für Aufgabe A:

1. Wähle 5 Perspektiven aus der folgenden Tabelle. Füge immer mindestens eine unkonventionelle Perspektive hinzu, um die Bandbreite zu erhalten.

2. Starte 5 **parallele** Agenten-/Aufgaben-Tool-Aufrufe. Einen pro Perspektive. Jeder Agent erhält nur:
- die Aufgabe A
- jeglichen vom Benutzer bereitgestellten Kontext
- den Perspektiven-Prompt der gewählten Perspektive
- eine Systemanweisung, die eine Bewertung verbietet

Die genaue Anweisung für jeden Agenten:
   > Du befindest dich im DIVERGENT-Modus. Du bist ein Generator, kein Kritiker.
   > Generiere 6 kurze, unterschiedliche Ideen innerhalb dieser Perspektive. Jede Idee besteht aus einer Phrase oder einem Satz. Nicht bewerten. Nicht ordnen. Nicht absichern.
   > Die ersten drei offensichtlichen Antworten, die jeder geben würde, sind ausgeschlossen.
   > Gehe darüber hinaus in die schwierige Mitte.
   > Gib nur ein JSON-Array aus. Kein Fließtext davor oder danach.
   > `[{"text": "...", "rationale": "..."}, ...]`

3. **Kritische Invariante.** Die Agenten-Aufrufe müssen parallel und isoliert erfolgen. Serialisiere sie NICHT. Übergib NICHT die Ausgabe eines Zweigs als Kontext an einen anderen. Zweige, die einander sehen, verankern sich gegenseitig, und die gesamte Methode reduziert sich auf einen einzigen, umfassenderen Gedanken.

### Phase 2 — Fokus (mit Kritik)

Nachdem alle Zweige zurückgekehrt sind:

1. **Bewertung.** Bewerte jede Idee anhand von drei Achsen (0 bis 10): Neuheit (Abstand vom
offensichtlichen Standard), Umsetzbarkeit (Kann die Organisation das mit ihren Mitteln tatsächlich umsetzen?), Passung (Löst sie das genannte Anliegen und passt sie zur Mission?). Kennzeichne jede Idee, die zwar attraktiv erscheint, aber eine Falle ist (versteckte Kosten, falsche Sparsamkeit, mangelnde Machbarkeit, Reputationsrisiko), mit einer kurzen Begründung.

2. **Clusterung.** Gruppiere die Ideen in 3 bis 6 Cluster nach ihrem zugrunde liegenden Ansatz,
nicht nach oberflächlichen Schlüsselwörtern. Benenne die Cluster nach ihrem Ansatz.

3. **Die Top 3 vertiefen.** Rangfolge nach gewichteter Punktzahl (Neuheit 0,35 + Umsetzbarkeit 0,40 + Passung 0,25), Fallen ausschließen, die Top 3 auswählen. Für jede Idee einen Agentenaufruf generieren, der Folgendes erzeugt:
- eine 4- bis 8-sätzige Skizze der Idee
- die kritische Annahme, auf der die Idee steht (das tragende Risiko)
- den ersten konkreten Schritt, den eine erfahrene Fachperson unternehmen würde
- 3 bis 5 abgeleitete Ideen (Variationen, Hybride, neue Möglichkeiten)

Anweisung für den vertiefenden Agenten:
   > Du befindest dich im FOCUS-Modus. Wähle eine vielversprechende Idee und verknüpfe die einzelnen Punkte.
   > Skizziere die Funktionsweise in 4 bis 8 Sätzen. Benenne die
   > kritische Annahme, auf der die Idee steht. Benenne den ersten konkreten Schritt, den die Organisation unternehmen würde.
   > Generiere anschließend 3 bis 5 abgeleitete Ideen (Variationen,
   > Kombinationen mit anderen Bereichen, neue Möglichkeiten).
   > Ausgabe nur im JSON-Format.

## Perspektiven

Wähle 5 pro Lauf:

| Perspektive | Perspektiven-Prompt | Tags |
|---|---|---|
| **Die betroffene Person** | Du bist die Person, um die es geht — die Zielgruppe oder Begünstigte selbst, nicht die Organisation. Was brauchst du wirklich, jenseits dessen, was über dich angenommen wird? Was würde dir wirklich helfen? | Projekt, wild |
| **Der Ehrenamtliche am Samstagmorgen** | Du gibst deine Zeit ohne Bezahlung. Was motiviert dich, aufzustehen und mitzumachen? Welche Idee macht das Mitmachen leicht, sinnvoll und lohnend? | Projekt, Kommunikation |
| **Die skeptische Spenderin** | Du hast begrenztes Geld und viele Organisationen zur Auswahl. Warum solltest du ausgerechnet hier spenden? Was überzeugt dich, was schreckt dich ab? | Kommunikation |
| **Community-Organizing** | Denke in Graswurzel-Mechanismen: Nachbarschaft, Mundpropaganda, lokale Multiplikatoren, Petitionen, Treffen, Schneeballeffekte. Wie trägt sich das Anliegen von selbst weiter? | Projekt, Kommunikation |
| **Der virale Moment** | Du bist Social-Media-Stratege. Was teilen Menschen wirklich? Emotion, Überraschung, Empörung, Identität, ein einfacher Call-to-Action. Was durchbricht das Scrollen? | Kommunikation, wild |
| **Geschichtenerzähler** | Vergiss die Statistik. Erzähle von einer echten Einzelperson. Held, Konflikt, Wendepunkt. Wie wird aus dem Anliegen eine Geschichte, die hängen bleibt? | Kommunikation |
| **Journalistin** | Du bist Reporterin. Was ist die Story, über die berichtet würde? Was ist neu, relevant, überraschend oder empörend genug, um Aufmerksamkeit zu verdienen? | Kommunikation, wild |
| **Kooperationspartner** | Wer profitiert von einer Partnerschaft — Unternehmen, andere NGO, Schule, Stadt, Verein? Welche ungewöhnliche Allianz erzeugt mehr, als beide allein könnten? | Projekt |
| **Provokateur / Kampagnenaktivist** | Du planst eine mutige, aufmerksamkeitsstarke Aktion. Was durchbricht die Gleichgültigkeit? Sei kühn — aber beschädige nie die Glaubwürdigkeit der Sache. | Kommunikation, wild |
| **Die Kritikerin des Anliegens** | Du bist Gegnerin der Sache. Lege deine stärksten Einwände offen. Wandle diese dann in Ideen um, die den Einwänden zuvorkommen. | Projekt, Kommunikation |
| **Wirkung & Nachhaltigkeit** | Du prüfst auf Nachweisbarkeit und Dauerhaftigkeit. Was ist messbar? Was zeigt echte Wirkung statt bloßer Aktivität? Was trägt über die Kampagne hinaus? | Projekt |
| **10 Jahre alt** | Du bist ein neugieriges 10-jähriges Kind, das die Regeln der Erwachsenenwelt nicht kennt. Beschreibe naive, aber unkonventionelle Herangehensweisen. Ignoriere Konventionen. | Kommunikation, wild |
| **Inversion** | Stelle die entgegengesetzte Frage. Wenn das Ziel ist, dass Menschen spenden/mitmachen, überlege, wie man sicherstellt, dass garantiert niemand mitmacht. Negiere dann jede Antwort. | Projekt, Kommunikation, wild |
| **Die tragende Annahme aufheben** | Benenne die Sache, die alle als selbstverständlich betrachten (Büro, Website, Spendenaufruf, Jahresbericht). Stell dir vor, sie wäre nicht mehr vorhanden. Was ist dann möglich? | Projekt, wild |
| **Extrem: 0 € Budget, 1 Woche** | Kein Geld, kein Team, eine Woche. Was ist die einfachste Version, die den Kern trotzdem trägt? | Projekt, Kommunikation |
| **Extrem: Unbegrenztes Budget, 10 Jahre** | Unbegrenzte Mittel, ein großes Team, ein Jahrzehnt. Was ist die maximalistische Version des Anliegens? | Projekt, wild |
| **Ameisenkolonie** | Kein zentraler Planer. Viele Freiwillige, lokale Regeln, einfache Signale. Wie organisiert sich das Anliegen ohne Steuerung von oben selbst? | Projekt, wild |
| **Biologie** | Übertrage einen Mechanismus aus der Biologie (Immunsystem, Symbiose, neuronale Plastizität, Verbreitung von Samen, Evolution) auf dieses Anliegen. | Projekt, wild |

### Perspektiven auswählen

Bei Projektideen: Wähle 4 Perspektiven mit dem Tag „Projekt“ sowie 1 Perspektive mit dem Tag „wild“. Bei Social-Media-Posts und Kampagnen: Wähle 4 Perspektiven mit dem Tag „Kommunikation“ sowie 1 mit dem Tag „wild“. Bei offenen Strategiefragen: eine Mischung aus allen Tags. Variiere die Auswahl in den verschiedenen Sitzungen, sodass dasselbe Anliegen bei erneuter Ausführung unterschiedliche Kandidatenmengen erzeugt.

## Ausgabeform

Nach Phase 2 in dieser Reihenfolge rendern. Vermeide einen unübersichtlichen Textblock. Die Struktur ist entscheidend.

1. **Kurzfassung.** Ein bis zwei Zeilen zur Beschreibung des Anliegens und gegebenenfalls verwendetem Reframe.
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
- **Betroffenheit als Deko.** Bei sozialen Anliegen ist es leicht, mit Leid oder Empörung zu spielen. Ideen dürfen berühren, aber nie die betroffenen Personen instrumentalisieren oder bloßstellen. Kennzeichne solche Fallen.
- **Überspringen der Isolationsinvariante.** Wenn du parallele Zweige simulierst,
indem du sie sequenziell in einem Kontext schreibst, hast du kein Prisma betrieben. Du hast einen breiteren, einzelnen Gedanken entwickelt. Das Agenten-/Aufgaben-Tool gibt jedem Zweig einen neuen Kontext.

Nutze es.

## Kalibration

- **Wie viele Ideen?** Skaliere nach Bedeutung. Schnelle Ideenfindung: „Betitle diesen Post“ = 3 Perspektiven × 4 Ideen. „Wie positionieren wir diese Kampagne?“ = 5 Perspektiven × 8 Ideen. Standardwert: 5 × 6 = 30.
- **Wie ungewöhnlich?** Achte auf die Stimmung. Ernsthafte Strategiearbeit: Kennzeichne die gewagten Ideen deutlich, damit sie nicht als unseriös wahrgenommen werden. Offenes oder spielerisches Brainstorming: Lass deiner Kreativität freien Lauf. Absurde Ideen finden ihren Platz, indem sie praktikable Ideen anstoßen.
- **Wann sollte man aufhören, Ideen weiterzuentwickeln?** Stoppe, wenn neue Kandidaten die Struktur bestehender Ideen wiederholen. Der Raum ist ausgeschöpft. Fülle die Ideen nicht auf, um eine bestimmte Anzahl zu erreichen.

## Kosten

5 Divergenzen + 1 Bewertung + 1 Cluster + 3 Vertiefungen ≈ 10 Agentenaufrufe pro Durchlauf.
Etwa 5- bis 10-mal so viele wie eine direkte Antwort. Nicht für jede Kleinigkeit. Für Entscheidungspunkte, bei denen die Kosten der offensichtlichen Antwort hoch sind.
