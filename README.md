Quelltext verschiedener Andor-Projekte von Butterbrotbär. Mehr Informationen, den aktuellen Stand und vorherige Versionen findet ihr auf https://butterbrotbaer.github.io



# Kompilation 

Um eines dieser Projekte selbst zu kompilieren, benötigst Du:

– Wenn Du es lokal auf einem Computer kompilieren lassen willst:
1. Eine Kopie des Quelltexts (https://butterbrotbaer.github.io)
2. Eine LaTeX-Distribution wie TeX Live (https://www.tug.org/texlive)
3. Einen lokalen LaTeX-Editor wie VS Code (https://code.visualstudio.com) mit der LaTeX Workshop Extension

– Wenn Du es online über einen Browser kompilieren lassen willst:
1. Eine Kopie des Quelltexts (https://butterbrotbaer.github.io)
2. Einen Online-LaTeX-Editor wie Overleaf (https://www.overleaf.com)

Anschließend kannst Du das erhaltene PDF komprimieren. Das geht mit einem Programm wie pdf24 (https://www.pdf24.org)

Wenn Du zwischen verschiedenen Compilern auswählen kannst, wähle LuaLaTeX.



# Copyright

Diese Projekte enthalten urheberrechtlich geschütztes Material von den offiziellen Internetauftritten der Marke "Die Legenden von Andor" des KOSMOS Verlags. Ich (Butterbrotbär) wandte mich an Michael Menzel und erhielt die Erlaubnis, dieses Material in dieser Form nicht-kommerziell zu teilen. Alle anderen Rechte bleiben jedoch vorbehalten. Diese Projekte sind Fan-Werke und werden nicht offiziell unterstützt.



# Notizen für Releases

Man kann die verschiedenen Branches auflisten:

```
git branch
```

Committe Updates an einem Projekt jeweils im entsprechenden Projekt-Branch.

Mache neue Releases gemäß folgender Prozedur:

1. Merge den Haupt-Branch (sicherheitshalber nochmals gesynct) in den Projekt-Branch:

```
git checkout main
git pull
git push
git checkout wiedasprojektheisst
git pull
git merge main --no-ff
```

2. Mache den Projekt-Branch bereit für den Release, indem du die Änderung der `????` zu richtigen Zeit- und Versionsangaben sowie die richtige `export-ignore` Kommentierung in `.gitattributes` (nur dieser Projekt-Branch kommentiert) committest und pushst.

3. Prüfe auf GitHub, dass ein zip-Download aus dem Projekt-Branch den richtigen Quellcode herunterlädt. Kompiliere das PDF. Prüfe, dass im PDF die richtigen Zeit- und Versionsangaben stehen. Komprimiere das PDF. Exportiere, falls neu, das Cover in 1000x1414.

4. Veröffentliche in der Taverne einen neuen Beitrag zum Release. Ergänze die Links im Eingangsbeitrag des Threads.

5. Bereite auf GitHub den neuen Release vor. Mache dafür im Projekt-Branch einen neuen Tag. Verlinke den Tavernenbeitrag in der Beschreibung. Hänge das komprimierte PDF mit dem richtigen Titel an. Veröffentliche den Release. Überprüfe, dass die Download-Links im neuen Tavernenbeitrag und im Tavernenthread-Eingangsbeitrag funktionieren.

6. Merge den Projekt-Branch (sicherheitshalber nochmals gesynct) in den Haupt-Branch:

```
git checkout wiedasprojektheisst
git pull 
git push
git checkout main
git pull
git merge wiedasprojektheisst --no-ff
```

7. Passe den Haupt-Branch wieder an, indem du die richtige `export-ignore` Kommentierung in `.gitattributes` (alles kommentiert) committest und pushst. 

8. Passe den Projekt-Branch wieder an, indem du ihn outcheckst und pullst sowie danach die Änderung der Zeit- und Versionsangaben zu `????` committest und pushst.

9. Ergänze das komprimierte PDF, ein etwaiges neues Cover und die neuen Links auf der GitHub Page ( https://butterbrotbaer.github.io ). Prüfe, dass die Download-Links und die pdfjs-Anzeige funktionieren und das richtige PDF zeigen.

