Perfekt — diese Fragenliste zeigt deutlich, **wie du den Stoff für die mündliche Prüfung beherrschen musst**: weniger stumpfes Auswendiglernen, mehr **Begriffe erklären, Unterschiede darstellen und Beispiele geben**. Deine ursprüngliche Unterlage deckt insbesondere die Grundlagen, Bildsteganographie, physikalische Kanäle, Stego-Dateisysteme, Textsteganographie und Wasserzeichen ab.

Für die **25-minütige mündliche Prüfung** würde ich ab jetzt mit dir genau im Prüfungsformat lernen.

## 🎓 Block 1: Information Hiding – die Basis

### Frage: „Was versteht man unter Information Hiding?“

Eine gute mündliche Antwort wäre:

> Information Hiding bezeichnet die gezielte Verschleierung von Informationen. Dabei kann nicht nur der Inhalt einer Nachricht verborgen werden, sondern beispielsweise auch ihre Existenz, Bedeutung oder die Kommunikationsbeziehung zwischen Sender und Empfänger.


Danach könnte der Prüfer sofort fragen:

### „Welche Teilbereiche gibt es?“
Aus deiner Unterlage solltest du diese kennen:
**Information Hiding**  
→ Anonymität  
→ Covert Channels  
→ Kryptographie  
→ Obfuskation  
→ Steganographie  
→ Wasserzeichen

Die Unterschiede:

|Bereich|Was wird verborgen?|
|---|---|
|Kryptographie|verständlicher Inhalt|
|Steganographie|Existenz einer Nachricht|
|Anonymität|Sender/Empfänger bzw. Kommunikationsbeziehung|
|Covert Channel|Kommunikation über nicht dafür vorgesehene Ressourcen|
|Obfuskation|charakteristische Merkmale|
|Wasserzeichen|Information über Cover/Eigentümer/Herkunft usw.|

Diese Einteilung wird in deinem Lernmaterial ausdrücklich vorgenommen.

---

# 🎓 Block 2: Kapazität vs. Bandbreite

Das ist aufgrund deiner Prüfungsfragen **sehr wichtig**.

### Kapazität

Frage:

> **Wie viel Information kann ich verstecken?**

Beispiel:

Ein Bild kann insgesamt **10.000 geheime Bits** aufnehmen.

→ Kapazität.

### Bandbreite

Frage:

> **Wie viel Information kann ich pro Zeit übertragen?**

Beispiel:

Ein verdeckter Netzwerkkanal überträgt **10 Bit pro Sekunde**.

→ Bandbreite.

**Merksatz:**

> 📦 Kapazität = Menge  
> 🚀 Bandbreite = Menge pro Zeit

Gerade bei verdeckten Kommunikationskanälen ist die Bandbreite relevant. Deine Unterlage weist ausdrücklich darauf hin, dass ein Kanal eine hohe Gesamtkapazität besitzen, aber trotzdem nur wenige Bits pro Zeiteinheit übertragen kann.

---

# 🎓 Block 3: Steganographie

### „Was ist Steganographie?“

Prüfungsantwort:

> Steganographie bezeichnet das Verbergen einer geheimen Nachricht in einem unverdächtigen Cover-Objekt. Ziel ist insbesondere, die Existenz der geheimen Kommunikation zu verbergen.

Das Cover kann zum Beispiel ein **Bild, eine Audiodatei, ein Text, ein Dateisystem oder eine Netzwerkressource** sein.

### „Muss Steganographie technisch sein?“

**Nein.**

Das ist eine klassische Verständnisfrage.

Informationsverstecken existierte schon lange vor Computern. Deine Unterlage nennt beispielsweise geheime Nachrichten, die aus Anfangsbuchstaben aufeinanderfolgender Wörter gebildet werden.

---

# 🎓 Block 4: Dual Use

### „Was bedeutet Dual-Use-Technologie?“

Eine Technologie kann sowohl für **legitime** als auch für **schädliche/problematische Zwecke** verwendet werden.

### „Warum ist Steganographie Dual Use?“

Beispielsweise:

**Legitim:** Journalisten oder Aktivisten können Kommunikation vor Überwachung schützen.

**Problematisch:** Verdeckte Kanäle können zur unbemerkten Kommunikation oder zur Umgehung von Sicherheitsgrenzen verwendet werden.

Genau diese beiden Seiten werden in deiner Unterlage gegenübergestellt.

---

# 🎓 Block 5: Gegenmaßnahmen

Prüfer:

> „Was versteht man unter Gegenmaßnahmen?“

Antwort:

> Gegenmaßnahmen sind technische oder organisatorische Maßnahmen, die Informationsverstecken verhindern, beschränken oder erkennen sollen.

Ziele können sein:

**Einbettung verhindern → Kapazität/Bandbreite reduzieren → versteckte Informationen erkennen → Ressourcen absichern → Datenabfluss verhindern.**

Hier solltest du außerdem das **Arms Race** erklären können:

Versteckverfahren wird entwickelt  
→ Gegenmaßnahme erkennt es  
→ Verfahren wird verbessert  
→ neue Gegenmaßnahme  
→ Verfahren wird erneut angepasst  
→ …

Also ein fortlaufendes technisches **Wettrüsten**.

---

# 🎓 Block 6: Bilder

### „Welche Bildformate unterscheidet man?“

Dein Material unterscheidet:

**Rasterformate**

Jeder Pixel speichert seine Farbwerte.

Beispiele: **BMP, PNG, TIFF**

und

**Palettenformate**

Eine Tabelle enthält mögliche Farben und ein Pixel speichert nur den **Index** auf einen Eintrag dieser Tabelle.

Beispiel: **GIF**, teilweise auch PNG.

### „Wie kann eine geheime Nachricht eingebettet werden?“

Ein einfaches Beispiel ist wieder **LSB**.

Geheimer Bitwert:

`1`

Pixelwert:

`11010110`

LSB ersetzen:

`11010111`

Die Änderung des Farbwertes ist sehr klein.

→ Mensch bemerkt möglicherweise nichts.

→ Das geheime Bit wurde trotzdem gespeichert.

LSB kann unter anderem Farbwerte, Palettenindizes oder auch quantisierte Frequenzkoeffizienten betreffen.

---

# ⚠️ Jetzt kommt Kurs 01731

Hier solltest du vorsichtig sein: Deine bisherige hochgeladene Unterlage behandelt zwar **physikalische Covert Channels und Shared Resources**, aber mehrere Begriffe aus deiner neuen Prüfungsfragenliste — insbesondere **Warden-Typen, Hiding Patterns, Network Environment Learning, Mikroprotokolle und Replication Studies** — werden darin nicht ausreichend behandelt.

Ich würde diese Inhalte deshalb **nicht erfinden oder aus allgemeinem Wissen als angeblichen Inhalt deiner Unterlage ergänzen**.

Was deine Unterlage bereits gut abdeckt:

### Shared Resource

Grundprinzip:

> Zwei Prozesse können über eine Ressource kommunizieren, wenn beide Zugriff darauf haben.

Beispielsweise:

**Prozess A → verändert Ressource → Prozess B → beobachtet Veränderung**

Damit entsteht potenziell ein verdeckter Kanal.

Die Shared Resource Matrix stellt dabei **Prozesse als Spalten und Ressourcen als Zeilen** dar und zeigt die jeweiligen Zugriffsarten.

---

# 🧠 Was du für die mündliche Prüfung können musst

Bei fast jedem Begriff trainieren wir künftig dieselben **vier Ebenen**:

**1. Definition**

> Was ist das?

**2. Abgrenzung**

> Was ist der Unterschied zu einem ähnlichen Begriff?

**3. Beispiel**

> Nennen Sie ein konkretes Beispiel.

**4. Bewertung**

> Welche Vor-/Nachteile, Gegenmaßnahmen oder Zielkonflikte existieren?

Wenn du beispielsweise nur sagen kannst:

> „LSB bedeutet Least Significant Bit.“

ist das zu wenig.

Du solltest frei erklären können:

> „Bei LSB-Steganographie wird das niedrigstwertige Bit eines Bildwertes zur Einbettung einer geheimen Information verwendet. Dadurch verändert sich der ursprüngliche Wert nur geringfügig. Der Vorteil ist eine relativ einfache Einbettung. Ein Nachteil besteht darin, dass die Veränderungen statistische Spuren erzeugen können und dadurch detektierbar werden.“

**Das ist das Niveau, auf das wir dich bringen wollen.** Die Vor- und Nachteile ergeben sich unmittelbar aus der Beschreibung und den Grenzen des LSB-Verfahrens in deiner Unterlage.







Klar. Ich mache es jetzt so, dass du es **wirklich verstehen und in der mündlichen Prüfung erklären kannst**. Deine Prüfungsübersicht zeigt, dass du vor allem Begriffe erklären, Unterschiede nennen und Beispiele geben können sollst. 

## 1. Was ist Information Hiding?

**Information Hiding bedeutet: Informationen werden versteckt.**

Dabei kann man unterschiedliche Dinge verstecken:

* den Inhalt einer Nachricht,
* die Existenz einer Nachricht,
* wer mit wem kommuniziert,
* oder bestimmte Merkmale einer Kommunikation.

### Einfaches Beispiel

Du willst jemandem heimlich sagen:

**„Treffen um 18 Uhr.“**

Bei **Kryptographie** verschlüsselst du den Satz:

`X7H92KL...`

Jeder sieht: **Da ist eine geheime Nachricht.**
Aber niemand versteht sie ohne Schlüssel.

Bei **Steganographie** versteckst du den Satz zum Beispiel in einem normalen Foto.

Jeder sieht nur:

🏖️ „Urlaubsfoto“

Die geheime Nachricht soll gar nicht auffallen.

**Merke:**

> 🔐 Kryptographie versteckt den Inhalt.
> 🥷 Steganographie versteckt möglichst die Existenz der Nachricht.

---

# 2. Kapazität und Bandbreite

Die beiden Begriffe werden gerne verwechselt.

### Kapazität

**Frage:** Wie viel kann ich insgesamt verstecken?

Beispiel:

In einem Bild kann ich **10.000 Bits** verstecken.

→ Das ist die **Kapazität**.

### Bandbreite

**Frage:** Wie schnell kann ich Informationen übertragen?

Beispiel:

Ein verdeckter Netzwerkkanal kann **10 Bit pro Sekunde** übertragen.

→ Das ist die **Bandbreite**.

Deine Prüfungsunterlage hebt genau diese Unterscheidung hervor. 

### Merksatz

> 📦 Kapazität = **Wie viel?**
> 🚀 Bandbreite = **Wie schnell?**

---

# 3. Was ist Steganographie?

Steganographie bedeutet:

> **Eine geheime Nachricht wird in etwas Unauffälligem versteckt.**

Dieses „Etwas“ nennt man häufig **Cover** oder **Cover-Objekt**.

Beispiele:

Bild → geheime Nachricht im Bild
Text → geheime Nachricht im Text
Audio → geheime Nachricht in Musik
Netzwerkverkehr → geheime Nachricht in Netzwerkpaketen

### Einfaches Beispiel

Normales Bild:

🌳 🏠 ☀️

Im Bild werden einige winzige Pixelwerte verändert.

Für einen Menschen sieht es immer noch genau gleich aus.

Aber ein bestimmtes Programm kann aus diesen Pixeln lesen:

> „PASSWORT123“

Das wäre Bildsteganographie.

---

# 4. Muss Steganographie technisch sein?

**Nein.**

Steganographie gab es schon vor Computern.

Beispiel:

> **H**eute
> **I**st
> **L**ernen
> **F**ür
> **E**xperten

Die Anfangsbuchstaben ergeben:

**H I L F E**

Die eigentliche Nachricht wurde also innerhalb eines normalen Textes versteckt.

Steganographische Speicherung und Übertragung müssen daher nicht zwingend auf moderne Computertechnik beschränkt sein. Deine Prüfungsübersicht nennt diese Unterscheidung ausdrücklich als möglichen Prüfungsgegenstand. 

---

# 5. Was bedeutet Dual Use?

**Dual Use bedeutet: Eine Technik kann für gute und schlechte Zwecke benutzt werden.**

### Beispiel: Messer 🔪

Mit einem Messer kann man:

🥕 Gemüse schneiden
oder
⚠️ jemanden verletzen.

Die Technik selbst entscheidet nicht, wofür sie eingesetzt wird.

### Bei Steganographie

**Legitim:**

Ein Journalist versteckt Informationen, damit sie nicht von einer repressiven Regierung entdeckt werden.

**Missbräuchlich:**

Malware versteckt gestohlene Daten in normal aussehendem Netzwerkverkehr.

Deshalb gilt Steganographie als **Dual-Use-Technologie**. Auch Forschung zu Network Steganography beschreibt sowohl legitime Einsatzmöglichkeiten als auch Risiken wie verdeckten Datenabfluss. ([arXiv][1])

### Prüfungsantwort

> „Eine Dual-Use-Technologie kann sowohl für legitime als auch für schädliche Zwecke verwendet werden. Steganographie ist Dual Use, weil sie beispielsweise zum Schutz sensibler Kommunikation, aber auch zur verdeckten Übertragung unerlaubter Informationen eingesetzt werden kann.“

---

# 6. Was sind Gegenmaßnahmen?

Gegenmaßnahmen versuchen, versteckte Kommunikation:

**zu erkennen, zu erschweren oder zu verhindern.**

Deine Unterlage definiert sie genau so. 

### Beispiel

Angenommen, jemand versteckt Daten in einem bestimmten Feld eines Netzwerkpakets.

Eine Gegenmaßnahme könnte sagen:

> „Dieses Feld wird eigentlich nicht benötigt. Ich setze es deshalb immer auf 0.“

Dann wird die darin versteckte Nachricht zerstört.

---

# 7. Speicherung oder Übertragung?

Auch sehr einfach:

### Steganographische Speicherung

Die Nachricht wird **irgendwo versteckt abgelegt**.

Beispiel:

Ich verstecke mein Passwort in einem Bild auf meiner Festplatte.

→ **Speicherung**

### Steganographische Übertragung

Die versteckte Nachricht wird **von A nach B geschickt**.

Beispiel:

Ich schicke dir dieses Bild über das Internet und darin befindet sich die geheime Nachricht.

→ **Übertragung**

Deine Zusammenfassung unterscheidet genau diese beiden Fälle. 

### Merksatz

> 💾 Speicherung = versteckt **liegen lassen**
> 📡 Übertragung = versteckt **verschicken**

---

# 8. Bildsteganographie

Bei Bildern gibt es verschiedene Möglichkeiten, Informationen zu verstecken.

Ein sehr einfaches Verfahren ist **LSB-Steganographie**.

LSB bedeutet:

**Least Significant Bit**

also:

> das niedrigstwertige Bit.

Nehmen wir einen Pixelwert:

`10110110`

Das letzte Bit ist:

**0**

Wir wollen eine geheime **1** speichern.

Dann ändern wir:

`10110110`

zu:

`10110111`

Der Wert verändert sich nur minimal.

Für das menschliche Auge kann der Unterschied praktisch unsichtbar sein.

### Merksatz

> LSB = Ich verstecke Informationen in den **letzten Bits von Pixelwerten**.

---

# 9. Storage Channel vs. Timing Channel ⭐

Jetzt beginnt der besonders wichtige Bereich **Network Steganography**. Deine Prüfungsübersicht nennt diese Unterscheidung ausdrücklich. 

## Storage Channel

Hier verändere ich **Daten oder Eigenschaften von Daten**.

Beispiel:

Ein Netzwerkpaket enthält ein Feld, das kaum benutzt wird.

Ich lege darin fest:

`0 = geheimes Bit 0`

`1 = geheimes Bit 1`

Ich verstecke die Nachricht also **in den Daten**.

→ **Storage Channel**

## Timing Channel

Hier verstecke ich Informationen nicht in den Daten, sondern in der **Zeit**.

Beispiel:

Ich sende Pakete mit unterschiedlichen Abständen:

kurzer Abstand = **0**

langer Abstand = **1**

Dann könnte die Folge

kurz – lang – lang – kurz

bedeuten:

`0110`

→ **Timing Channel**

Die Fachliteratur beschreibt dieselbe Grundunterscheidung: Storage Channels verändern einen Datenträger wie etwa ein Protokollfeld, während Timing Channels zeitliche Beziehungen wie Paketabstände verändern. ([arXiv][2])

### Prüfungs-Merksatz

> 📦 Storage Channel = **Was wird übertragen?**
> ⏱️ Timing Channel = **Wann wird übertragen?**

---

# 10. Shared Resource Methodology

Der Name klingt komplizierter als die Idee.

**Shared Resource = gemeinsam genutzte Ressource**

Zwei Teilnehmer können dieselbe Ressource benutzen.

Einer verändert sie.

Der andere beobachtet die Veränderung.

Dadurch können Informationen übertragen werden. 

### Beispiel

Wir haben:

Computer A
Computer B
gemeinsame Ressource X

A möchte eine geheime **1** senden.

A verändert Ressource X.

B sieht:

> „Die Ressource wurde verändert.“

→ B liest **1**.

Für eine **0** verändert A die Ressource nicht.

### Merksatz

> Einer **verändert**, der andere **beobachtet**.

---

# 11. Overt und Covert Sender/Receiver ⭐

Vier Begriffe:

**Overt = offen**

**Covert = versteckt**

Deine Unterlage definiert sie so: Overt Sender und Receiver sind die sichtbaren Kommunikationspartner; Covert Sender und Receiver bringen die versteckte Information ein beziehungsweise lesen sie aus. 

### Beispiel

Alice schickt Bob ganz normal ein Netzwerkpaket.

Nach außen sieht man:

**Alice → Bob**

Alice ist hier der:

**Overt Sender**

Bob der:

**Overt Receiver**

Jetzt sitzt aber auf Alices Computer ein Schadprogramm.

Dieses Schadprogramm verändert heimlich bestimmte Paketinformationen.

→ **Covert Sender**

Auf einer anderen Stelle befindet sich ein Programm, das diese Informationen wieder ausliest.

→ **Covert Receiver**

### Merksatz

> 👀 Overt = sichtbare Kommunikation
> 🥷 Covert = versteckte Kommunikation

---

# 12. Network Covert Channel

Ein Network Covert Channel ist einfach gesagt:

> **Ein versteckter Kommunikationsweg innerhalb normaler Netzwerkkommunikation.**

Dabei nutzt man etwas, das eigentlich nicht für diese Kommunikation gedacht war. 

### Beispiel

Ein Netzwerkprotokoll besitzt ein Feld, das normalerweise kaum genutzt wird.

Normal:

`Feld = 0`

Der geheime Sender macht daraus:

`0 = geheimes Bit 0`

`1 = geheimes Bit 1`

Dann überträgt scheinbar normaler Netzwerkverkehr gleichzeitig eine zweite geheime Nachricht.

---

# 13. Was ist ein Warden? 🛡️

Ein **Warden** überwacht die Kommunikation und versucht versteckte Kommunikation zu:

**erkennen oder verhindern.** 

Stell dir einen Sicherheitsbeamten vor:

Sender → 📦 → **WARDEN 🛡️** → 📦 → Empfänger

Der Warden untersucht:

> „Sieht dieser Netzwerkverkehr normal aus?“

Fällt etwas auf, kann er reagieren.

In der Forschung werden unter anderem statische, dynamische und adaptive Warden-Strategien untersucht. Ein adaptiver Warden kann seine Normalisierungsregeln abhängig vom beobachteten Verkehr auswählen. ([arXiv][3])

---

# 14. Was ist ein Normalizer?

Der **Normalizer** verändert den Netzwerkverkehr so, dass er wieder einer vorher festgelegten „normalen“ Form entspricht.

Deine Zusammenfassung beschreibt ihn als Verfahren oder Instanz zur Standardisierung von Daten, wodurch versteckte Informationen entfernt oder erschwert werden können. 

### Beispiel

Angreifer benutzt ein unwichtiges Feld:

`101`

Normalizer sagt:

> „Dieses Feld sollte immer 000 sein.“

Also:

`101 → 000`

💥 Die versteckte Information ist weg.

### Unterschied

**Warden:**

> „Ich überwache den Verkehr.“

**Normalizer:**

> „Ich verändere den Verkehr, damit verdächtige Unterschiede verschwinden.“

---

# 15. Steganographic Cost

Das bedeutet vereinfacht:

> **Wie stark muss ich den normalen Datenverkehr verändern, um meine Information zu verstecken?**

Deine Prüfungsübersicht beschreibt die Steganographic Cost als die durch das Einbetten verursachten Kosten beziehungsweise Veränderungen. 

### Beispiel

Normalerweise kommen Pakete alle ungefähr:

`20 ms`

Für meine geheime Kommunikation mache ich plötzlich:

`20 – 500 – 20 – 800 – 20 ms`

Das ist eine starke Veränderung.

→ **hoher steganographic cost**

Wenn ich nur minimal ändere:

`20 – 22 – 19 – 21 ms`

→ kleinere Veränderung.

---

# 16. Covertness / Stealthiness

Das bedeutet:

> **Wie unauffällig ist meine versteckte Kommunikation?**

Beispiel:

Wenn meine Paketabstände völlig merkwürdig aussehen:

→ geringe Stealthiness.

Wenn sie fast genauso aussehen wie normaler Netzwerkverkehr:

→ hohe Stealthiness.

### Unterschied zum Steganographic Cost

Das ist wichtig:

> **Cost = Wie stark verändere ich etwas?**

> **Stealthiness = Wie leicht fällt diese Veränderung auf?** 

---

# 17. Hiding Patterns

Auch hier klingt der Name schlimmer als das Konzept.

**Pattern = Muster**

Es gibt sehr viele Möglichkeiten, Informationen zu verstecken.

Statt jedes einzelne Verfahren separat zu lernen, versucht man ähnliche Verfahren zu **Mustergruppen** zusammenzufassen.

### Beispiel

Methode A:

Information in einem TCP-Feld ändern.

Methode B:

Information in einem anderen Protokollfeld ändern.

Technisch sind sie unterschiedlich.

Aber die Grundidee ist gleich:

> „Ein vorhandener Datenwert wird verändert.“

Also können sie demselben **Hiding Pattern** zugeordnet werden.

### Warum ist das nützlich?

Man kann Verfahren besser:

**ordnen → vergleichen → beschreiben → neue Verfahren einordnen.**

Genau das nennt deine Prüfungsunterlage als Vorteil.  Wissenschaftliche Arbeiten zu Hiding Patterns verfolgen ebenfalls das Ziel, unterschiedliche Steganographie-Verfahren einheitlicher zu beschreiben und vergleichbar zu machen. ([arXiv][4])

---

# 18. Network Environment Learning

Der verdeckte Sender schaut sich zuerst an:

> **„Wie verhält sich dieses Netzwerk normalerweise?“**

Er lernt also die Umgebung kennen. Deine Unterlage beschreibt Network Environment Learning allgemein als Untersuchung und Lernen der Netzwerkumgebung. 

### Warum?

Weil die geheime Kommunikation möglichst normal aussehen soll.

### Beispiel

Der Sender beobachtet:

Normale Paketabstände:

`18–25 ms`

Dann wäre es dumm, für die geheime Kommunikation plötzlich:

`500 ms`

zu verwenden.

Das wäre auffällig.

Also versucht er, seine Kommunikation an das normale Netzwerk anzupassen.

### Merksatz

> 👀 Erst Netzwerk beobachten → 🧠 normales Verhalten lernen → 🥷 verdeckte Kommunikation daran anpassen.

---

# 19. Mikroprotokolle

Ein verdeckter Kanal muss trotzdem irgendwie organisiert werden.

Beispielsweise muss der Empfänger wissen:

**Wo beginnt eine Nachricht?**

**Wo endet sie?**

**Welche Reihenfolge haben die Daten?**

**Ist etwas verloren gegangen?**

Dafür können **Mikroprotokolle** eingesetzt werden. Deine Prüfungsübersicht nennt ihren Zweck als wichtigen Prüfungsgegenstand, erläutert ihn aber nicht weiter. 

Einfaches Beispiel:

Geheime Daten:

`START | 001101 | ENDE`

Das kleine Steuerungssystem:

`START`
`ENDE`
Reihenfolge usw.

ist vereinfacht die Idee eines Mikroprotokolls.

### Merksatz

> Mikroprotokoll = **kleines Kommunikationsprotokoll innerhalb des verdeckten Kanals**.

---

# 20. Replication Studies 🔬

Das ist ein wissenschaftliches Thema.

**Replication Study = Wiederholungsstudie**

Ein Forscher behauptet zum Beispiel:

> „Mein Verfahren kann 100 Bit/s versteckt übertragen.“

Ein anderes Forschungsteam führt das Experiment erneut durch.

Ergebnis:

**100 Bit/s**

→ Ergebnis wird stärker bestätigt.

Oder:

**nur 20 Bit/s**

→ ursprüngliches Ergebnis muss hinterfragt werden.

Deine Unterlage nennt genau diesen Zweck: Ergebnisse erneut untersuchen und ihre Zuverlässigkeit besser beurteilen. 

### Merksatz

> 🔬 Replikation bedeutet: **Andere prüfen, ob ein wissenschaftliches Ergebnis reproduzierbar ist.**

---

# 🧠 Die 10 wichtigsten Sätze für deine Prüfung

Wenn du zunächst nur diese Sätze sicher kannst, hast du schon ein gutes Grundgerüst:

**1. Information Hiding:**
Informationen oder ihre Existenz werden verborgen.

**2. Steganographie:**
Eine geheime Nachricht wird in einem unauffälligen Cover versteckt.

**3. Kapazität:**
Wie viel Information kann ich verstecken?

**4. Bandbreite:**
Wie viel Information kann ich pro Zeit übertragen?

**5. Storage Channel:**
Die geheime Information steckt in Daten oder deren Eigenschaften.

**6. Timing Channel:**
Die geheime Information steckt im zeitlichen Verhalten.

**7. Shared Resource:**
Ein Sender verändert eine gemeinsame Ressource und ein Empfänger beobachtet sie.

**8. Warden:**
Er überwacht Netzwerkverkehr und versucht verdeckte Kommunikation zu erkennen oder zu verhindern.

**9. Steganographic Cost:**
Wie stark muss ich den normalen Träger verändern?

**10. Stealthiness:**
Wie unauffällig bleibt diese Veränderung?

Wenn der Prüfer fragt:

> „Was ist der Unterschied zwischen Storage und Timing Channel?“

reicht also nicht nur:

> „Das eine ist Storage und das andere Timing.“

Eine **sehr gute kurze Prüfungsantwort** wäre:

> „Bei einem Storage Channel wird die geheime Information in Eigenschaften der übertragenen Daten versteckt, zum Beispiel in einem Protokollfeld. Bei einem Timing Channel wird dagegen das zeitliche Verhalten verändert, beispielsweise die Abstände zwischen Paketen. Vereinfacht gesagt: Beim Storage Channel steckt die Information in den Daten, beim Timing Channel in der Zeit.“

Das ist genau die Art von **30–40-Sekunden-Antwort**, die du für eine mündliche Prüfung trainieren solltest. 📚 ([arXiv][2])

[1]: https://arxiv.org/pdf/1407.2029?utm_source=chatgpt.com "On the Emergence of Network Steganographic Threats"
[2]: https://arxiv.org/pdf/2111.03310?utm_source=chatgpt.com "Adaptive Warden Strategy for Countering Network Covert ..."
[3]: https://arxiv.org/abs/2111.03310?utm_source=chatgpt.com "Adaptive Warden Strategy for Countering Network Covert Storage Channels"
[4]: https://arxiv.org/abs/1512.07438?utm_source=chatgpt.com "Unified Description for Network Information Hiding Methods"



- https://www.studocu.com/de/search?courseId=135923&institutionId=79
- 






