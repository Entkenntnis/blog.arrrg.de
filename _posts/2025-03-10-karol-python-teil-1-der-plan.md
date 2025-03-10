---
title: 'Karol x Python - Teil 1: Der Plan'
layout: post
---

Es geht langsam los. Nach mehreren Anfragen werde ich mich dransetzen und den Python-Modus für Karol erweitern. Es wird ein größeres Unterfangen, worauf ich mich wirklich gespannt bin. Wer hat nicht Lust, seine Compiler-Bau-Skills wieder einmal auf die Probe zu stellen?

Im heutigen Post möchte ich meinen Plan festhalten. Wird sicherlich spannend am Ende zurückzuschauen und zu sehen, wie es am Ende wirklich gelaufen ist.

Meine Ideen sind jetzt nicht so spektakulär. Als erstes brauche ich eine gute Test-Infrastruktur. Der Java-Tester war ok, aber ausbaufähig. In Python möchte ich paar Sachen noch mehr integrieren. Die Eingabe soll aus einem Paar von Python-Programm und einer Quest bestehen, zum Beispiel aus der Aufgabengalerie. Das Programm wird kompiliert, ausgeführt und auf Korrektheit geprüft. Diverse Parameter können zusätzlich geprüft werden, wie Profi-Modus oder nicht, ob eine Fehlermeldung erwartet wird und welche. Außerdem kann der konvertierte Robot Karol Code auch ausgeführt und geprüft werden.

Beim Nachdenken fällt mir auf: wäre wahrscheinlich gut, auch eigene Quests dafür anzulegen, denn ich werde ja neue Sprachfeatures nutzen und diese brauchen dann auch spezielle Aufgaben. Das heißt mit meiner Test-Infrastruktur baue ich auch eine Dokumentation/Anleitung. Spannend.

Das wird der erste Schritt sein. Ich arbeite erstmal mit meinen vorhandenen Compiler und stelle sicher, dass in der Test-Infrastruktur alles klappt. Sobald das der Fall ist, werde ich im zweiten Schritt den Compiler schreiben.

Hier wiederum ist der erste Schritt zu schauen, ob ich nicht neue Elemente in der VM brauche. Was mir in den Sinn kommt ist die Frage: Wie handhabe ich den Heap? Im Gegensatz zu Robot Karol wird die Sprache stärker auf Datenflüsse fokussiert sein. Eine einfache Art, mit verschiedenen Datentypen innerhalb der VM umgehen zu können und externe Funktionsaufrufe wären eine sinnvolle Abstraktion. Ich würde mir das vor der Implementation überlegen, weil das doch wichtige Entscheidungen sind, die auch auf notwendige Datenabhängigkeiten innerhalb des Compilers hindeuten.

So, im dritten Schritt kann ich nun den Compiler neu schreiben und den vorhandenen Funktionsumfang re-implementieren. Das ist aber auch ziemlich weit in der Zukunft. Ich glaube es gibt einiges an Potenzial, wenn ich den Compiler ein ganz kleines bisschen abstrakter baue. Nichts gegen den Robot Karol Compiler, aber dieser ist doch sehr ad-hoc hingeschustert. Eine klarere Trennung würde tatsächlich helfen. Macht aber auch das Schreiben der Fehlermeldungen vielleicht etwas schwieriger? Ich möchte auf jeden Fall bei Kontrollstrukturen und Bedingungen wirklich Daten und externe Funktionen nutzen und diese nicht in den Compiler hard-coden.

Im vierten Schritt, nach all der Vorbereitungsarbeit, kann ich nun endlich die neuen Funktionen einführen, wie Variablen, mathematische Operatoren, logische Operatoren. Je nach dem, wie die ersten drei Stufen laufen, werde ich hier ein klareres Bild haben, in welcher Reihenfolge ich diese bauen möchte.

Mit der Test-Infrastruktur wird dieser Schritt dann hoffentlich sowohl entspannter als auch produktiver sein. Ich glaube auch, leichter neue Architekturen und Strukturen im Compiler testen zu können, alles in allem mit kürzeren Test-Zeiten und mehr Iterationen. Das heißt auch mehr Spaß und weniger Frust.

Joah, soweit der Plan. Ich plane mental alle Schritte schon mal ganz grob im Kopf, um nach Abhängigkeiten und Fallstricken Ausschau zu halten. Aber bald sollte es auch mit den ersten Commits losgehen können.
