---
title: 'HTW Reflektionen 1'
layout: post
---

I dunno, ich habe das Gefühl, dass ich viele Gedanken habe zu HTW und einen Ort brauche, sie regelmäßig zu reflektieren. Auch, weil ich eine für mich massive neue Funktion eingebaut habe: A/B-Tests. Ich muss sagen, ich habe das schon ziemlich oft probiert, aber das ist das erste Mal, wo ich wirklich zum Zug komme.

Das Setup ist relativ simple: NutzerInnen werden zufällig in Gruppen eingeteilt und erhalten entweder die normale Inhaltsversion oder eine experimentelle Version. Es gibt so viele Dinge, die ich testen kann, von Auswirkungen des Titels, zu inhaltlichen Änderungen, größeren Aufgabenänderungen, eigentlich alles.

Dieses Alles ist aber auch ein Problem: ich kann so viel ausprobieren. Es gibt so viele Dinge, an denen ich schrauben kann. Bisher habe ich eher auf mein Bauchgefühl gehört oder mit groben Kohorten-Daten gearbeitet. Das ist nicht sehr zuverlässig, wie man im letzten Blog-Post nachlesen kann.

Wenn ich auf die letzten Jahre schaue, habe ich eigentlich nie so _wirklich_ konsequent mit Daten gearbeitet. Klar, ich habe meine jährlichen Raten verglichen, das ist ganz nett als Gesamtindikator, aber das ist nicht so sehr von mir beeinflusst. Die Lösungsraten waren schon immer gute Hinweise, aber diese habe wie geschrieben nur kohortenweise ausgewertet, was mal funktioniert, mal nicht. Es hinterlässt immer so ein Gefühl der Unsicherheit. Und ich fühle, dass ich nicht wachse und vorankomme, wenn ich nicht genauer hinschauen kann.

Stand jetzt sind 4 Experimente am Laufen. Das erste Experiment ist ein A/A-Test um mein Test-Instrument zu validieren. Daten sehen gut aus, Zahlen schwanken leicht, sind aber weit weg davon, signifikant zu sein. Wenn ich die Theorie richtig verstehe, sollte der A/A-Test in keinem Fall, auch bei sehr vielen Daten, nicht zu einem signifikanten Ergebnis führen. Hoffentlich hält das auch so. Die Randomizierung ist jetzt bisschen wird, ich habe im Code noch einen Bug gefunden und werde die Tests nochmal zurücksetzen ... aber man macht Fehler und ich lerne dazu.

Mein zweites Experiment ist eine Mini-Änderung, ein Satz gestrichen, eine so kleine Änderung wie man es sich nur vorstellen kann. Keine messbaren Unterschiede hier erstmal. Aber wie gesagt, alles noch recht früh und ich sollte die Daten nicht zu früh bewerten. Ich muss mich eh noch damit zurückfinden, keine statistischen Fehler zu machen (auch wenn sich das fast nicht vermeiden lässt, wie ich finde, z.B. habe ich auch keine ordentliche Power-Analyse gemacht oder so ...)

Das dritte Experiment ist nochmal interessanter, nämlich die Auswirkung des Titels. Und das scheint massiv zu sein, Booyah! scheint dann doch zu obkure zu sein, ein Wechsel auf Agent schafft einen CTR-Uplift von 93%. Auch die Lösungsrate der Aufgabe selber steigert sich, was nochmal überraschender ist, weil ich die Aufgabe selber gar nicht geändert habe. Wahnsinn, wie viel Unterschied alleine der Titel ausmacht!!!

Auch im vierten Experiment macht der Titel einen Unterschied, wobei ich auch die Aufgabe dahinter geändert habe. Das fühlt sich wie ein Fehler an, denn das sind wieder zu viele Änderungen auf einmal, die inhaltlichen Änderungen lassen sich damit ja kaum von den Titel-Änderungen trennen. Vielleicht poliere ich das nochmal ein bisschen.
