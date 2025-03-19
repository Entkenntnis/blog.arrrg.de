---
title: 'Karol x Python - Teil 3: Eine Uhr, die stehen bleibt'
layout: post
---

Es ging dann doch schneller als gedacht, der Python Pro Modus ist online, zumindest in der ersten Fassung. Ich bin dabei, spannende Ideen zu sammeln und diese in der Beispiel-Galerie einzubauen. Wie [eine Uhr](https://karol.arrrg.de/#SKM3).

Ich habe die Uhr heute parallel auf meinem Laptop-Bildschirm laufen lassen. Es war ein wildes Gefühl, es fühlt sich fast an, wie eine Person, die mit mir zusammen ist und jede Minute die Zeit aktualisiert. Den ganzen Vormittag lief alles super, dann ging ich in ein Arbeits-Meeting. Und dann passierte etwas sehr seltsames: Die Uhr blieb einfach stehen.

Und man konnte auch genau sehen, zu welchem Zeitpunkt sie stehen blieb. Ich startete sie neu - und dann blieb sie wieder stehen. Was hat sich verändert? Ja, das Meeting! Das Script bleibt hängen, wenn ich in einem anderen Tab ein Meeting laufen habe.

Von solchen Fälle erfährt man als Kuriosität, ich hätte nicht gedacht, das ich sowas bei mir selbst erlebe. Ich probiere es später nochmal aus, und tatsächlich, sobald ich ein Meeting starte, bleibt die Uhr stehen. Hierbei muss es sich um eine Race-Condition handeln.

Und es gibt auch eine sehr offensichtliche Stelle, wo es passiert. Ich werde hier etwas technisch, wem das nicht interessiert, kann ja diesen Teil überspringen. Das Python-Programm läuft in einem Web-Worker. Wenn ich die Karol-Welt mit einem Befehl wie `schritt()` verändere, ist das vergleichsweise einfach zu machen: Ich sende eine Nachricht an den Haupt-Thread und kann mit der Ausführung weitermachen. Aber was ist mit Bedingungen wie `istWand()`? Hier muss ich auf eine Antwort vom Haupt-Thread warten, bevor ich weitermachen kann.

Gleichzeitig darf ich den Funktions-Kontext nicht verlassen. Meine Strategie bestand also darin, einen gemeinsamen Speicher (`SharedArrayBuffer`) zu verwenden, worin der Haupt-Thread seine Antwort schreiben kann. Ich schicke die Nachricht und warte mit `Atomics.wait()` auf ein Signal. Nur: wenn der Browser stark ausgelastet ist, wie in mit einem Meeting, dann kann es passieren, dass der Haupt-Thread das Signal bereits gesendet hat wenn ich zu warten anfange. Dadurch hängt sich der Web-Worker auf und die Uhr bleibt stehen.

Ich habe den Code für längere Zeit angestarrt, bis ich eine Lösung finden konnte. Ich wollte nicht mit IDs oder sonstigen komplexen Dingen arbeiten. Es musste doch eine eine einfache Lösung geben? Ja, diese gibt es. Und zwar hat `Atomics.wait()` einen dritten Parameter, der wohl genau für meinen Fall gedacht ist. Dieser Parameter gibt an, was der erwartete Wert ist am Anfang des Wartens. Bevor ist die Nachricht sende, setze ich den Buffer auf den Platzhalter-Wert 42. Die Antwort vom Haupt-Thread ist 0 oder 1. Wenn der Wert beim Start des Wartens 42 ist, dann kommt noch das Signal. Ist aber der Wert nicht 42, dann weiß ich, dass ich das Signal verpasst habe. Das macht aber nichts! Das ist ja gut, ich kann in diesem Fall einfach weitermachen. Und so ist auch das Verhalten von `Atomics.wait()` definiert.

Eine kleine Code-Änderung später und die Uhr läuft - auch mit mehreren parallel laufenden Meetings. Dass ich mich in Javascript mal mit nebenläufiger Programmierung beschäftigen würde, hätte ich eigentlich nicht gedacht. Aber es war eine spannende Suche und eine befriedigend einfache Lösung.

Von der reinen Funktionalität her bin ich mit dem Python Pro Modus mittlerweile ganz zufrieden. Beim Programming-Support gibt es aber noch Potenzial, wie z.B. ein sinnvolles Auto-Complete/Language-Server, bessere Fehlermeldungen, vielleicht, ganz vielleicht sogar einen Debugger.

Ich merke auch, wie die neue Art zu programmieren auch bestimmte Annahmen in der UX in Frage stellen. Der Splitter sollte sich beim Resize vielleicht nicht resetten. Die Spielwiese entwickelt sich immer mehr zur eigentlichen IDE und könnte auch ein Teilen-Feature gut vertragen.

Es hat 1,5 Wochen gedauert und ich habe den Python-Modus jetzt in Production. Hurray. Das ging ziemlich gut. Eine erste Iteration live zu haben ist so ein gutes Gefühl. Es gibt mir die Freiheit die nächsten Tasks anzugehen und schafft Kapazitäten in meinem Kopf.
