# Information Hiding – einfach erklärt mit Diagrammen

> **Ziel:** Die Themen so verstehen, dass du sie in der mündlichen Prüfung **in eigenen Worten erklären und mit einem Beispiel zeigen** kannst.

---

# 1. Was ist Information Hiding?

**Information Hiding = Informationen verstecken.**

Dabei kann nicht nur der Inhalt einer Nachricht versteckt werden. Man kann auch verstecken:

* dass überhaupt eine Nachricht existiert,
* wer mit wem kommuniziert,
* welche Bedeutung etwas hat,
* oder bestimmte Merkmale einer Kommunikation.

## Visualisierung

```text
                    INFORMATION HIDING
                           │
          ┌────────────────┼─────────────────┐
          │                │                 │
          ▼                ▼                 ▼
       Inhalt          Existenz         Beziehung
      verstecken       verstecken       verstecken
          │                │                 │
          ▼                ▼                 ▼
   Kryptographie     Steganographie      Anonymität
```

## Einfaches Beispiel

Alice möchte Bob heimlich mitteilen:

```text
Treffen um 18 Uhr.
```

### Kryptographie 🔐

```text
Treffen um 18 Uhr
        │
        ▼
   Verschlüsselung
        │
        ▼
   X8a9K2Lm91...
        │
        ▼
       Bob
```

Ein Beobachter sieht:

> „Hier wird etwas Geheimes übertragen.“

Er kann aber den **Inhalt nicht verstehen**.

### Steganographie 🥷

```text
Geheime Nachricht
"Treffen um 18 Uhr"
        │
        ▼
┌──────────────────┐
│   🏖️ Urlaubsbild │
│  Nachricht darin │
│     versteckt    │
└──────────────────┘
        │
        ▼
       Bob
```

Ein Beobachter sieht nur:

> „Alice schickt Bob ein Urlaubsbild.“

Er soll möglichst **nicht einmal wissen, dass eine geheime Nachricht existiert**.

## Merksatz

```text
Kryptographie  → WAS gesagt wird, wird unlesbar.
Steganographie → DASS etwas gesagt wird, soll verborgen bleiben.
```

---

# 2. Die wichtigsten Bereiche

Die Unterlage unterscheidet unter anderem Kryptographie, Steganographie, Anonymität, Covert Channels, Obfuskation und Wasserzeichen.

```text
                     INFORMATION HIDING
                            │
      ┌───────────┬─────────┼─────────┬─────────────┐
      │           │         │         │             │
      ▼           ▼         ▼         ▼             ▼
 Kryptographie  Stegano-  Anonymität Covert      Wasser-
                graphie              Channels     zeichen
      │           │         │         │             │
      ▼           ▼         ▼         ▼             ▼
   Inhalt      Existenz   Wer mit   versteckter   Info über
 unleserlich   verstecken wem?      Kanal         das Cover
```

### Beispiel für jeden Bereich

| Bereich        | Einfaches Beispiel                                             |
| -------------- | -------------------------------------------------------------- |
| Kryptographie  | Eine Nachricht wird verschlüsselt                              |
| Steganographie | Nachricht wird in einem Bild versteckt                         |
| Anonymität     | Man versteckt, wer der Sender ist                              |
| Covert Channel | Cache, Netzwerkfeld, Licht usw. wird zur Kommunikation benutzt |
| Obfuskation    | Eigenschaften werden verschleiert                              |
| Wasserzeichen  | Copyright-Information wird in einem Bild gespeichert           |

---

# 3. Kapazität vs. Bandbreite

Diese beiden Begriffe darfst du nicht verwechseln.

## Kapazität 📦

**Frage: Wie viel Information kann insgesamt versteckt werden?**

```text
┌───────────────────────────────┐
│            BILD               │
│                               │
│  ██████████████████████████   │
│                               │
│  Platz für 10.000 geheime Bits│
└───────────────────────────────┘

        = KAPAZITÄT
```

Beispiel:

> In einem Bild können insgesamt 10.000 Bits versteckt werden.

---

## Bandbreite 🚀

**Frage: Wie schnell können Informationen übertragen werden?**

```text
Sender                           Empfänger
  │                                  │
  │──── 10 Bit ─────────────────────>│
  │                                  │
  │          pro Sekunde             │
  │                                  │

       = 10 Bit/s Bandbreite
```

Die Unterlage beschreibt Kapazität als Menge der versteckbaren Information und Bandbreite als Übertragungsumfang bzw. -geschwindigkeit.

## Super-Merksatz

```text
Kapazität  = WIE VIEL?
Bandbreite = WIE SCHNELL?
```

---

# 4. Zielkonflikt bei Steganographie

Ein wichtiger Zusammenhang:

```text
           MEHR DATEN VERSTECKEN
                    │
                    ▼
             höhere Kapazität
                    │
                    ▼
          mehr Veränderungen
                    │
                    ▼
          eventuell auffälliger
                    │
                    ▼
          leichter zu erkennen
```

Deshalb gilt häufig:

```text
Kapazität ↑
     │
     └──────► Entdeckungsrisiko ↑
```

Eine hohe Kapazität kann stärkere Veränderungen des Cover-Objekts verursachen und dadurch die Entdeckung erleichtern.

---

# 5. Robustheit

**Robustheit = Überlebt die versteckte Nachricht Veränderungen?**

Beispiel:

```text
Bild + geheime Nachricht
          │
          ▼
     Komprimierung
          │
          ▼
      Verkleinern
          │
          ▼
     Format ändern
          │
          ▼
Geheime Nachricht noch da?
          │
      ┌───┴───┐
      │       │
     JA      NEIN
      │       │
      ▼       ▼
   robust   nicht robust
```

Robustheit ist beispielsweise wichtig, wenn Bilder komprimiert, skaliert oder in ein anderes Format umgewandelt werden.

---

# 6. Unmerklichkeit vs. Undetektiertheit

Sehr wichtig für die Prüfung.

## Unmerklichkeit

**Kann ein Mensch die Veränderung wahrnehmen?**

```text
Originalbild       Stego-Bild
    🖼️                🖼️
     │                 │
     └──── Auge 👁️ ────┘
             │
             ▼
     "Sieht gleich aus."

        → unmerklich
```

## Undetektiertheit

**Kann ein Computer die Veränderung erkennen?**

```text
             Stego-Bild
                 │
                 ▼
        statistische Analyse
                 │
                 ▼
            Computer 💻
                 │
                 ▼
       "Hier stimmt etwas
             nicht!"

        → detektierbar
```

Ein Bild kann also gleichzeitig:

```text
für Menschen     → unauffällig ✅
für Maschinen    → auffällig  ❌
```

sein.

---

# 7. Was ist Steganographie?

Bei der Steganographie wird eine geheime Nachricht in einem **Cover-Objekt** versteckt. Typische Cover sind Bilder, Audio, Texte, Dateisysteme oder Netzwerkressourcen.

```text
             geheime Nachricht
                    │
                    ▼
        ┌───────────────────────┐
        │       COVER           │
        │                       │
        │ Bild / Audio / Text   │
        │ Netzwerk / Dateisystem│
        └───────────────────────┘
                    │
                    ▼
             STEGO-OBJEKT
                    │
                    ▼
           sieht normal aus
```

---

# 8. Steganographie muss nicht digital sein

Steganographie gab es bereits vor Computern.

Beispiel:

```text
Heute
Ist
Lernen
Für
Experten
```

Erste Buchstaben:

```text
H
I
L
F
E
│
▼
HILFE
```

Die sichtbare Nachricht ist ein normaler Text.

Die versteckte Nachricht lautet:

> **HILFE**

---

# 9. Dual Use

**Dual Use = dieselbe Technologie kann legitim oder missbräuchlich eingesetzt werden.**

```text
                  STEGANOGRAPHIE
                        │
             ┌──────────┴──────────┐
             │                     │
             ▼                     ▼
        legitime Nutzung      Missbrauch
             │                     │
     ┌───────┴───────┐       ┌─────┴──────┐
     │               │       │            │
 Journalismus     Schutz   verdeckte    Umgehung
 sensibler Daten          Übertragung   von Grenzen
```

Informationsverstecken wird deshalb als **Dual-Use-Technologie** betrachtet.

### Prüfungsantwort

> Eine Dual-Use-Technologie kann sowohl für legitime als auch für schädliche Zwecke verwendet werden. Steganographie kann beispielsweise sensible Kommunikation schützen, aber auch zur unerwünschten verdeckten Kommunikation eingesetzt werden.

---

# 10. Gegenmaßnahmen

Gegenmaßnahmen sollen Informationsverstecken:

```text
ERKENNEN
   │
   ├────────► EINSCHRÄNKEN
   │
   └────────► VERHINDERN
```

Beispiele:

```text
verdächtige Kommunikation
          │
          ▼
      Analyse 🔍
          │
    ┌─────┴─────┐
    │           │
 normal     verdächtig
                │
                ▼
        blockieren / ändern
```

Weitere Ziele sind beispielsweise, Kapazität oder Bandbreite zu reduzieren und gemeinsam genutzte Ressourcen abzusichern.

---

# 11. Das Wettrüsten

Versteckverfahren und Gegenmaßnahmen entwickeln sich gegenseitig weiter.

```text
┌───────────────────┐
│ neues Stego-      │
│ Verfahren         │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Detektor erkennt  │
│ das Verfahren     │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Verfahren wird    │
│ verbessert        │
└─────────┬─────────┘
          │
          ▼
┌───────────────────┐
│ Detektor wird     │
│ verbessert        │
└─────────┬─────────┘
          │
          └──────────────► zurück zum Anfang
```

Dieses fortlaufende Wechselspiel bezeichnet die Unterlage als technisches **Arms Race**.

---

# 12. Steganographische Speicherung vs. Übertragung

## Speicherung 💾

```text
Geheimnis
    │
    ▼
┌─────────────┐
│ Festplatte  │
│   🗂️        │
│ Geheimnis   │
│ versteckt   │
└─────────────┘
```

Die Information bleibt versteckt **an einem Ort gespeichert**.

## Übertragung 📡

```text
Alice                                    Bob
  │                                       │
  │     Bild mit versteckten Daten        │
  ├──────────────────────────────────────>│
  │                                       │
```

Die Information wird versteckt **von einem Ort zum anderen transportiert**.

### Merksatz

```text
Speicherung  = versteckt ABLEGEN
Übertragung  = versteckt VERSCHICKEN
```

---

# 13. Bildsteganographie

Bilder eignen sich gut als Cover, weil sie viele Daten und Redundanz besitzen und Menschen kleine Veränderungen oft nicht zuverlässig erkennen.

Ein Pixel kann vereinfacht drei Werte besitzen:

```text
             PIXEL
               │
       ┌───────┼───────┐
       │       │       │
       ▼       ▼       ▼
      ROT     GRÜN     BLAU
       R       G        B
```

Also:

```text
RGB = Rot + Grün + Blau
```

Kleine Veränderungen einzelner Werte können genutzt werden, um Informationen zu verstecken.

---

# 14. Rasterformat vs. Palettenformat

## Rasterformat

Jeder Pixel besitzt direkt seine Farbwerte.

```text
Pixel 1 → RGB(255, 0, 0)
Pixel 2 → RGB(250, 0, 0)
Pixel 3 → RGB(0, 255, 0)
Pixel 4 → RGB(0, 0, 255)
```

Beispiele:

**BMP, PNG, TIFF**

## Palettenformat

Es gibt zuerst eine Farbtabelle:

```text
FARBTABELLE

Index 0 → 🔴 Rot
Index 1 → 🟢 Grün
Index 2 → 🔵 Blau
```

Die Pixel speichern dann nur:

```text
Bild:

0 0 1 1
0 2 2 1
0 2 1 1
```

`0` bedeutet Rot, `1` Grün usw.

GIF ist ein typisches Beispiel. PNG kann ebenfalls eine Palette verwenden.

---

# 15. JPEG – einfach visualisiert

JPEG verwendet unter anderem die **Discrete Cosine Transform (DCT)** und verlustbehaftete Kompression.

Den Ablauf kannst du dir so merken:

```text
RGB-Bild
   │
   ▼
YCbCr
   │
   ▼
Bild in Blöcke teilen
   │
   ▼
DCT
   │
   ▼
Quantisierung
   │
   ▼
weitere Kompression
   │
   ▼
JPEG
```

## YCbCr

```text
            YCbCr
              │
      ┌───────┼────────┐
      │       │        │
      ▼       ▼        ▼
      Y       Cb       Cr
      │       │        │
 Helligkeit   └──┬─────┘
                 │
                 ▼
          Farbinformation
```

**Merke:**

```text
Y     = Helligkeit
Cb/Cr = Farbinformation
```

Die Chrominanzinformationen können mit geringerer Auflösung gespeichert werden.

---

# 16. LSB-Steganographie ⭐⭐⭐

**LSB = Least Significant Bit**

Also das **niedrigstwertige Bit**.

Beispiel:

```text
Pixelwert:

1 0 1 1 0 1 1 0
              └─┬─┘
                │
               LSB
```

Wir wollen die geheime **1** speichern.

Vorher:

```text
10110110
       ↑
       0
```

Nachher:

```text
10110111
       ↑
       1
```

Also:

```text
10110110
       │
       │ geheimes Bit = 1
       ▼
10110111
```

Der Wert wurde nur sehr wenig verändert.

LSB-Steganographie verwendet genau dieses niedrigstwertige Bit eines Farb- oder Bildwertes zur Einbettung.

## Mehrere Bits verstecken

Geheime Nachricht:

```text
1 0 1
```

Drei Pixel:

```text
Pixel 1: 10110110
Pixel 2: 11001011
Pixel 3: 10011010
```

LSBs ersetzen:

```text
                 Geheim
                   ↓
Pixel 1: 10110111 → 1
Pixel 2: 11001010 → 0
Pixel 3: 10011011 → 1
```

Auslesen:

```text
letzte Bits:

1 + 0 + 1

    ↓

   "101"
```

---

# 17. Warum kann LSB erkannt werden?

Natürliche Bilder besitzen häufig relativ glatte Übergänge.

Durch viele LSB-Manipulationen können statistische Auffälligkeiten entstehen.

```text
Natürlich:

120 → 121 → 122 → 123 → 124
       relativ glatt


Manipuliert:

120 → 123 → 120 → 125 → 122
        mehr Auffälligkeiten
```

Vereinfacht gesagt kann ein Detektor fragen:

```text
"Sehen diese Pixelwerte noch natürlich aus?"
                  │
          ┌───────┴───────┐
          │               │
         JA              NEIN
          │               │
       normal         möglicherweise
                      Steganographie
```

---

# 18. Covert Channel

Ein **Covert Channel** benutzt eine Ressource zur Kommunikation, die eigentlich **nicht dafür vorgesehen ist**.

```text
Normale Funktion einer Ressource
             │
             │ wird zweckentfremdet
             ▼
      geheime Kommunikation
```

Beispiele aus der Unterlage:

```text
🔊 Schall
💡 Licht
💾 Speicher
💻 Cache-Verhalten
💡 Geräteaktivität
```

Physikalische verdeckte Kanäle können beispielsweise Schall oder Licht verwenden.

---

# 19. Storage Channel vs. Timing Channel

## Storage Channel

Die Information steckt in einem **Datenwert oder einer Eigenschaft**.

```text
Netzwerkpaket
┌──────────────────────────────┐
│ Header │ Feld = 1 │ Daten    │
└──────────────────────────────┘
             ↑
             │
       geheimes Bit
```

Zum Beispiel:

```text
Feld = 0 → geheime 0
Feld = 1 → geheime 1
```

### Denkregel

> **Storage = WO steckt das Bit? → in einem Wert**

---

## Timing Channel

Hier steckt die Information in der **Zeit**.

```text
Zeit ─────────────────────────────────────►

Paket        Paket                  Paket
  ●────────────●──────────────────────●
       kurz              lang
        │                 │
        ▼                 ▼
        0                 1
```

Zum Beispiel:

```text
kurzer Abstand = 0
langer Abstand = 1
```

Geheime Nachricht:

```text
kurz | lang | lang | kurz

  0  |  1   |  1   |  0

        = 0110
```

## Der wichtigste Unterschied

```text
STORAGE CHANNEL
      │
      ▼
"Ich verändere WAS übertragen wird."


TIMING CHANNEL
      │
      ▼
"Ich verändere WANN übertragen wird."
```

---

# 20. Shared Resource Methodology

**Shared Resource = gemeinsam genutzte Ressource**

Die Grundidee:

```text
┌───────────────┐
│ Covert Sender │
└───────┬───────┘
        │
        │ verändert
        ▼
┌─────────────────┐
│ GEMEINSAME      │
│ RESSOURCE       │
└────────┬────────┘
         │
         │ beobachtet
         ▼
┌─────────────────┐
│ Covert Receiver │
└─────────────────┘
```

### Beispiel

```text
Sender
  │
  │ schreibt/verändert
  ▼
┌─────────────┐
│ Speicher X  │
└──────┬──────┘
       │
       │ liest/beobachtet
       ▼
    Empfänger
```

Vereinfacht:

```text
Ressource verändert     → 1
Ressource nicht verändert → 0
```

Die Shared Resource Matrix untersucht entsprechend, welche Prozesse gemeinsam auf Ressourcen zugreifen können.

---

# 21. Overt vs. Covert

Die Wörter kannst du dir so merken:

```text
OVERT  = OFFEN / SICHTBAR
COVERT = VERDECKT / GEHEIM
```

## Visualisierung

```text
                 SICHTBARE KOMMUNIKATION

┌──────────────┐                         ┌──────────────┐
│ Overt Sender │ ──────────────────────► │Overt Receiver│
└──────────────┘                         └──────────────┘
        │
        │ versteckte Information
        ▼
┌──────────────┐                         ┌──────────────┐
│Covert Sender │ ══════════════════════► │Covert       │
│              │   geheimer Kanal        │Receiver     │
└──────────────┘                         └──────────────┘
```

Nach außen sieht man nur die normale Kommunikation.

Innerhalb oder mithilfe dieser Kommunikation existiert zusätzlich ein verdeckter Informationsfluss.

---

# 22. Warden 🛡️

Stell dir den Warden wie einen **Sicherheitskontrolleur** vor.

```text
Sender
  │
  │ Netzwerkverkehr
  ▼
┌──────────────────┐
│    WARDEN 🛡️     │
│                  │
│ "Ist hier etwas  │
│  versteckt?"     │
└────────┬─────────┘
         │
         ▼
     Empfänger
```

Seine Aufgabe ist vereinfacht:

```text
Kommunikation
      │
      ▼
   überwachen
      │
      ▼
Auffälligkeiten suchen
      │
      ▼
verdeckte Kommunikation
erkennen / verhindern
```

---

# 23. Normalizer

Ein Normalizer bringt Daten in eine **normale bzw. standardisierte Form**.

Beispiel:

Ein Feld darf eigentlich immer `000` sein.

Der geheime Sender verwendet:

```text
101
```

um Informationen zu verstecken.

Der Normalizer macht:

```text
vorher:

101
 │
 ▼
NORMALIZER
 │
 ▼
000

nachher
```

Die versteckte Information wurde dadurch zerstört.

### Warden vs. Normalizer

```text
WARDEN
  │
  └──► "Ich kontrolliere."


NORMALIZER
  │
  └──► "Ich standardisiere/verändere."
```

---

# 24. Steganographic Cost

Vereinfacht:

> **Wie stark muss ich etwas verändern, damit ich meine geheime Information übertragen kann?**

Beispiel eines Timing Channels:

Normal:

```text
20 ms   21 ms   19 ms   20 ms
```

Verdeckter Kanal:

```text
20 ms   500 ms   20 ms   800 ms
```

Die Veränderung ist sehr groß.

```text
große Veränderung
        │
        ▼
hoher steganographic cost
```

Kleine Veränderung:

```text
20 ms → 22 ms
```

```text
kleine Veränderung
        │
        ▼
geringerer steganographic cost
```

---

# 25. Stealthiness / Covertness

Hier lautet die Frage:

> **Wie unauffällig ist die versteckte Kommunikation?**

```text
                Stego-Verfahren
                      │
             ┌────────┴────────┐
             │                 │
             ▼                 ▼
       sieht normal aus     auffällig
             │                 │
             ▼                 ▼
          hohe              geringe
       Stealthiness       Stealthiness
```

### Cost vs. Stealthiness

```text
Steganographic Cost
        │
        └──► Wie stark verändere ich etwas?


Stealthiness
        │
        └──► Wie auffällig ist das Ergebnis?
```

---

# 26. Hiding Patterns

Es gibt viele verschiedene Steganographie-Verfahren.

Ohne Ordnung:

```text
Methode A
Methode B
Methode C
Methode D
Methode E
Methode F
...
```

Das wird schnell unübersichtlich.

Hiding Patterns gruppieren ähnliche **Grundideen**:

```text
                   Hiding Patterns
                         │
          ┌──────────────┼──────────────┐
          │              │              │
          ▼              ▼              ▼
       Muster A       Muster B       Muster C
          │              │              │
       ┌──┴──┐        ┌──┴──┐        ┌──┴──┐
       A1   A2        B1   B2        C1   C2
```

Dadurch kann man Verfahren leichter:

```text
beschreiben
    +
ordnen
    +
vergleichen
```

---

# 27. Network Environment Learning

Grundidee:

> **Bevor ich mich verstecke, muss ich wissen, was in diesem Netzwerk normal ist.**

```text
            Netzwerk
               │
               ▼
        beobachten 👀
               │
               ▼
        normales Verhalten
             lernen
               │
               ▼
     verdeckten Kanal daran
            anpassen
```

### Beispiel

Normaler Netzwerkverkehr:

```text
18 ms
22 ms
20 ms
24 ms
19 ms
```

Der Covert Sender erkennt:

```text
"Ungefähr 18–24 ms ist normal."
```

Dann wäre folgendes möglicherweise auffällig:

```text
20 ms
900 ms  ← ???
21 ms
800 ms  ← ???
```

Die Idee des Environment Learning ist also:

```text
LERNEN
  ↓
ANPASSEN
  ↓
WENIGER AUFFALLEN
```

---

# 28. Mikroprotokolle

Auch ein geheimer Kanal braucht Organisation.

Angenommen, wir übertragen:

```text
101101001010
```

Woher weiß der Empfänger:

* Wo beginnt die Nachricht?
* Wo endet sie?
* Welche Reihenfolge ist richtig?
* Fehlen Daten?

Dafür kann ein **Mikroprotokoll** eingesetzt werden.

Vereinfacht:

```text
┌───────┬───────────────┬──────┐
│ START │ GEHEIME DATEN │ ENDE │
└───────┴───────────────┴──────┘
```

Oder:

```text
┌─────┬────────┬──────────┐
│ Nr. │ Länge  │ Nutzdaten│
├─────┼────────┼──────────┤
│  1  │   6    │ 101101   │
└─────┴────────┴──────────┘
```

**Merksatz:**

> Mikroprotokoll = kleines Protokoll zur Organisation der verdeckten Kommunikation.

---

# 29. Replication Studies 🔬

**Replication = Wiederholung einer wissenschaftlichen Untersuchung.**

Forscher A behauptet:

```text
Experiment
    │
    ▼
"Mein Verfahren schafft 100 Bit/s."
```

Dann kommt Forscher B:

```text
gleiches / vergleichbares Experiment
                │
                ▼
            Ergebnis?
          ┌─────┴─────┐
          │           │
        ähnlich      anders
          │           │
          ▼           ▼
 Ergebnis wird     Ergebnis muss
   gestützt        hinterfragt werden
```

Warum ist das wichtig?

```text
Eine Studie
    │
    ▼
interessantes Ergebnis
    │
    ▼
Wiederholung
    │
    ▼
Ist das Ergebnis zuverlässig?
```

---

# 30. Wasserzeichen vs. Steganographie

Das ist ebenfalls ein wichtiger Unterschied.

## Steganographie

```text
       Bild
        │
        │ enthält
        ▼
"Treffen um 18 Uhr"
```

Die Nachricht hat **nichts mit dem Bild selbst zu tun**.

## Wasserzeichen

```text
       Bild
        │
        │ enthält
        ▼
"Copyright Max Mustermann"
```

Die Information bezieht sich auf das **Bild, seinen Eigentümer, seine Herkunft oder seinen Empfänger**.

### Merksatz

```text
Steganographie
      ↓
beliebige geheime Nachricht


Wasserzeichen
      ↓
Information ÜBER das Cover
```

---

# 31. Robustes vs. fragiles Wasserzeichen

## Robustes Wasserzeichen 💪

Es soll Veränderungen **überleben**.

```text
Bild + Wasserzeichen
        │
        ▼
   verkleinern
        │
        ▼
   komprimieren
        │
        ▼
 Format ändern
        │
        ▼
Wasserzeichen noch da ✅
```

Das ist die Grundidee robuster Wasserzeichen.

## Fragiles Wasserzeichen 🧩

Es soll helfen zu erkennen:

> **Wurde der Inhalt manipuliert?**

```text
Original
   │
   ▼
Wasserzeichen vorhanden
   │
   ▼
Manipulation
   │
   ▼
Wasserzeichen reagiert / Prüfung schlägt an
   │
   ▼
"Der Inhalt wurde verändert."
```

Fragile Wasserzeichen dienen damit insbesondere der **Integritätsprüfung**.

---

# 32. Textsteganographie

Informationen können auch in Texten versteckt werden.

Die Unterlage unterscheidet unter anderem:

```text
                 TEXTSTEGANOGRAPHIE
                         │
            ┌────────────┼────────────┐
            │            │            │
            ▼            ▼            ▼
        semantisch    grafisch     geometrisch
            │            │            │
         Sprache       Aussehen      Position
```

## Semantisch

Man verändert die **sprachliche Auswahl**.

```text
groß  ↔ riesig
Auto  ↔ Wagen
schnell ↔ rasch
```

Die Auswahl eines bestimmten Synonyms kann beispielsweise ein geheimes Bit darstellen.

## Grafisch

Man verändert das **Aussehen**.

```text
Hallo Welt

H = normale Schrift  → 0
H = andere Schrift   → 1
```

## Geometrisch

Man verändert die **Position oder Abstände**.

```text
normal:

Hallo Welt


verändert:

Hallo   Welt
     ↑
größerer Abstand
```

---

# 33. Stego-Dateisysteme

Es gibt zwei grundlegende Möglichkeiten:

```text
Möglichkeit 1:

DATEISYSTEM
    │
    └──► enthält geheime Nachricht


Möglichkeit 2:

sichtbares Dateisystem
    │
    └──► enthält
           │
           ▼
       geheimes
       Dateisystem
```

Diese beiden Varianten werden in der Unterlage ausdrücklich unterschieden.

Das Problem:

```text
Dateisystem
    │
    ├── Datei erstellen
    ├── Datei löschen
    ├── Datei verändern
    └── Speicher überschreiben
              │
              ▼
      geheime Daten könnten
         zerstört werden
```

Deshalb sind hier **Robustheit und Redundanz** besonders wichtig.

---

# 34. Die komplette Landkarte 🧠

```text
                         INFORMATION HIDING
                                │
          ┌─────────────────────┼─────────────────────┐
          │                     │                     │
          ▼                     ▼                     ▼
    Kryptographie          Steganographie         Wasserzeichen
          │                     │                     │
          ▼                     ▼                     ▼
 Inhalt unlesbar        Existenz verstecken     Info über Cover
                                │
          ┌─────────────────────┼─────────────────────┐
          │                     │                     │
          ▼                     ▼                     ▼
       Bilder                 Texte              Dateisysteme
          │
          └─────────────────────┐
                                ▼
                       Network Steganography
                                │
                   ┌────────────┴────────────┐
                   │                         │
                   ▼                         ▼
            Storage Channel           Timing Channel
                   │                         │
                   ▼                         ▼
              Datenwerte                    Zeit
                   │                         │
                   └────────────┬────────────┘
                                ▼
                         Covert Channel
                                │
             ┌──────────────────┼─────────────────┐
             │                  │                 │
             ▼                  ▼                 ▼
      Shared Resources        Warden         Normalizer
             │                  │                 │
             ▼                  ▼                 ▼
       Kommunikation        erkennen        standardisieren/
       ermöglichen          überwachen       verändern
```

---

# 35. Prüfungs-Mindmap

```text
                         INFORMATION HIDING
                                │
        ┌───────────────────────┼────────────────────────┐
        │                       │                        │
        ▼                       ▼                        ▼
    GRUNDLAGEN             STEGANOGRAPHIE          NETWORK STEGO
        │                       │                        │
   ┌────┼────┐            ┌─────┼─────┐          ┌──────┼──────┐
   │    │    │            │     │     │          │      │      │
   ▼    ▼    ▼            ▼     ▼     ▼          ▼      ▼      ▼
Kapaz. Band. Robust.     Bild   Text  Datei    Storage Timing Shared
                                                  │      │    Resource
                                                  └──┬───┘
                                                     │
                                                     ▼
                                              Covert Channel
                                                     │
                                       ┌─────────────┼─────────────┐
                                       ▼             ▼             ▼
                                    Warden       Normalizer      Patterns
```

---

# 36. Die wichtigsten Gegensatzpaare

```text
┌──────────────────────┬─────────────────────────────┐
│ Begriff A            │ Begriff B                   │
├──────────────────────┼─────────────────────────────┤
│ Kapazität            │ Bandbreite                  │
│ Wie viel?            │ Wie schnell?                │
├──────────────────────┼─────────────────────────────┤
│ Kryptographie        │ Steganographie              │
│ Inhalt verstecken    │ Existenz verstecken         │
├──────────────────────┼─────────────────────────────┤
│ Storage Channel      │ Timing Channel              │
│ Daten verändern      │ Zeit verändern              │
├──────────────────────┼─────────────────────────────┤
│ Overt                │ Covert                      │
│ offen                │ verdeckt                    │
├──────────────────────┼─────────────────────────────┤
│ Unmerklichkeit       │ Undetektiertheit            │
│ Mensch erkennt?      │ Maschine erkennt?           │
├──────────────────────┼─────────────────────────────┤
│ Steganographic Cost  │ Stealthiness                │
│ Stärke der Änderung  │ Auffälligkeit               │
├──────────────────────┼─────────────────────────────┤
│ robustes Wasserz.    │ fragiles Wasserz.           │
│ Änderung überleben   │ Änderung erkennen           │
└──────────────────────┴─────────────────────────────┘
```

---

# 37. Prüfungsstrategie: Definition → Beispiel → Unterschied

Wenn der Prüfer einen Begriff nennt, benutze immer dieses Schema:

```text
             PRÜFUNGSFRAGE
                   │
                   ▼
        1. WAS IST DAS?
             Definition
                   │
                   ▼
        2. WIE FUNKTIONIERT ES?
             Erklärung
                   │
                   ▼
        3. BEISPIEL?
          konkretes Beispiel
                   │
                   ▼
        4. UNTERSCHIED?
       ähnlichen Begriff abgrenzen
```

## Beispiel: Timing Channel

**1. Definition**

> Ein Timing Channel überträgt versteckte Informationen durch zeitliche Eigenschaften einer Kommunikation.

**2. Erklärung**

> Dabei werden zum Beispiel die Abstände zwischen Netzwerkpaketen verändert.

**3. Beispiel**

> Ein kurzer Paketabstand könnte für 0 und ein langer Paketabstand für 1 stehen.

**4. Abgrenzung**

> Im Gegensatz zum Storage Channel wird die Information also nicht durch einen Datenwert, sondern durch das zeitliche Verhalten übertragen.

---

# 38. Ultra-Kurzfassung vor der Prüfung 🚀

```text
INFORMATION HIDING
│
├─ Kryptographie → Inhalt unlesbar
├─ Steganographie → Existenz verstecken
├─ Wasserzeichen → Information über Cover
└─ Covert Channel → unerwarteten Kanal benutzen


KAPAZITÄT
└─ Wie viel?


BANDBREITE
└─ Wie schnell?


LSB
└─ geheime Daten in niedrigstwertigen Bits


STORAGE CHANNEL
└─ Daten/Eigenschaften verändern


TIMING CHANNEL
└─ zeitliches Verhalten verändern


SHARED RESOURCE
└─ Sender verändert → Empfänger beobachtet


OVERT
└─ offene Kommunikation


COVERT
└─ versteckte Kommunikation


WARDEN
└─ überwacht / erkennt / verhindert


NORMALIZER
└─ standardisiert/verändert Daten


STEGANOGRAPHIC COST
└─ Wie stark verändert die Einbettung den Träger?


STEALTHINESS
└─ Wie unauffällig ist die Methode?


HIDING PATTERNS
└─ ähnliche Verfahren systematisch gruppieren


NETWORK ENVIRONMENT LEARNING
└─ Umgebung lernen → Verhalten anpassen


MIKROPROTOKOLL
└─ organisiert den verdeckten Kanal


REPLICATION STUDY
└─ wissenschaftliches Ergebnis wiederholen und prüfen
```

## Der wichtigste Gesamtzusammenhang

```text
        GEHEIME INFORMATION
                │
                ▼
        Wie verstecke ich sie?
                │
                ▼
          STEGANOGRAPHIE
                │
                ▼
        Wo verstecke ich sie?
       ┌────────┼─────────┐
       ▼        ▼         ▼
      Bild     Text     Netzwerk
                          │
                          ▼
                    Covert Channel
                          │
                  ┌───────┴───────┐
                  ▼               ▼
               Storage          Timing
                  │               │
                  └───────┬───────┘
                          ▼
                 möglichst unauffällig
                          │
                          ▼
                      WARDEN
                          │
                          ▼
                  versucht den Kanal
                     zu erkennen
```

**Ein Satz für den Kopf:**

> **Steganographie versucht Informationen unauffällig zu verstecken; bei Network Steganography geschieht dies innerhalb von Netzwerkkommunikation, zum Beispiel durch Veränderungen von Daten oder Timing, während Gegenmaßnahmen versuchen, diese verdeckte Kommunikation zu erkennen oder zu verhindern.**

Die zentralen Zusammenhänge deiner Unterlage umfassen genau diese Aspekte: Steganographie, Kapazität und Bandbreite, Robustheit und Undetektiertheit, Bild- und Textsteganographie, verdeckte Kanäle, Dateisysteme sowie Gegenmaßnahmen.
