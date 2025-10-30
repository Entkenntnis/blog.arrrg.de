---
title: 'HTW Reflektionen 3'
layout: post
---

"Wir sind Hacker. Und wenn es Probleme gibt, die unsere Hacker Skills benötigen, dann sind wir zur Stelle."

Dieser Satz ist mir heute gekommen als Motto für Hack The Web und als Antwort auf die Frage, was Hacking eigentlich ist und welche Art von Definition uns gut tut. Ich hatte immer so das Problem, dass Systeme wie CTFs oder cyber-\* vor allem über den Inhalt arbeitet und auf Leistung fokussiert sind, was vielleicht den menschlichen Aspekt aus den Augen verliert. Ich meine, es geht darum, dass ich meine Skills einsetzen möchte - das ist das ultimative Ziel. Und meine Skills sind nicht unendlich und ich kann auch nicht ständig wachsen und es wäre schon gut wenn es regelmäßig Gelegenheiten gibt, meine Hacking Skills einzusetzen ... hier ist noch viel Futter zum Nachdenken.

Nebenbei bin ich am Überlegen, ob eine Art Random Challenge Maker lustig wäre. Ich habe noch einige neue Ideen, die sich damit vielleicht auch umsetzen lassen. Es ist viel Arbeit, es heißt aber auch dass ich viel Arbeit in einem konzentrieren Erlebnis verpacken kann, was wiederum ganz gut ist. Bin schon committed, die Frage ist eher wann und wie aufwändig in der ersten Version.

Es sind jetzt mehr als eine Woche vergangen seit dem Start der Experimente und die ersten stabilen Ergebnisse sind verfügbar. Der A/A-Test zeigt bei 600+ Einträgen ein sehr ausgewogenes Ergebnis, die Verteilung ist fast perfekt gleichmäßig ohne Unausgeglichenheiten in die eine oder andere Richtung. Damit weiß ich relativ sicher: mein Messsystem funktioniert und ist ausbalanciert. Ich kann den Daten erstmal vertrauen. Über den Zeitverlauf ist meine Einschätzung, dass bei 200 - 400 Samples ein guter Teil des Noise ausgefiltert sind, sicherlich wenn ich im Bereich 500+ bin. Ich brauche allerdings schon eher Richtung 1000 Samples, um auch kleine Untereschiede im Bereich von ~10% nachweisen zu können. Mehr als das werde ich wohl kaum brauchen denke ich.

Überraschend sind die Ergebnisse von Experiment 2, 636 Samples Stand jetzt, und ich habe einen Uplift von 8% für die CTR. Das ist irgendwie seltsam, weil ich ja nichts am Titel verändert habe. Die Lösungsrate für Leute, die auf die Aufgabe klicken, ist gleich geblieben. Wie kann es sein, dass sich eine Änderung am Inhalt sich darauf auswirkt, wie viele Leute auf die Aufgabe klicken?

Und hier spielt auch rein, dass dieser Uplift ein p = 0.03 hat und damit statistisch signifikant - das ist kein Zufall, sondern wirklich eine Folge meiner Änderung, die darin bestand, eine Zeile zu löschen. Ich habe also ein Ergebnis und darf es jetzt interpretieren.

Meine Vermutung: Es muss sein, dass die SpielerInnen, die die Trial-Version erhalten, eher bereit sind, die Aufgabe weiterzuempfehlen an ihre Sitznachbarn und dadurch einen Netzwerk-Effekt erzeugen. Der zusätzliche Satz ist tatsächlich signifikant genug, dass Leute die Aufgabe seltener ihren Freunden empfehlen. Crazy. Wenn das die Erklärung ist, dann kann ich mit diesem simplen Setup sogar Meta-Effekte messen und sichtbar machen. Haha, und ich dachte dass die CTR-Analyse langweilig wäre.

Die neue Aufgabenvariante beim Einhorn ist ein Flop, leider. Die Daten sind da ziemlich eindeutig. Mich wundert es, dass die Booyah!/Agent Änderung jetzt im zweiten Anlauf keinen Unterschied macht. Dass die neue Variante von Geburtstag keine Regression auslöst, ist gut. Manchmal sind Nicht-Ergebnisse auch gute Neuigkeiten.

Evtl. verlängere ich den Testzeitraum für die Experimente noch ein wenig, z.B. für Minecraft III (auch ziemlich minimale Änderung). Stört ja nicht, wenn ich das über einen Monat oder so laufen lasse, weil wenn die Effekte klein sind, brauche ich schon eine Weile, bis ich an die Daten rankomme.

Jup, es wird Zeit für die nächste Iteration an Ideen.
