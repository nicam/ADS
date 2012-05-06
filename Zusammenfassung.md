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
Probleme von einfach verketeten Listen
Zugang zum Listenende kostete viel Zeit
Man kann sich nur effizient in eine Richtung bewegen

Doppelt verkette Listen
ListNode next, prev
Jeder Knoten hat zwei Referenzen next und previous
Add bei doppelt verketten Listen
###Add()
<img src="verkettet2_add.png">

	newNode.next = current;	newNode.prev = current.prev;	current.prev.next = newNode;	current.prev = newNode;
###Remove()

<img src="verkettet2_remove.png">
	
	current.prev.next = current.next;
	current.next.prev = current.prev;
	current = current.next;

### Zirkular verkettete Liste
- Next des letzten zeigt auf head (erstes)
- Previous des ersten zeigt auf tail (letztes)
- Effekt: Einziger spezialfall ist eine elere Liste

### Sortierte Listen
- Verwenden Comparator um bei Insert das Objekt an der richtigen Stelle einzufügen

###Liste Sortieren
Sofern das Listenobjekt Comparable implementiert, kann mit dieser Methode die Liste sortiert werden.

	Collections.sort(List list);
Folgende Objekte implementieren bereits Comparable:

Byte, Character, Double, File, Float, Long, ObjectStreamField, Short, String, Integer, BigInteger, BigDecimal, Date

Alternativ kann auch mittels eines Comparators verglichen werden. Der Comparator implementiert das Comaprator interface.

	Collections.sort(List list, Comparator comp);

###Array VS Liste
####Array

(+) Benutzung sehr einfach<br>
(+) direkter Zugriff a[5] sehr effizient<br>
(-) Grösse muss vor erstellen bekannt sein<br>

####Liste
(-) Schwieriger in der Benutzung<br>
(-) nur Referenztypen können in Listen verwaltet werden<br>
(-) Indizierter Zugriff ineffizient list.get(i)<br>
(+) Anzahl Elemente muss nicht bekannt sein<br>
(+) Anfügen, ersetzten, vertauschen und Einfügen und Löschen sehr effizient

### Array implementation der Liste (ArrayList)

**LinkedList** 
- schneller für Mutationen, langsam bei direktem Zugriff- non-synchronized Aufrufe

**ArrayList**
- Implementation als Array	- direkter Zugriff schnell
	- Mutationen (einfügen, löschen) langsam- non-synchronized Aufrufe

##Sets
Definition: eine ungeordnete Menge ohne Duplikate

###Implementation durch
- Hashset bei grossen Datenbeständen (etwas) effizienter- TreeSet speichert die Elemente in alphabetischer (geordneter) Folge

Code implementation

	Set stooges = new HashSet();
	stooges.add("Larry"); 
	stooges.add("Moe");
	stooges.add("Curly");
	stooges.add("Moe"); // Duplicate wont be added
	stooges.add("Shemp"); 
	stooges.add("Moe"); // Duplicate wont be added
	System.out.println(stooges);

###Vergleiche von 2 Sets (A und B)
<img src="set_comparison.png" width="70%">


##Collection Interface
Gemeinsames Interface für Sammlungen (Collections) von Objekten - Ausnahme Array - leider.

Statische Funktionen die über **Collections.METHODNAME** aufgerufen werden können

<img src="collection_methods.png" width="75%">

Collections.unmodifiableList gibt die Unmodifizierbare Liste (ReadOnly zurück)<br>
Collections.synchronizedList() gibt die ThreadSafe Liste zurück.

Per Default sind alle Collection Klassen Thread Unsafe



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