# 01a Datenformate 

## 1. BMP - Bitmap Picture

- Standardformat des Windows-Betriebssystems
- kann auf verschiedenen Bildschirmen oder Druckern
- es können auch monochrome oder Graustufenbilder kodiert werden
- wird für die Hintergrundbilder der Arbeitsoberfläche in Windows verwendet

### *Datenstruktur*

Eine Windows 1.0 BMP-Datei besitzt nur einen Header gefolgt von den Bitmap-Daten, Windows 4.0-Versionen bestehen zusätzlich noch aus einem Datei-Header und einer Farbtabelle. Der Aufbau einer BMP-Datei sieht also folgendermaßen aus:

![bild1](./bilder/bild1.PNG)

### *File Header* 

- 14 Bytes lang
- enthält eine Dateiidentifizierung und Angaben zur Dateigröße in Bytes

Weiters folgen Strukturen ohne Daten, die von Applikationen genutzt werden, sobald der Header eingelesen wird.

### *Bitmap Header* 

- seit Windows 95 108 Bytes lang
- enthält:
  - Informationen zu den Bitmap-Daten
  - Angaben über Breite und Höhe der Datei in Pixeln, die Anzahl der Farbpaletten und die Datentiefe
  - Informationen zur Kompression (z.B. unkomprimiert oder RLE)
  - Informationen zur Größe der gespeicherten Bitmap in Bytes
  - die verwendeten Farben

Mit jeder Windows-Version sind neue Header- Felder hinzugekommen, wie zum Beispiel mit Windows 95 die vier Masken-Felder (Rot, Grün, Blau, Alpha). Von Adobe Photoshop werden jedoch Informationen zu z.B. Color Management oder auch Alphakanälen beim BMP-Format nicht unterstützt. 

### *Color Palette* 

Die Farbtabelle ist optional und hängt von der Datentiefe des Bildes ab - sie ist nur bei 1-, 4-, und 8- Bit
Datentiefe vorhanden. 

### *Bitmap Data* 

Die Bitmap-Daten enthalten die eigentlichen Bildinformationen - für jedes Pixel werden die Farbwerte
gespeichert. 



### Kompression

Das BMP-Format benutzt meist **keine Kompression** oder eine Art von RLE (Runlength Encoding).

### Speicheroptionen 

Beim Speichern im BMP-Format sind nur sehr wenige Angaben zu treffen, es ist nur das **Dateiformat**
sowie die **Farbtiefe** zu wählen. Der einfache Speicherdialog in Photoshop sieht folgendermaßen aus: 

![bild2](./bilder/bild2.PNG)

### Vorteile/Nachteile

- kann praktisch von allen Programmen ohne zusätzliche Plugins gelesen werden
- absolut verlustfrei (keine bzw. geringe Kompression)

### Anwendungsgebiete

- Standard-Format des Windows-Betriebssystems
- eignet es sich für alle Bereiche in denen gar nicht bzw. verlustfrei komprimierte Grafiken benötigt werden (z.B. Computerspiele)

<hr>

## 2. Weitere Formate

### 2.1 GIF (Graphics Interchange Format)

- wurde speziell für den Gebrauch im Internet entwickelt und 
- stellt neben JPEG das wohl am meisten genutzte Dateiformat im WWW dar
- basiert auf dem verlustfreien LZW-Kompressionsverfahren
- speichert nur eine Farbtiefe von 8 Bit. 

### 2.2  JPEG (Joint Photographic Experts Group)

- Pixelgrafik-Format 
- für die Anwendung im Internet geeignet
- ähnelt in seinen Eigenschaften dem GIF-Format 
- kann jedoch bis zu 16,7 Mio. Farben darstellen
- unterliegt keinen Copyright Einschränkungen

### 2.3 PNG (Portable Network Graphics)

- erweiterbares, portables, effektiv und verlustfrei komprimierendes Bildformat
- lizenzfrei und unterstützt indizierte Farben, Graustufen und Truecolor
- PNG kann Transparenz und Interlacing darstellen. 

### 2.4 PSD (Photoshop Native Format)

- programmspezifische Dateiformat von Photoshop

### 2.5 TIFF (Tagged Image File Format)

- eines der flexibelsten Rastergrafik-Formate
- wurde entwickelt von Aldus, Microsoft und Hardware-Herstellern

## 3. Vergleich zwischen den einzelnen Formaten

| Format    | Kompression     | Transparenz |
| --------- | --------------- | ----------- |
| Bitmap    | ohne            | nein        |
| GIF       | verlustfrei     | ja          |
| JPEG      | verlustbehaftet | nein        |
| PNG       | verlustfrei     | ja          |
| Photoshop | ohne            | ja          |
| TIFF      | ohne            | ja          |

## 4. Hybride Grafikformate

#### EPS - Encapsulated PostScript

- Page Description Language (PDL)
- die Daten werden mit einem Teil des Befehlssatzes von PostScript beschrieben und schließlich "eingebettet"

#### PDF - Portable Document Format

- Dateiformat, das Dokumente mit Bild und Text enthält und auf PostScript basiert. 
- gewährleistet plattformunabhängigen Austausch von Dokumenten

## 5. Audio-Dateiformate

### Wav - "WAVE File Format"

- Untergruppe der Microsoft RIFF-Spezifikation (RIFF = Ressource Interchange File Format)
- Quasi-Standard in der digitalen Soundproduktion
- kann verschieden Arten von Daten beinhalten
- eine WAVE Datei besteht aus drei Datenblöcken (=> Chunks)

1. RIFF-Chunk
2. FORMAT-Chunk
3. DATA-Chunk

**PCM** (Pulse Code Modulation) unkomprimiert
**DPCM** (Differential Pulse Code Modulation) nicht das Signal wird codiert, sondern die
Differenz zur vorherigen Abtastung
**ADPCM** (Adaptive Differential Pulse Code Modulation) Verbessertes DPCM-Modell
durch die Einführung eines Prädiktionswertes

### MP3 - "MPEG-Audio Layer 3"

MPEG-Audio wurde in Layern realisiert, wobei sich diese in der Komplexität des
Kompressionsalgorithmus und im Grad der Kompression unterscheiden. MPEG-1
Layer 3, besser bekannt als MP3, ist der Effizienteste, da hier zusätzlich eine
Entropiekodierung (Huffman) vorgenommen wird.

- Verwendung für fast alle Audioanwendungen über Internet
- Streamingfähig

### OGG - Ogg Vorbis

- neuer OpenSource-Algorithmus zur Reduktion der Datenmenge bei Audiofiles
- Konkurrent von MP3 im Bereich Audiostreaming 
- erreicht bessere Kompressionsergebnisse durch die Verwendung des FLAC (free lossless audio
  codec) Verfahrens.

### AC-3 - "Dolby Digital Audio Code 3"

- 5.1 System, das aus 5 Vollbereichskanälen – Front R/L, Center und Surround R/L – und
  einem LFE-Kanal (Low Frequency Effects) Kanal besteht
- Audiodaten werden ca. mit dem Faktor 8 komprimiert. 
- ähnlichen Kompressionsmethoden wie MP3
- alle Kanäle stehen einzeln und im vollen Frequenzumfang zur Verfügung

### WMA - "Windows Media Audio"

- proprietärer Audio-Codec von Microsoft
- Teil der Windows Media Plattform
- verlustbehafteter Codec
- unterstützt bis zu 24 bit/96 KHz 
- variable Bitrate von bis zu 768 kb/s 
- Surround-Ton mit bis zu 7.1 Kanälen

## 6. Video-Formate

### <u>Dateiformate Video:</u> 

#### Mpg

- können Video und/oder Audio-Daten enthalten
- sind aufgrund der Interframe-Kompression nicht zum Editieren
  geeignet, können aber in verschiedenen Videobearbeitungsprogrammen
  zumindest geöffnet werden
- Eine Ausnahme bildet hier das I-Frame-Only
  Verfahren. Dabei handelt es sich um eine MPEG-Variante, bei der nur
  Intraframe-kodiert wird, also die Einzelbilder unabhängig komprimiert werden

#### Vob (Video Objects)

- wird für DVDs verwendet
- kann Menüs, Titel oder MPEG-2 Video- und Audiodaten sowie
  Navigationselemente einer DVD enthalten.
- nicht wirklich editierbar

#### Gif (Graphics Interchange Format)

- wird vorrangig für Internetanwendungen eingesetzt 
- innerhalb einer Datei können mehrere Bilder gespeichert werden, die dann in
  entsprechenden Programmen (z.B. Webbrowser) nacheinander angezeigt
  werden
- kann jeweils nur 256 Farben enthalten und darstellen
- eignet sich dieses Format nicht für Realbilder 
- kann keine Audiodaten speichern

### <u>Container-Formate Video</u> 

#### Avi (Audio Video interleaved)

- sehr offenes Format 
- beschreibt eigentlich nur, dass es sich bei einer Datei grundsätzlich um eine Videodatei handelt
- Der Inhalt kann aus Video- und Audiodaten bestehen
- Avi-Dateien können unkomprimiertes Video enthalten oder komprimierte Videodaten.

#### Mov (Quicktime Movie)

- Apple-Format 
- wird auch im Windows-Bereich häufig eingesetzt

#### Wmv (Windows Media Video)

- sowohl ein Multimedia- als auch ein Streaming Format

#### ASF (Advanced Systems Format)

- Teil des Windows Media Systems
- Dateien enthalten Mediendateien die mit Windows Media Codecs komprimiert sind

### <u>Ergänzung</u>

#### Matroska

- Containerformat für Audio- und Videodaten. Matroska-Dateien haben
- Matroska-Dateien sind oft kleiner als vergleichbare Dateien in anderen Formaten, da die Datenstruktur des Containers nur einen geringen Overhead erzeugt
- Matroska kann als Streaming-Format eingesetzt und dann mittels HTTP und RTP übertragen werden

#### AVCHD (Advanced Video Codec High Definition)

- digitales Aufzeichnungsformat für Camcorder
- verwendet den H.264/MPEG-4 AVC-Codec

<hr>

# 2.1 Kommunikation in Bits und Bytes

Ein Signal ist die deterministische Änderung einer physikalischen Größe. Ein Signal enthält demnach Information über seine Ursache und kann sie durch Zeit und Raum transportieren.

## Digitalisierung 

Die Bearbeitung von Signalen für menschliche Sinnesorgane mit den Mitteln der modernen Technik erfordert die **Digitalisierung der Signale**. Dabei werden kontinuierliche Analogsignale in eine diskrete Folge von meist ganzzahligen numerischen Werten umgewandelt. Die aus einem Analogsignal gewonnenen Werte heißen **Daten**. Stehen aufeinander folgende Daten in einer festen zeitlichen oder räumlichen Beziehung, so spricht man von ihrer zeitlichen oder räumlichen **Korrelation**.

Die Digitalisierung besteht aus zwei Schritten:

- Bei der **Diskretisierung** werden räumlich und/oder zeitlich äquidistante Messwerte des analogen Signales aufgezeichnet (Sampling)
- Die **Quantisierung** besteht in der Darstellung der Messwerte endlicher Auflösung,
  indem sie auf ganzzahlige Binärwerte abgebildet werden.

Die Nomenklatur ist dabei nicht einheitlich geregelt: 

- Bei der **Digitalisierung von Audiosignalen** bezeichnet man Genauigkeit, mit welcher
  der Messwert quantisiert wird, als **Auflösung** (Resolution), die Frequenz der Messung
  als **Abtastrate** (Sampling Rate).
- Bei der **Digitalisierung von Bilddaten** bezieht sich der Begriff Auflösung meist auf die
  räumliche Auflösung. Die Genauigkeit der Quantisierung wird als **Farb- oder Grauwertauflösung** bezeichnet

<hr>

# 2.2 Kompression von Multimediadaten

#### 1. Warum Kompression?

- Einsparung von Speicherplatz

- Einsparung von Übertragungsbandbreite

  

#### 2. Methodik der Kompression: Physikalisch/Logisch

- Physikalische Kompression
  - Reduktion der Datenmenge durch weniger redundante Kodierung
- Logische Kompression
  - Verwendung einer Tabelle von Abkürzungen für wiederkehrende Datensequenzen.

#### 3. Symmetrie

- Symmetrische Kompression
  - Zeitaufwand für Kompression und Dekompression etwa gleich.
- Kompressions-Asymmetrische Kompression
  - Kodierung deutlich aufwendiger als Dekodierung
- Dekompressions-Asymmetrische Kompression
  - Dekodierung aufwendiger als Kodierung

#### 4. Rekonstruierbarkeit

- Verlustfreie Kompression
  - Entfernt keine Informationen aus dem Datenbestand
  - Wiederherstellung der ursprünglichen Daten aus einer komprimierten Datei ist vollständig
    möglich
- Verlustbehaftete Kompression
  - Die dekomprimierte Datei ähnelt nur der Ausgangsdatei

### Prinzip und Beispiele der Datenkompression

#### 1. Verlustfreie Kompression (lossless compression)

- Das Original kann perfekt wiedergewonnen werden

#### 2. Verlustbehaftete Kompression (lossy compression)

- Es gibt einen Unterschied zwischen Originalobjekt und decodiertem Objekt
- Physiologische und wahrnehmungspsychologische Eigenschaften des Auges und des Ohres
  können ausgenutzt werden
- Höhere Kompressionsraten als bei der verlustfreien Kompression möglich (über 100:1) 

# 05 - Tipps und Tricks zum Fotografieren

![1578912027999](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912027999.png)

![1578912089714](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912089714.png)

![1578912105139](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912105139.png)

![1578912162291](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912162291.png)

![1578912190834](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912190834.png)

![1578912204970](C:\Users\besic\AppData\Roaming\Typora\typora-user-images\1578912204970.png)

# 5b - 10 besten Tricks für tolle Bilder

1. Gehen Sie immer nah an Ihr Motiv heran
2. Platzieren Sie Ihr Motiv außerhalb der Bildmitte
3. Achten Sie auf den Hintergrund
4. Beachten Sie die Tiefenschärfe, damit die Bilder noch professioneller wirken
5. Teilen Sie Landschaftsaufnahmen niemals mit dem Horizont in der Mitte
6. Erzeugen Sie spannendere Bilder durch mehrere Ebenen
7. Probieren Sie das Hoch- und das Querformat aus
8. Erzählen Sie eine Geschichte mit Ihren Fotos
9. Bei Platzmangel - Die Fotos verkleinern ohne Qualitätsverlust
10. Sichern Sie wichtige Reiseinformationen am besten gleich mit

# 5c - Richtig digital fotografieren

1. Datum und Uhrzeit richtig einstellen

2. Bildgröße einstellen

   NIEMALS Bildgröße verwenden die größer ist als der Kamerachip (Speicherplatz) (Bullshit)

   kleiner als Chipgröße fotografieren, kann am PC hochgerechnet werden (bei 4MP Sensor mit 2MP fotografiern)

3. Einstellen der JPG-Kompression

   geringste Kompression wählen

4. ISO einstellen

   niedriger ISO da sonst höheres Rauschen auftritt

5. Digital-Zoom vermeiden

   mehr Digital-Zoom -> unschärfer

6. Hochformat möglichst vermeiden

   Alle Bildschirme und Beamer haben Querformat (da baar was ned wos a handy is z.b.)

7. Serienbilder machen

   Die Wahrscheinlichkeit den richtigen MOment zu treffen ist höher 

8. Mehrfeld-Autofokus

9. Vorab Scharfstellen

10. Rote-Augen-Blitz abschalten

    sonst bringt Vorab-Scharfstellen nix

11. Langzeitbelichtung statt Blitz

    bei großen statischen Objekten

12. Automatik-Blitz abschalten

    Reichweite von nur ca. 3 Metern

13. Exakten Bildausschnitt später festlegen

    lieber in Nachbearbeitung als gleich richtig

14. Perspektive verändern

15. Bild ansehen

    nach jeder aufnahme überprüfen ob sie gelungen ist.

16. Histogramm ansehen

    um Fehler durch falsche Monitoreinstellung zu vermeiden



# LUFS

Loudness Units Full Scale

**LUFS m**

Momentane Lautheit

**LUFS s**

Lautheit in den letzten 3 Sekunden

**LUFS i**

insgesamte Lautheit

R128: Empfehlung der European Broadcast Union, die sagt das die LUFSi nicht über -23,6 sein soll

Youtube und Spotify sind es -14 LUFS

ITunes -16 LUFS

### Digitale Audiobearbeitung

**Normalisierung**

nachträgliche Verstärkung eines Signals auf Vollaussteuerung

kann Rauschen und andere unerwünschte Signale verstärken

**Hüllkurve**

beschreibt Zeitverlauf der Amplitude eines Signals

alle Programme erlauben, eine beliebige Hüllkurve zu verwenden

gibt lineare, logarithmische und exponentielle Fades

**Dynamik**

Verhältnis von max. bis min. Signalamplitude

Menschliches Empfinden hängt von dem durschnittlichen Pegel ab, deshalb sind Signale mit höherer Dynamik leiser

**Kompressor**

verringert die Dynamik eines Signals

Treshhold und Ratio sind die wichtigsten Parameter

Wird der Treshhold überschritten, kann mit Attack- und Release-Time eingestellt wie der Kompressor eingreifen soll

**Einsatzgebiete Kompressor:**

- Menschliche Stimme
- Verdichtung des Klangbildes
- Schallsignal mit konstantem Pegel erzeugen

**Limiter**

Begrenzt den einstellbaren Pegel. Verwendet um Übersteuerungen zu vermeiden

**Expander**

Erhöht die Dynamik eines Signals

**Gate**

alles unter Treshhold wird stumm gemacht (Rauschen in Redepausen unterdrücken)



**Audioschnitt**

Grundregeln

- in Signalpausen schneiden
- von einer Passage zu einer ähnlichen schneiden
- von leiser Stelle zu lauter schneiden, nicht umgekehrt
- immer an Nulldurchgängen schneiden
- an den Schnittpunkten auf ähnliche Steigung des Signals achten

Bei Sprache stimmen die Pausen im technischen Signal nicht mit Wortgrenzen überein, das erschwert die Einhaltung der Grundregeln

**Loop**

Wiederholtes Abspielen eines definierten Bereichs

**Resampling**

Veränderung der Abspielgeschwindigkeit

wird durch Weglassen bzw. Einfügen von Abtastwerten realisiert

nicht nur Zeitverlauf, sondern auch Tonhöhe wird verändert

**Timestretching**

Ändern von Dauer und Tempo bei gleichbleibender Tonhöhe

entweder duch Einfügen/Weglassen von Schwingungsperioden oder durch Einfügen/Weglassen von Signalpausen

das erste wird als TDHS bezeichnet (Time Domain Harmony Scaling)

Beispiele für Anwendungen von Timestretching sind:
• die Anpassung von vorproduzierten Drum-Loops das Tempo eines Musiktitels
• die Anpassung der Dauer eines Musiktitels an eine zu vertonende Filmszene
• die Beschleunigung des Sprechtempos für Werbe



### Bearbeitung der Klangfarbe

Klangfarbe ist die Eigenschaft, welche 2 Schallsignale mit gleicher Tonhöhe und Lautstärke unterscheidet

Fromanten sind Maxima über der Grundfrequenz

**Gestaltungsmöglichkeiten der Klangfarbe**

- sorgfältige Auswahl der akustischen Ereignisse
- Schichtung mehrerer Ereignise zu einem neuen Schallsignal
- Mikrofonierung
- Bearbeitung durch Resamplint, Filter, ...



### Filter

ermöglichen gezielte Bearbeitung des Spektrums und der Klangfabe

**wichtigsten Eigenschaften von Filtern:**

- Grenzfrequenz (Frequenz ab/bis der gesperrt wird)
- Filtercharakteristik 
- Resonanz und Güte
- Flankensteilheit( wie schnell der Übergang von Durchlassen auf Sperren ist)



**4 Filtercharakteristiken**

- Tiefpass: Lässt tiefe Frequenzen "passieren" und sperrt hohe 
- Hochpass: Lässt hohe Frequenzen passieren und sperrt niedrige
- Bandpass: lässt in einem bestimmten Bereich passieren
- Bandsprerre: lässt alles ausserhalb dieses Bereichs passieren



### Equalizer

aus mehreren Filtern zusammengesetzt und ermöglicht Bearbeitung in verschiedenen Frequenzbändern

**Einsatzgebiete:**

- Korrektur von Verzerrungen
- Abstimmung der SChallsignale für die Mischung



### Bearbeitung der Raumwirkung

**Gestaltung der Raumwirkung auf verschiedenen Ebenen**

- Wahl des Akustischen Umfelds
- Simulation einer räumlichen Szene
- Mikrofonierung
- Staffelung
- Panorama-Einstellung
- Raum-Effekte (Hall und Echo)
- Mehrkanalformate (5.1)



### Raumeffekte

#### Nachhall

wichtigste Parameter: 

- Halltyp (welcher Raum imitiert werden soll)
- Nachhallzeit
- Raumgröße
- Dichte bzw Diffustion der Mehrfachreflexion
- Mixlevel (Verhältnis zu Orginal-Sound)
- Pre-Delay (Abstand zwischen Sound und Nachhall)
- HF & LF Damp (Dämpfung hoher/niedriger Frequenzen)



#### Delay

Echo, dessen Verzögerungszeit in musikalischen Notenwerten angegeben wird

**Anwendungen: **

- Erhöhung der rythmischen Komplexität
- Hervorheben von wichtigen Sounds
- Erhöhung der Räumlichkeit

### Tiefenstaffelung

**Wahrnehmung der räumlichen Tiefe durch:**

- absolute Lautstärke
- Anteil hoher Frequenzen
- Verhältnis und Verzögerung zwischen Direktschall, Erstreflexion und Nachhalö

nahe an der Schallquelle => Direktschall mit voller Lautstärke, Reflexion und Nachhall müssen eine längere Strecke zurücklegen und sind deswegen leiser