---
title: 'Karol x Python - Teil 2: Plot Twist und Pyodide'
layout: post
---

Anfang der Woche habe ich mir einen Plan zurechtgelegt. Davon ist jetzt fast nichts mehr übrig, haha. Ich habe meine Ideen am Dienstag ein paar SchülerInnen vorgestellt und es kam die berechtigte Frage auf, warum ich nicht einen existierenden Python-Interpreter nutze. Gute Frage. Warum nicht? Weil ich mit der JavaVM relativ schlechte Erfahrungen gemacht habe was Performance und Usability anging. Und weil ich Sorgen hatte, dass Funktionen wie Debugging nicht unterstützt werden.

Aber man darf sich nicht von Vorurteilen leiten lassen. Also habe ich mir einen Moment Zeit genommen und die Welt der Web-Python-Interpreter angeschaut. Das erste Ergebnis war PyScript, aber nach genaueren Hinschauen stellte sich das nur als Wrapper um Pyodide heraus mit weniger Flexibilität. Also schaute ich mir Pyodide an und damn, ich war schnell überzeugt.

Erstmal ist es sehr hilfreich, dass Python interpretiert wird. Dadurch muss man den Code nicht kompilieren und kann ihn einfach dem Interpreter hinschmeißen. Ladezeiten und Performance sind passable, es braucht natürlich einen Download von ungefähr 10MB, aber das ist ein akzeptabler Aufwand, es braucht keine weirden Caching-Mechanismen. Debuggen ist grundsätzlich möglich, was mich auch beruhigt hat.

Pläne dürfen sich also ändern. Nach wenigen Stunden habe ich mich dann entschieden, diesen Ansatz zu verfolgen. Und Stand heute habe ich die Grundfunktionen bereits implementiert. Auf eine Test-Infrastruktur konnte ich verzichten, denn die schwierigen Aufgaben übernimmt ja jetzt Pyodide.

Auf dem Weg habe ich einige Sachen über web worker gelernt. Diese sind für mich jetzt weniger beängstigend und ziemlich zuverlässig. Zwischendrin hatte ich einen kleinen Heisenbug mit lokal vs globalen Variablen, ich hoffe dieser Poltergeist lässt sich ausräuchern.

Das Integrieren und Wiederverwenden von existierenden Code fühlt sich so gut an. Ich kann mich viel mehr auf das Produkt konzentrieren und habe gleichzeitig den vollständigen Python-Compiler zur Verfügung. Ich habe ein kleines Beispiel mit `random.randint()` gebaut und es funktioniert und eröffnet einen neuen Horizont. Was ist noch alles mit Robot Karol möglich?

Die Brücke zwischen asynchronen JavaScript und synchronen Python ist stellenweise etwas schwierig. Ich komme nicht drum herum, mich mit cross-origin-isolation (habe ich aktiviert) und SharedArrayBuffer auseinanderzusetzen.

Ich habe auch gerade nochmal andere Web-Optionen angeschaut, wie z.B. Skulpt. Ich bin Stand heute mit Pyodide zufrieden. Es ist ein einfaches und starkes Interface. Ich kann davon ausgehen, dass Pyodide in der Zukunft leichter mit Python mithalten kann. Und ich habe eine coole Community, die ähnliche Probleme wie ich schon gelöst hat und ich ein wenig mitschwimmen kann.

Damit sind jetzt die einfachen 80% fertig. Ab jetzt kommen die technisch anspruchsvolleren 20%. Wird schon. Bisher ging ja auch alles ziemlich gut. In 1 - 2 Wochen sollte die Python-Integration öffentlich verfügbar sein.
