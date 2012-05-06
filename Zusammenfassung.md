#Allgemein
##Algorithmus
Eine Anleitung zur Lösung einer Aufgabenstellung, die so präzise Formuliert ist, dass sie mechanisch ausgeführt werden kann.

###Determiniertheit
Identische Einfgaben führen stetes zu identischen Ergebnissen

###Determinusmus
Ablauf des Verfahrens ist an jedem Punkt fest vorgeschrieben (keine Wahlfreiheit)


###Terminierung
Für jede Eingabe liegt Ergenis nach endlich vielen Schritten vor.

###Effizient
Wirtschaftlichkeit des Aufwands relativ zu einem vorgegeben Massstab

##Korrektheit von Programmen
Ein Programm wird als korrekt bezeichnet, wenn unter der Annahme, dass die Vorbedingung erfüllt ist, unter Anwendung des Programms die Nachbedingung erfüllt wird.

Vorbedingung -> f(x) -> Nachbedingung

##Reference Types in Java
- Arrays
- alle Object abgeleiteten
- String
- Variablen sind nur Referenzen (Zeiger auf Objekte im Speicher)


#ADT / Stacks / Queues

ADT = Abstrakte Datentypen

##Stacks
- Speichert Objekte als Stapel
- **Push** legt neue Objekte oben auf den Stapel
- **Pop** gibt oberstes Objekt wieder zurück
- **LIFO** Last in first out Datenstrucktur

Anwendungszwecke

- Auswertung von Postfix Ausdrücken (HP)
- Test auf korrekte Klammersetzung
- XML Check

##Vererbung vs Delegation
**Vererbung**:	erbende Klase ist eine echte Erweiterung

**Delegation** andere Klasse wird ledigitlich verwendet, teile der Verarbeitung werden delegiert

##Queues
- Werden mit Listen oder Arrays implementiert
- FIFO (First in first out)
- enque
- deque
- Anwendungszwecke (Warteschlangen)

###PriortiyQueues
- Objekte hoher Priorität wandern nach vorne
- Objekte gleicher Priorität werden in derselben Reihenfolge entfernt wie sie eingefügt wurden.
- Anwendungszwecke: (Scheduling von Prozessen, Aufgabenliste nach Prioritäten)


#Listen
- Grundlegende Datenstrucktur
- java.util.List (Interface), java.util.LinkedList (implementation)
- Anwendungszwecke / Eigenschaften
	- Stack, Queue
	- Disk-Blöcke, Prozesse, Threads
	- Anzahl der Elemente zur ERstellungszeit offen
	- Reihenfolge, position ist relevant
- Funktioniert mit zeigern
	- Attribute der Nodes: next, data
	- LinkedList Attribut first
- Werden mit Iterator traversiert
	- ADT mit dem eine Datenstruktur traversiert werden kann, ohne dass die Datenstruktur bekannt gemacht werden muss
- Einfügen funktioniert durch umhängen der Zeiger next zwischen zwei Elementen
- Entfernen funktioniert auch durch umhängen der Zeiger a.next = a.next.next



##Doppelt verkettete Listen



#Generics

#Rekursion

#Bäume

#Sortiere Bäume / Suchen

#Graphen / Topologien

#Backtracking

#Algorithmen Aufwand

#Suchen / Hashing

#Sortieren 1

#Soriteren 2

#Speicherverwaltung

#Parsing