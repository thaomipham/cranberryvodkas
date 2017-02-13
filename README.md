

<h1>
<a id="Übe">CranberryVodka</a>
</h1>

<h3>Inhaltsverzeichnis</h3>
<ul>
<li><a href="#Cod">Code.org®</a></li>
<li><a href="#App">App-Konzept</a></li>
<li><a href="#Ver">Versionen</a></li>
<li><a href="#Gra">Graphische Gestaltung</a></li>
<li><a href="#Pro">Programmierung</a></li>
<li><a href="#Fin">Finale App</a></li>
<li><a href="#Bug">Bugs</a></li>
</ul>


<h2>
<a id="Cod">Code.org®</a>
</h2>



<p>Code.org® ist eine non-profitable Organisation, die es sich zur Aufgabe gemacht hat, jedem Schüler die Möglichkeit zu geben, Informatik-Unterricht zu erhalten. Dies ist seit dem Start in 2013 durch Sponsoren wie Microsoft, Facebook, Google oder auch Einzelspendern ermöglicht worden.</p>


<p>Verwendet wird JavaScript, welches zur vereinfachten Darstellung in Blöcken angezeigt wird, wodurch angehende Programmierer, die nicht viel Erfahrung mit JavaScript oder Programmiersprachen im Allgemeinen haben, einfacher einen schnellen Überblick über die Funktion des Codes erhalten können, ohne sich mit lästigen Rechtschreibfehlern aufzuhalten.</p>

<p>Es gibt verschiedene Kurse, sowie das Studio Applab, welches ich benutzt habe, um eine App zu erstellen.</p>

<img src="pictures/3 options applab.png">

<p>Bei Applab gibt es 3 Bereiche in denen man arbeiten kann: Code, Design und Data.</p>

<p>Das eigentliche Programmieren findet im ersten Bereich, dem Code-Bereich statt. Im Design-Bereich kann man die graphische Oberfläche gestalten, im Data-Bereich kann man Datenbanken, bzw. Listen erstellen, auf die man beim Programmieren zurückgreifen kann. Im Design- und Code-Bereich ist links eine Vorschau des Smartphones eingebettet, in der man das Projekt gestalten und nachvollziehen kann.</p>

<a href="pictures/1.png" target="_blank">
<img src="pictures/1.png">
</a>

<h2>
<a id="App">App-Konzept</a>
</h2>


<p>Meine App wurde von der existierenden App <mark>"Picolo"</mark> inspiriert. Bei <mark>"Picolo"</mark> werden die Namen der jeweiligen Spieler eingefügt und personenbezogene Aufgaben werden erstellt.</p>

<p>Bei meiner App CranberryVodka gibt es <i>orders</i> und <i>drinks</i>. Die <i>orders</i> stehen für Befehle bzw. sind Texte, die den Spielern vorschreiben zu trinken/Schlücke zu verteilen, wenn bestimmte Bedingungen erfüllt wurden. Die <i>drinks</i> zeigen Rezepte zu beliebten, ausgewählten Cocktails, welche die Spieler machen können, um diese während des Spiels zu trinken.</p>


<h2>
<a id="Ver">Versionen®</a>
</h2>


<p>Abgesehen von dem späten Start des Projektes, gab es viele Hürden, die zu meistern waren. Es entstanden Probleme bei der Wiedergabe der orders und drinks, weswegen 2 verschiedene Ansätze beziehungsweise Versionen der App entstanden.</p>

<h3>
Version 1
</h3>


<p>Zuerst wurden screens mit den orders erstellt. Beim Klicken wird der User auf den nächsten screen geleitet, dies geschah in einer festgelegten Reihenfolge durch das manuelle Setzen der Bedingungen click, setscreen. Dadurch musste man, um eine neue order hinzuzufügen, einen neuen screen erstellen und manuell wieder ein event erstellen.</p>

<img src="pictures/2.png">

<h3>
Version 2
</h3>

<p>Zuerst wird eine Liste erstellt, die (in der Version 2) acht Werte enthält - <i>(drink1 - drink8) bzw. "orders"</i>. Eine Schleife, die sich wiederholt, solange die Variable <i>i</i> kleiner ist als die Anzahl an Einträgen in der Liste (acht). Innerhalb der Schleife wird <i>i</i> um jeweils einen erhöht. Außerdem gibt sie den <i>i</i>-ten Wert von <i>list</i> an die Funktion <i>setScreen</i> weiter. Wenn <i>i</i> einmal durchgelaufen ist (also größer als die Anzahl von Einträgen in <i>list</i>), wird <i>i</i> wieder gleich 0 gesetzt. </p>

<img src="pictures/3.png">
 
 
<h2>
<a id="Gra">Graphische Gestaltung</a>
</h2>
 
 <img src="pictures/design applab.png">
 
 <p>Die Weboberfläche von Applab in der man das Interface der App per Drag'n'Drop gestaltet. Den Buttons und Textfeldern kann man Eigenschaften und IDs vergeben.</p>
 
<h2>
<a id="Pro">Programmierung</a>
</h2>


<p>Über den Entwurf wurden die 5 screens “MAIN”, “GAME”, “DRINKS”,”DRINKPIC” und “NO” grundlegend gestaltet. Alle Buttons und andere Objekte, die permanent vorhanden sind, wurden hier erstellt. Außerdem greift das Programm auf zwei vordefinierte und durch den Nutzer unveränderbare Datenbanken zu. Die erste heißt “orders” und beinhaltet drei Spalten “ID”, “text” und “color”, die zweite heißt “drinks” und beinhaltet ebenfalls drei Spalten “ID”, “url” und “name”.</p>

<p>Öffnet sich die App, so landet der Nutzer auf der Seite MAIN, die als Hauptseite (make default) definiert ist. Klickt er auf “I’m a pussy”, wird er einfach auf die Seite “NO” weitergeleitet, ein weiterer Klick auf diese Seite befördert ihn zurück auf die Startseite. Klickt der User auf “Hell Yeah”, so wird er auf den screen “GAME” weitergeleitet.</p>

<h3>
Orders
</h3>

<p>Dort wird er von einem Einleitungstext im Textfeld “GameText” willkommen geheißen. Wenn dieses Textfeld, welches sich über den gesamten Bildschirm erstreckt, geklickt wird, startet die Funktion “changeOrder”. Sie soll auf die Datenbank orders zugreifen, daraus einen zufälligen Befehl greifen und den Text des Textfeldes “GameText” durch den Text eben dieses Befehls ersetzen. Außerdem soll die Funktion die Hintergrundfarbe der Seite zu einer zum Befehl gehörenden ändern.</p>

<p>Also wird zunächst mithilfe von readRecords eine zufällige Zahl zwischen 1 und der größten ID in der Datenbank “orders” auf die Variable “random” gespeichert. Daraufhin wird durch ein weiteres readRecords in der Datenbank nach der eben bestimmten zufälligen ID gesucht. Es folgt eine Ausgabe der entsprechenden Zeile, woraufhin diese Zeile in einer for-Schleifen durchlaufen wird und der Text des Textfeldes “gameText” durch den Wert in der Spalte “text” ersetzt wird. Dasselbe Procedere wird im Anschluss noch einmal durchlaufen, um mit dem Farbwert des Befehls die Hintergrundfarbe der Seite zu ändern. Wird erneut auf den gameText geklickt, so wiederholt sich schlichtweg die gesamte Funktion “changeOrder”, um den Befehl erneut zu ändern. Möchte der Nutzer wieder zurück zur Startseite, so muss er nur rechts unten auf den immer vorhandenen Button “Home” drücken.</p>

<h3>
Drinks
</h3>

<img src="pictures/drink generator.png" alt="drink generator">

<p>Wird im Hauptmenü der Button “Good drinks for a great Party” ausgewählt, so wechselt die App auf die Seite “DRINKS”. In der Funktion “createButtons” werden mithilfe von readRecords hier in einer for-Schleife für jedes Listenelement in “drinks” Buttons erstellt, die jeweils ihre Beschriftung aus der Spalte “name” auslesen. Im Programm erhält man Bezeichungen, die von der jeweiligen ID abhängen, wie drink1, drink2, drink3 usw.. Außerdem werden die Buttons alle gleich formatiert und die y-Position auf dem Bildschirm anhand einer einfachen Formel, die von der ID Gebrauch macht, berechnet.</p>

<p>Wird nun einer der eben erstellten Buttons gedrückt, wird eine weitere Funktion readRecords gestartet, die mithilfe der ID des geklickten Buttons den Wert der Spalte url des zugehörigen Elementes findet. Nun wird auf die Seite “DRINKPIC” gewechselt, die Flächendeckend vom Bild recipe bedeckt ist. Dieses Bild erhält nun die eben gefundene url und das entsprechende Bild wird geladen. Wird dieses Bild wiederum geklickt, öffnet sich wieder der screen “DRINKS”, während die url des Bildes “recipe” genullt wird, sodass während der Ladezeit des nächsten Rezeptes nicht das alte Bild angezeigt wird.</p>

<p>Beim Klicken des Bildes wurde nicht nur die Seite gewechselt, sondern auch die Funktion “createButtons” neu gestartet, da diese nicht nur beim Klicken des Buttons “Good drinks for a great party”, sondern durch den Ausdruck “oder”, also “||” auch durch Drücken des Rezeptbildes gestartet wird. Um ein gedoppeltes Laden der Bilder zu vermeiden, werden hier zunächst alle alten Buttons gelöscht. Während des Aufenthalts auf dieser Seite ist es dem Nutzer ebenfalls möglich, jederzeit durch ein Drücken des Buttons “Home” auf den Startbildschirm zurück zu kehren.</p>

<h2>
<a id="Fin">Finale App</a>
</h2>


<p>Die fertige App kann nun über den Link <a href="https://studio.code.org/projects/applab/fE2MZErtLIvPFBxEBf-o7Q" target="_blank">CranberryVodka</a>  geteilt werden.</p>

<p>Wenn man den link öffnet, muss erst das Alter des Users angegeben werden. Applab verbietet es Minderjährigen die Apps auf dem Smartphone zu speichern und leitet diese zu Code.org® weiter.</p>

<p>Um die App auf das smartphone zu laden, muss man diese zu home screen hinzuzufügen.</p>
  
<table>
 <tr>
  <td width="50%">

  
 <img src="pictures/iphonescreenshotapplab.PNG" alt="Screenshot iPhone">
 
 </td>
 <td width="50%">
 
 <img src="pictures/screenshot2.png" alt="Screenshot2">
 
 </td>
 </tr>
 
 <tr>
 <td>
 
 <img src="pictures/screenshot3.png" alt="Screenshot3">
 
 </td>
 <td>
 
 <img src="pictures/screenshot4.png" alt="Screenshot4">
 
 </td>
 </tr>
 </table>
 
<h2>
<a id="Bug">Bugs</a>
</h2>

<p>Da der gametext mit der jeweiligen Hintergrundfarbe über den ganzen Bildschirm definiert wurde, mussten keine neuen screens geschaffen werden, wodurch das einfügen von neuen orders und drinks einfacher wird. Jedoch zieht das nach sich, dass ein dünner grauer Rand auf dem Bildschirm zu erkennen ist.</p>

<p>Dies könnte eventuell bei Design geändert werden(?)</p>
<p>Zudem können "random" wieder aus der liste orders gezogen werden, wodurch die gleiche order nochmals dran kommen kann.</p>

<p>Dies könnte eventuell geändert werden, indem die bereits gezogenen orders in eine neue Liste verschoben werden und nicht wieder gewählt werden können, jedoch ist die List fest definiert(?)</p>

<p>Die Liste könnte mehr orders erhalten und die Chancen, dass die selbe "random" gezogen wird, ist dadurch kleiner <sup>?</sup>
Diese App wurde erstellt von Thao Mi Pham, 12 ab, im Rahmen des Informatikunterrichts an der Stormarnschule bei Herrn Buhl im Jahre 2016.</p>

<p style="color: pink; font-family: comic-sans;"><sub>App is being used by Thao Mi Pham and her friends at parties :P</sub></p>
