[![Creative Commons Lizenzvertrag](https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-nc-sa/4.0/)

Dieses Werk ist lizenziert unter einer [Creative Commons Namensnennung - Nicht-kommerziell - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz](http://creativecommons.org/licenses/by-nc-sa/4.0/).

# LED-Teelicht mit Homematic-Anbindung

<img src="images/LED_Teelicht_02.jpg">

## Beschreibung:
Diese Projekt beschreibt den Aufbau eines LED Teelichts / einer LED Kerze mit Homematic-Anbindung.<br>
Ziel war, dass die Kerze im Durchmesser einem regulären Teelicht entspricht<br>
<br>

## Funktionen:
3pol Schiebeschalter auf der Batterieplatine: Ein- und Ausschalter (trennt die Batteriespannung)<br>
SW1 auf der Batterieplatine: Config-Taster & manuelles Ein- und Ausschalten der Flacker-LED<br>
SW1 auf der Hautplatine: Reset-Taster (optional)<br>
<br>

## Platinen:
<img src="images/LED_Teelicht_PCBs.jpg">
<br>

## Bauteile:
### Benötigte Bauteile für Hauptplatine:
| Anzahl | Ref | Typ | Bezeichnung |
|----|----|----|----|
1 | U1 | AVR | [ATMega 328P-AU](https://www.reichelt.de/mcu-atmega-avr-risc-32-kb-20-mhz-tqfp-32-atmega-328p-au-p119684.html)
1 | IC1 | Funkmodul | Funkmodul CC1101 868MHz
1 | IC1 | Stiftleise RM2,00 | [BKL 10120732](https://www.reichelt.de/stiftleiste-2-00mm-1x8-gerade-bkl-10120732-p262754.html)
1 | D1 | LED | 3mm Flacker-LED
1 | D2 | SMD LED rot 1206 | [RND 135-00188](https://www.reichelt.de/led-smd-1206-rot-115-mcd-rnd-135-00188-p263784.html)
1 | R1 | Widerstand 10k 0805 | [RND 0805 1 10K](https://www.reichelt.de/smd-widerstand-0805-10-kohm-125-mw-1-rnd-0805-1-10k-p183251.html)
1 | R2 | Widerstand 1k 0805 | [RND 0805 1 1,0K](https://www.reichelt.de/smd-widerstand-0805-1-0-kohm-125-mw-1-rnd-0805-1-1-0k-p183228.html)
1 | R10 | Widerstand 47Ohm 0805 | [RND 0805 1 47](https://www.reichelt.de/smd-widerstand-0805-47-ohm-125-mw-1-rnd-0805-1-47-p183165.html)
3 | C1,C2,C4 | Kondensator 100nF 0805 | [X7R-G0805 100N](https://www.reichelt.de/smd-vielschicht-keramikkondensator-100n-10-x7r-g0805-100n-p31879.html)
1 | C3 | Kondensator 10µF 0805 | [X5R-G0805 10/16](https://www.reichelt.de/smd-vielschichtkondensator-g0805-10-f-16v-x5r-g0805-10-16-p89734.html)
1 | J2 | Stiftleise RM2,00 | [MPE 150-1-004](https://www.reichelt.de/stiftleisten-2-00-mm-1x04-gerade-mpe-150-1-004-p119965.html)
1 | SW1 | SMD-Taster | Reset-Taster (optional)
<br>

### Benötigte Bauteile für Batterieplatine:
| Anzahl | Ref | Typ | Bezeichnung |
|----|----|----|----|
| 1 | BT1 | CR2477 | Batteriehalter CR2477 |
| 1 | J1 | 3pol. Schiebeschalter | [SS ESP101](https://www.reichelt.de/schiebeschalter-1x-um-stehend-print-rm-2-54-ss-esp101-p112178.html)|
| 1 | J2 | Buchsenleise RM2,00 | [MPE 156-1-004](https://www.reichelt.de/buchsenleisten-2-00-mm-1x04-gerade-mpe-156-1-004-p119985.html) |
1 | SW1 | SMD-Taster | Config-Taster
<br>

## Aufbau:
### Batterieplatine:
Das Bestücken der Batterieplatine ist relativ einfach erklärt.<br>
Man sollte die Bauteile in dieser Reihenfolge auflöten:<br>
1. CR2477 Batteriehalter einlöten<br>
2. 3pol Schiebeschalter und Config-Taster auflöten<br>
3. 4pol Buchsenleiste auf der Lötseite einlöten (steht dann nach unten)<br>
<br>

### Hauptplatine:
#### 1. Bestücken der SMD-Bauteile:
Im ersten Schritt werden die SMD-Bauteile auf der Hauptplatine bestückt.<br>
Speziell beim Atmega ist es wichtig, dass es keine Kurzschlüsse gibt.<br>
Ich empfehle nach dem Löten die Platine mit einem Leiterplattenreiniger gründlich zu reinigen (besonders im Bereicht vom Atmega).<br>
Die besten Ergebnisse habe ich damit erzielt, die Platine für ein paar Minuten in Leiterplattenreiniger einzulegen und mit einem Pinsel gründlich zu reinigen.<br>
<img src="images/LED_Teelicht_Haupt_PCB_01.jpg">
<br>

#### 2. Fuses und Bootloader flashen:
Das Flashen der Fuses und des Bootloaders erfolgt über die Lötaugen von J5.<br>
Die Pinbelegung ist auf der Platine aufgedruckt.<br>
Man muss sich lediglich ein Adapterkabel für den In Circuit Programmer anfertigen.<br>
<br>
Das Flashen erfolgt mit folgenden Befehlen.<br>
Die Pfade sind ggf. entsprechend anzupassen.<br>
<code>asdf</code>

#### 3. Einlöten der Stiftleisten:
Nun werden die Stiftleisten von Funkmodul (IC1) und den Board to Board Verbinder (J2) bestückt.<br>
Die Stiftleisten werden beide auf der Bestückseite gesetzt.<br>
<br>
Siehe Bild:<br>
<img src="images/LED_Teelicht_Haupt_PCB_02.jpg">
<br>

#### 4. Funkmodul auflöten:

#### 5. Flacker-LED einlöten:
<br>

### Sketch flashen:
Der nächste Schritt ist das Flashen des Sketches.<br>
Das Vorgehen ist auf [asksinpp.de/Grundlagen/02_software](https://asksinpp.de/Grundlagen/02_software.html) beschrieben.<br>
<br>

### Anlernen und erster Test:
Vor dem Einbau in das Gehäuse sollte man das LED-Teelicht erst einmal auf Funktion testen.
Hierzu empfehle ich folgende Vorgehensweise:
1. Hauptplatine auf die Batterieplatine aufstecken
2. FTDI-Adapter anschließen und den seriellen Monitor in der Arduino IDE öffnen. Nun sollten die üblichen Ausgaben auf der Konsole kommen
3. Den Config-Taster auf der Batterieplatine so lange drücken, bis in der Konsole "Reset" kommt (wird auch durch schnelles Blinken an der LED angezeigt)
4. Nun lässt sich die Flacker-LED durch kurzen Druck auf den Config-Taster ein- bzw. ausschalten.
5. Die HM-Zentrale in den Anlernmodus bringen.
6. Den Config-Taster so lange drücken, bis die LED zu blinken beginnt.
7. Wenn alles funktioniert, dann sollte sich das LED-Teelicht anlernen und als Schaltaktor in der HM-Zentrale sichtbar werden.
8. Über die WebUI kann das LED-Teelicht nun geschaltet werden.
<br>

### Einbau in das Gehäuse:
#### 1. Hauptplatine einbauen:

#### 2. Batterieplatine einbauen:

#### 3. Deckel aufschrauben:
