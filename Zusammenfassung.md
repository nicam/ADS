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

	newNode.next = current;
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


**ArrayList**

	- Mutationen (einfügen, löschen) langsam

##Sets
Definition: eine ungeordnete Menge ohne Duplikate

###Implementation durch
- Hashset bei grossen Datenbeständen (etwas) effizienter

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

￼￼￼￼

#Generics

Defintion:
Einen Algorithmus, der auf Werte von unterschiedlichen Datentypen angewandt werden kann, nennt man generisch.

	List<Integer> list = new LinkedList<Integer>();
	list.add(new Object()); --> Compile Error
##Generic Klasse
	class LinkedList<T> {
	    public LinkedList(T item) {
	      // Code
	    }
	
	    public LinkedList(T[] items) {
		  // Code
	    }
	
	    public T getFirst() {
	  	  // Code
	    }
	}

##Extends

	public void drawAll(List<? extends Figure> figures) {
##Oberklasse festlegen

	public void addRectangle (List<? super Rectangle> shapes) {
##Bounded Wildcards
	
	public static <T, S extends T> void copy(List<T> est, List<S> src) {

##Wildcards bei Rückgabe
	
	public List<? extends Number> getValueList () { }
##Erasures
Zur laufzeit werden die Typeninformationen vollständig entfernt. Aus Box<T> wird Box<Object>.
Keine Typenprüfung möglich if (e instanceof List<LinkedList>).
Beim Ablauf des Programms kann nicht mehr von z.B. LinkedList<String> und LinkedList<Integer> unterschieden werden.

#Rekursion
##Definition
Ein Algorithmus/Datenstruktur heisst rekursiv definiert, wenn er/sie sich selbst als Teil enthält oder mit Hilfe von sich selbst definiert ist.
###Direkt / indirekt
Bei der direkten Rekursion ruft sich eine Methode selbst wieder auf, bei der indirekten Rufen sich 2 Methoden gegenseitig auf (ungewollt).

###Iterativ vs Rekursiv

####Iterativ
	int anzahlSchritte() {
		int anzahl = 0;
		}
####Rekursiv
	int anzahlSchritteR() {
		if (vorn_frei()) {
		} else
		}		
	}
###Zusammenfassung
- Zu jedem rekursiven Algorithmus gibt es einen äquivalenten iterativen Algorithmus
- (+) kürzere Formulierung
- (+) Einsparung von Variablen
- (+) Teilweise sehr effiziente Problemlösung (Quicksort)
- (-) weniger effizientes Laufzeitverhalten (overhead beim Methodenaufruf)
- (-) gewöhnungsbedürftig

#Bäume
##Begriffe
<img src="terminologie_tree.png" width="90%">

- Die Tiefe eines Baumes gibt an, wie weit die "tiefsten" Blätter von der Wurzel entfernt sind: Anzahl Kanten + 1
- Das Gewicht ist die Anzahl der Knoten des (Teil-) Baumes

##Binärbäume
Die am häufigsten verwendete Art von Bäumen: beim Binärbaum hat ein Knoten maximal 2 Nachfolger



###Berechnung der nötigen Tiefe:
ln(10)/ln(2) (Aufrunden)
Maximale Anzahl
(2^k)-1 (k = tiefe)

###Traversieren

####Klassen zur Traversierung
<img src="traversal_klasses.png" width="90%">

####Preorder (Oben nach Unten, Tiefensuche)
- Besuche die Wurzel
- Traversiere Links
- Traversiere Rechts

Code

	private void preorder(TreeNode<T> node, Visitor<T> visitor) { if (node != null) {
		visitor.visit(node.element);
		preorder(node.left,visitor);
		preorder(node.right,visitor);
	}

####Postorder (Unten nach Oben)
- Traversiere den linken Teilbaum (in Postorder)
- Traversiere den rechten Teilbaum (in Postorder).
- Besuche die Wurzel

Code

    private void postorder(TreeNode<T> node, Visitor<T> visitor) {
        if (node != null) {
            postorder(node.left,visitor); 
            postorder(node.right,visitor); 
            visitor.visit(node.element);
        }
    }



####Inorder (Links nach rechts)

- Traversiere den linken Teilbaum (in Inorder)
- Besuche die Wurzel
- Traversiere den rechten Teilbaum (in Inorder)

Code

    private void inorder(TreeNode<T> node, Visitor<T> visitor) {
        if (node != null) {
            inorder(node.left,visitor); 
            visitor.visit(node.element);
            inorder(node.right,visitor); 
        }
    }

####Levelorder (Breitensuche)
Beginnend bei der Baumwurzel werden die Ebenen von links nach rechts durchlaufen

- zuerst die Wurzel
- dann die Wurzel des Linken und rechten Teilbaumes
- dann die nächste Schicht

###Sortierte Bäume
- im linken Unterbaum sind alle kleineren Elemente KL <=* k 
- im rechten Unterbaum sind alle grösseren Elemente: KR >* k

####Einfügen
Beim Einfügen muss links eingefügt werden, wenn das neue Element kleiner oder gleich ist, sonst rechts (rekursiv)

####Löschen
<img src="tree_delete.png" width="50%">

- der Knoten hat keinen Teilbaum
	- Knoten löschen 
- der Knoten hat einen Teilbaum
	- Vater des zu löschenden an Kind des zu löschenden hängen 
	- Vom linken Teilbaum wird das Element ganz rechts als Ersatz genommen
	- Dann gilt immer noch die Bedingung KL <=k und KR > k


#Sortiere Bäume / Suchen

#Graphen / Topologien

#Backtracking

#Algorithmen Aufwand

#Suchen / Hashing

#Sortieren 1

#Soriteren 2

#Speicherverwaltung

#Parsing