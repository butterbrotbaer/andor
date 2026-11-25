Quelltext verschiedener Andor-Projekte von Butterbrotbär. Mehr Informationen, den aktuellen Stand und vorherige Versionen findet ihr auf https://butterbrotbaer.github.io



# Kompilieren 

Um eines dieser Projekte selbst zu kompilieren, benötigst Du:

– Wenn Du es lokal auf einem Computer kompilieren willst:
1. Eine Kopie des Quelltexts (https://butterbrotbaer.github.io)
2. Eine LaTeX-Distribution wie TeX Live (https://www.tug.org/texlive)
3. Einen lokalen LaTeX-Editor wie VS Code (https://code.visualstudio.com) mit der LaTeX Workshop Extension

– Wenn Du es online über einen Browser kompilieren willst:
1. Eine Kopie des Quelltexts (https://butterbrotbaer.github.io)
2. Einen Online-LaTeX-Editor wie Overleaf (https://www.overleaf.com)

Anschließend kannst Du das erhaltene PDF komprimieren. Das geht mit einem Programm wie pdf24 (https://www.pdf24.org).

Wenn Du zwischen verschiedenen Compilern auswählen kannst, wähle LuaLaTeX.



# Copyright

Diese Projekte enthalten urheberrechtlich geschütztes Material von den offiziellen Internetauftritten der Marke "Die Legenden von Andor" des KOSMOS Verlags. Ich (Butterbrotbär) wandte mich an Michael Menzel und erhielt die Erlaubnis, dieses Material in dieser Form nicht-kommerziell zu teilen. Alle anderen Rechte bleiben jedoch vorbehalten. Diese Projekte sind Fan-Werke und werden nicht offiziell unterstützt.



# Releases (Notizen an mich selbst)

Man kann die verschiedenen Branches auflisten:

```
git branch
```

Committe Updates an einem Projekt jeweils im entsprechenden Projekt-Branch.

Mache neue Releases gemäß folgender Prozedur:

1. **Update im entsprechenden Projekt-Branch die Quelltexte der anderen Projekte:** Merge den Haupt-Branch (sicherheitshalber nochmals gesynct) in den Projekt-Branch:

```
git checkout main
git pull
git push
git checkout wiedasprojektheisst
git pull
git merge main --no-ff
```

2. **Mache den Projekt-Branch bereit für den Release:** *Nur CdA: Prüfe die Links in "Andor im Netz" und setze veraltete auf "ehemals".* Committe und pushe die Änderung der `????` zu richtigen Zeit- und Versionsangaben sowie die richtige `export-ignore` Kommentierung in `.gitattributes` (nur dieser Projekt-Branch kommentiert). Prüfe auf GitHub, dass ein zip-Download aus dem Projekt-Branch den richtigen Quelltext herunterlädt.

3. **Mache alle Dateien bereit für den Release:** Kompiliere das PDF. Prüfe, dass im PDF die richtigen Zeit- und Versionsangaben stehen. Komprimiere das PDF. Exportiere, falls neu, das Cover in 1000x1414. *Nur EdW: Konvertiere das plain-PDF ohne* `\puxif` *in eine EPUB-Datei für den Release (z.B. mit Calibre: Bücher konvertieren > Zielformat EPUB > Erscheinungsbild > Layout > Einzugsgröße 2.5em und "Abstand zwischen Absätzen entfernen" > OK) und konvertiere das plain-PDF samt* `\puxif` *in eine TXT-Datei für die GitHub Page (z.B. mit Calibre: Bücher konvertieren > Zielformat TXT > Erscheinungsbild > Layout > nicht "Abstand zwischen Absätzen entfernen" > OK).*

4. **Mache die Taverne bereit für den Release:** Schreibe und veröffentliche in der Taverne einen neuen Beitrag zum Release. Ergänze die Links im Eingangsbeitrag des Threads.

5. **Mache den Release:** Mache im Projekt-Branch einen neuen Tag. Drafte den neuen Release auf GitHub. Verlinke den Tavernenbeitrag in der Beschreibung. Hänge das komprimierte PDF mit dem richtigen Titel an. *Nur EdW: Hänge die EPUB-Datei ohne* `\puxif` *mit dem richtigen Titel an.* Veröffentliche den Release. Überprüfe, dass die Download-Links im neuen Tavernenbeitrag und im Tavernenthread-Eingangsbeitrag funktionieren.

6. **Update den Quelltext dieses Projekts im Haupt-Branch:** Merge den Projekt-Branch (sicherheitshalber nochmals gesynct) in den Haupt-Branch:

```
git checkout wiedasprojektheisst
git pull 
git push
git checkout main
git pull
git merge wiedasprojektheisst --no-ff
```

7. **Korrigiere den Haupt-Branch:** Committe und pushe die richtige `export-ignore` Kommentierung in `.gitattributes` (alles kommentiert).

8. **Korrigiere den Projekt-Branch:** Checke den Projekt-Branch aus. Committe und pushe die Änderung der Zeit- und Versionsangaben zu `????`.

9. **Mache die GitHub Page bereit für den Release:** Ergänze das komprimierte PDF, ein etwaiges neues Cover und die neuen Links auf der GitHub Page ( https://butterbrotbaer.github.io ). *Nur EdW: Update die plain-TXT-Datei samt* `\puxif`. *Prüfe, dass die Download-Links und die pdfjs-Anzeigen funktionieren und das richtige PDF zeigen. Committe und pushe. Prüfe erneut, dass die Links und Anzeigen funktionieren.

10. **Führe Projekt-spezifische Schritte aus:** *Nur EdW: Mache ein Pu'Xif Update. Ergänze etwaige neue Fan-Geschichten an anderen Orten. Falls es mal wieder an der Zeit ist, Fan-Geschichten an anderen Orten auf den neusten Stand zu bringen, kompiliere ein plain-PDF ohne* `\puxif` *und konvertiere es in eine TXT-Datei (z.B. mit Calibre: Bücher konvertieren > Zielformat TXT > Erscheinungsbild > Layout > nicht "Abstand zwischen Absätzen entfernen" > OK). Kopiere die Kapitel daraus an den anderen Ort.*

