---
title: 'Lernen durch Bugs'
layout: post
---

Für mein Tutorium habe ich verschiedene Lernformate durchprobiert, die eine Richtung ist es von klein zu starten und über Visualisierungen und Tests einen Zielzustand zu definieren - das ist der typische Robot Karol Online Workflow. Das klappt gut, solange die Programme kurz sind und man ausreichend Zeit hat, sich mit den allen Teilen zu befassen.

Aber im weiteren Lernprozess möchte man auch komplexere Themen behandeln. Themen, die teilweise nur innerhalb eines größeren Projekts sichtbar werden - ich denke da im Bereich 200 - 400 LOC. Es gibt verschiedene gängige Frageformate:

- A) Man stellt Verständnisfragen zum Code, die Antwort ist ein schriftlicher Absatz, kein Code.
- B) Man fordert auf, etwas am Code zu verändern oder zu modifizieren
- C) Man stellt Zwischenstufen bereit und baut das Projekt nach und nach zusammen.

Die Methode A) ist ok, sie führt nicht so in die Tiefe, aber als Füllmaterial gut zu gebrauchen. Mit B) und C) bin ich vom Ablauf bisher nicht ganz zufrieden. Wenn man Änderungen am Code fordert, dann startet man meist mit funktionierenden Code. Die eigenen Aktivitäten führen dann dazu, dass das Programm mehr Fehler enthält. Und es ist immer ein pain, die Zielvorstellung klar zu formulieren. Wann ist es genug? Wie verhindert man, dass es zu einem stupiden "Folgen-von-Anweisungen" wird? Diese frustrierenden Aspekte führen dazu, dass man dann eher ein LLM zu Rate zieht, anstatt sich selber durchzuarbeiten. Es geht um die Motivationslage: Die Startsituation ist meist ohne Bugs oder die fertige Demo, und alles was man tut hat die Gefahr, Dinge kaputt zu machen.

Zwischenstufen sind attraktiv, weil sie einem das Gefühl von Fortschritt geben. Die Stufen sind wie Checkpoints. Idealerweise sind die Stufen selber so kleinschrittig, das sie mit Unit-Tests und Anleitung gut lösbar sind. Der Aufwand für ein solches System ist aber extrem hoch. Das Schreiben der Tests, damit die interaktive Rückmeldung funktioniert, die Struktur in Zwischenstufen, etc... ein Aufwand, der die Arbeit unflexibel macht und damit mehr Last als Hilfe ist.

Ok, ich schreibe den Text natürlich, weil ich denke, eine Methode D) gefunden zu haben, die die meisten gängigen Probleme geschickt umgeht. Es ist die Bug-Hunt-Methode. Am Anfang wird ein fertiges Programm ausgeteilt, z.B. ein kleines Spiel mit 30 - 60 Sekunden Spielzeit. Ein Erlebnis, wo gut erkennbar ist, dass es funktioniert oder nicht.

Danach werden von der Baseline aus Dinge am Code kaputt gemacht. Die Aufgabe ist dann einfach: den ursprünglichen spielbaren Zustand wiederherstelllen. Die Eleganz liegt in der klaren Endbedingung: man erkennt relativ schnell, ob man fertig ist oder nicht - das Spiel funktioniert, und wenn nicht, ist man noch nicht fertig. Ich kann also einmal das Spiel attraktiv gestalten, es muss ja auch kein Spiel sein... die Möglichkeiten sind ja endlos ... und kann das immer wieder verwenden.

Die Erstellung von buggy Varianten geht extrem stell, meist braucht es dafür nur wenige Minuten, einmal abspeichern - fertig! Es kommt sofort eine brauchbare Aufgabe heraus, die für einige Minuten kognitive Aktivität sorgen. Der Umfang lässt sich direkt beeinflussen: je mehr Bugs, je subtiler die Bugs, umso anstrengender die Aufgabe natürlich. Ich kann sogar ganze Logik-Blöcke löschen - und bin dann an etwas dran, dass sehr nach an B/C herankommt, es ist halt umgedreht, der Zielzustand ist schon bekannt, und man versucht da zurückzukommen.

Man ist auch sehr flexibel. Es ist kein Problem, wenn Teile des Codes z.B. weniger interessant sind. Dann baut man da halt keine Bugs ein und legt so keinen Fokus drauf. Ich kann quasi wie eine Taschenlampe auf bestimmte Aspekte des Codes leuchten und für diese Bereich das Verständnis gezielt abfragen.

Mir gefällt auch, welche Art von kognitiver Aktivität notwendig ist: es ist ein Suchen, Scannen, Code lesen. Es ist viel mentale Arbeit, gar nicht so viel Tippen. Cleverness wird belohnt, ich habe ja selbst meist nur ganz wenige Sachen gelöst. Die Motivation ist auch in der Richtung gut, dass man ja mit was kaputten anfängt. Man erlebt, wie man den Code repariert und es besser wird. Weil der Code eh schon kaputt ist, ist das Risiko etwas zu ändern geringer.

Und weil die Baseline bekannt ist, gibt es auch immer ein Fallback: man schaut halt an, wie die Original-Datei aussieht. Hier brauche ich das Vertrauen, dass sich die Leute nicht selber bescheißen - in der Altergruppe der Studis ist das aber gegeben. Und sogar umgekehrt: es macht mehr Spaß, den Bug selber zu finden, als durch Diff mit der Baseline. Weil es ja auch spannend ist. Und noch eins: den Leuten soll auffallen, wie wenig sie sich Code eigentlich merken, wenn sie ihn nicht selber geschrieben haben. Und was es heißt, den Code in-und-auswendig zu kennen: Lösche irgendeine Zeile, ich finde sie schon und kann sie wiederherstellen.

Es ist eine solide Methode, um eine Basis an Verständnis zu schaffen, ergänzbar mit A)-Elemente, und C)-Spotlights wo ich z.B größere Teile lösche und Anleitungen bereitstelle und mit Bonusaufgaben im B)-Format für die Differenzierung.

Die Methode muss nicht perfekt funktionieren. Aber solange sie guten Wert liefert und bisschen Spaß macht, hat sie sich schon rentiert, weil sie so RESOURCENSCHONEND und FLEXIBEL ist. Ich kann mehr experimentieren, ich kann mehr iterieren, schneller wachsen. Und insgesamt entspannter unterrichten.
