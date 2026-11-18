# Konzept: KC-Verwaltung

> **Status:** Entwurf
> **Stand:** 18.11.2026
>
> Dieses Dokument beschreibt *was* die Anwendung leisten soll. Auf seiner Basis wird anschließend die Spezifikation erstellt. Technische Details (Technologie-Stack, Datenmodell, Oberflächen) sind nicht Teil des Konzepts.

---

## 1. Ausgangslage und Ziel

### Ausgangslage

- Der Schriftführer schreibt während des Kegelabends alles auf einem Papierzettel mit (Strafen je Person, verlorene Spiele, Gesamtbetrag).
- Der Zettel wird anschließend als Foto in die Gruppe geschickt – danach sind die Informationen faktisch verloren.
- Satzung, Vereinsordnung, Strafliste und Spielbeschreibungen liegen als einzelne Dateien (Word, Excel, PDF) vor.

### Grundsatz

- **Während des Kegelabends bleibt es bei Papier.** Es gilt Handyverbot; die Anwendung wird am Abend selbst nicht benutzt.
- Die Webseite ist das **Archiv und die Auswertung**: Nach dem Abend werden die Daten des Zettels nachgetragen.

### Ziel

Eine Webseite, auf der ein Kegelclub alle Informationen gesammelt festhält:

- Mitglieder, Rollen und Termine verwalten
- eine Sammlung von Kegelspielen pflegen
- Kegelabende dokumentieren (Anwesenheit, gespielte Spiele, Strafen)
- Satzung, Vereinsordnung und Strafenkatalog pflegen
- aus den gesammelten Daten Statistiken und Ranglisten erzeugen

---

## 2. Benutzer, Clubs, Rollen und Rechte

### Mehrere Clubs

- Eine Installation kann **mehrere Kegelclubs** verwalten. Die Daten der Clubs sind voneinander getrennt.
- Ein Nutzerkonto kann **in mehreren Clubs** Mitglied sein.

### System-Admin

- Es gibt einen **System-Admin**, der über allen Clubs steht.
- Der System-Admin legt Clubs an und verwaltet Clubs und Nutzer.
- Für einen neuen Club verschickt der System-Admin die **Einladung an den ersten Club-Verwalter**.

### Rollen im Club

- Jeder Club legt seine **Rollen selbst an** (z. B. Vorsitzender, Kassenwart, Schriftführer).
- Pro Club gibt es **mindestens eine Rolle, die den Club verwalten** darf.
- Ein Mitglied kann **mehrere Rollen** haben, eine Rolle kann **mehrere Mitglieder** haben (z. B. zwei Kassenwarte).

### Rechte

- Pro Rolle wird festgelegt, welche Bereiche sie **bearbeiten** darf:

  | Bereich | Beispiel |
  |---|---|
  | Club verwalten | Einstellungen des Clubs (Turnus, Saison, Absagefrist …) |
  | Mitglieder | Mitglieder und Gäste anlegen, Einladungen verschicken |
  | Rollen | Rollen anlegen und Rechte vergeben |
  | Termine | Termine anlegen und pflegen |
  | Kegelabende dokumentieren | Anwesenheit, Spiele und Strafen eines Abends eintragen |
  | Spielekatalog | Spiele anlegen und bearbeiten |
  | Strafenkatalog | Strafen anlegen und bearbeiten |
  | Dokumente | Satzung, Vereinsordnung und weitere Dokumente bearbeiten |

- **Lesen** dürfen alle Mitglieder des Clubs.

---

## 3. Mitglieder, Gäste und Einladungen

### Mitglieder

- Mitglieder werden im Club angelegt.
- **Ehemalige Mitglieder** bleiben als „ehemalig“ erhalten, damit ihre Daten in Abenden und Statistiken erhalten bleiben.

### Einladungen und Nutzerkonten

- Zu einem angelegten Mitglied kann ein **personalisierter Einladungslink** verschickt werden.
- Über diesen Link legt die Person ein Nutzerkonto an, das mit dem Mitglied verknüpft ist.
- Nutzerkonten entstehen **ausschließlich über Einladungslinks**.

### Gäste (externe Personen)

- Gastkegler werden nicht als Mitglieder geführt, sondern als **externe Personen**.
- Für einen Gast wird ein **kleiner Datensatz** mit **Vor- und Nachname** angelegt.
- In der Ansicht des Kegelabends sind Gäste als **Gast markiert**.
- Gäste nehmen an Spielen teil, erhalten Strafen wie Mitglieder und tauchen in den Daten des Abends auf.
  Ob der Gast oder das einladende Mitglied die Strafen zahlt, regeln die Beteiligten unter sich.
- Eine externe Person kann **zum Mitglied werden**. Ihre bisherigen Daten und Statistiken werden dabei **in das Mitglied übernommen**.

---

## 4. Termine, Saison, Zu- und Absagen

### Turnus

- Pro Club wird ein **Turnus** der Kegelabende festgelegt, angegeben in **Wochen oder Monaten** (Tage optional).
- Aus dem Turnus werden die Termine erzeugt.

### Saison

- Pro Club wird festgelegt, wie eine Saison definiert ist:
  - **am Kalenderjahr** ausgerichtet, oder
  - über ein **Startdatum und eine Laufzeit**.
- Statistiken wie „Pudelkönig der Saison“ beziehen sich auf die Saison.

### Zu- und Absagen

- Mitglieder können zu Terminen **zu- und absagen**.
- Pro Club ist einstellbar, ob Absagen **über die Webseite** erfolgen, **nachgetragen** werden oder **beides** möglich ist.
- Pro Club wird eine **Absagefrist** festgelegt (beim KC Umluft: 5 Stunden vor Beginn).
  Erfolgt keine rechtzeitige Absage, schlägt die Webseite das Fehlen als **unentschuldigt** vor.

---

## 5. Spielekatalog

Jeder Club pflegt eine eigene Sammlung von Kegelspielen. Ein Spiel enthält:

| Angabe | Beispiel (Hausnummer) |
|---|---|
| Name | Hausnummer |
| Spieltyp | Einzelspiel |
| Bahneinstellung | Volle |
| Spieleranzahl | 2 – ∞ Spieler |
| Grobe Zeitangabe | (im Spieleblatt noch nicht enthalten) |
| Spielbeschreibung | Alle werfen reihum 3-mal, aus den Zahlen wird eine Hausnummer gebildet … |
| Besonderheiten | Keine |
| Varianten | Wer die Position der Ziffer festlegt (Nachbar, vorher festgelegt, Spieler selbst) |

---

## 6. Kegelabend dokumentieren

Nach dem Kegelabend trägt ein Mitglied mit entsprechendem Recht die Daten des Abends ein.

### Vordruck

- Die Webseite stellt einen **druckbaren Vordruck** für den Abend bereit, auf dem während des Abends mitgeschrieben wird.
- Aussehen und Inhalt des Vordrucks sind noch offen (siehe [Offene Punkte](#11-offene-punkte)).

### Erfasste Daten

- **Anwesenheit:** anwesend, entschuldigt fehlend, unentschuldigt fehlend; dazu anwesende Gäste.
- **Gespielte Spiele:** Spiel aus dem Spielekatalog und die **Position**, die jeder Teilnehmer erreicht hat.
  - **Geteilte Plätze** sind möglich. Die folgenden Plätze werden dann übersprungen (z. B. 1., 2., 2., 4.).
  - Bei **Teamspielen** erhält jedes Team eine Position, die für alle Spieler des Teams gilt. Ein Teamspiel hat **höchstens zwei Teams** (Gewinnerteam erster Platz, anderes Team letzter Platz).
- **Strafen pro Vergehen** und pro Person, jeweils als **Anzahl** (z. B. 3× Pudel, 1× Seil berührt, 1× Spiel verloren).
  - Pudel und verlorene Spiele werden ebenfalls als Strafe eingetragen.
  - Strafen, die von einer Menge abhängen, werden ebenso über die Anzahl erfasst. Beispiel: Verspätung (1 € je angefangene Stunde) wird je angefangene Stunde einmal gezählt.
- **Strafen ohne Geldbetrag** (z. B. Bierfrevel → Runde ausgeben) werden ebenfalls dokumentiert.
- **Auskegeln** um den Pudelkönig: ob ausgekegelt wurde und wer beteiligt war (siehe [Statistiken – Regeln](#regeln)).

Das **Kegelbild** eines Spiels wird **nicht** gesondert festgehalten. Wo es eine Rolle spielt, ist es Teil der Spielbeschreibung im Spielekatalog.

Einzelne Würfe werden **nicht** erfasst – der Aufwand ist hoch und der statistische Nutzen gering, da je nach Spiel unterschiedliche Ziele und Ausgangslagen gelten.

### Berechnung der Strafen

- **Summe pro Person:** Alle Strafen einer Person werden addiert und anschließend **auf volle Euro aufgerundet**.
  Angezeigt werden beide Beträge (ungerundet und gerundet).
- **Fehlende Mitglieder** zahlen den **Durchschnitt** der Strafen des Abends:
  - Grundlage sind nur Strafen, die im Strafenkatalog als **„zählt für den Durchschnitt der Fehlenden“** markiert sind (gespielte Strafen wie Pudel, Seil, Spiel verloren – nicht z. B. „T-Shirt vergessen“).
  - Durchschnitt = Summe dieser Strafen ÷ Anzahl der Anwesenden.
  - Anwesende **Gäste zählen normal mit**, sowohl bei der Summe der Strafen als auch bei der Anzahl der Anwesenden.
- **Unentschuldigtes Fehlen:** Die Strafe für unentschuldigtes Fehlen (beim KC Umluft 50 €) wird **zusätzlich** auf den Durchschnitt aufgerechnet.

---

## 7. Strafen und Strafenkatalog

- Jeder Club pflegt einen **Strafenkatalog**. Eine Strafe enthält:
  - **Bezeichnung** des Vergehens (Text)
  - **Betrag** als Zahl – Strafen ohne Geldbetrag (z. B. Bierfrevel → „Runde ausgeben“) erhalten den Betrag 0 €.
  - Hinweise wie „je angefangene Stunde“ oder „Runde ausgeben“ sind Teil der Bezeichnung.
  - Merkmal **„zählt für den Durchschnitt der Fehlenden“**
- Der Strafenkatalog ist die **einzige Quelle** für Strafen. Er wird **automatisch in die Vereinsordnung** übernommen und dort angezeigt.

### Beispiel: Strafenkatalog des KC Umluft

| Vergehen | Strafe |
|---|---|
| Unentschuldigtes Fehlen | 50,00 € |
| Kegeloberteil vergessen | 10,00 € |
| Verspätetes Zahlen von Beiträgen oder Strafen | 10,00 € |
| Polnischer Abgang | 5,00 € |
| Verspätetes Erscheinen / früher gehen | 1,00 € je angefangene Stunde |
| Pudelmütze vergessen | 5,00 € |
| Handynutzung | 1,00 € |
| Kugel von Bahn runter | 1,00 € |
| Kugel kommt zurück | 1,00 € |
| Kugel falsch bringen | 1,00 € |
| Spiel verloren | 0,50 € |
| Kugel auf den Tisch gebracht bekommen | 0,50 € |
| Pudel (Rinne) | 0,20 € |
| Seil berühren (Klingel) | 0,20 € |
| Kackstuhl (Y) / Stine (I) | 0,20 € |
| Falsch anschreiben | 0,10 € |
| Anschreiben vergessen | 0,10 € |
| Bierfrevel | Runde ausgeben |

---

## 8. Dokumente

### Allgemein

- Satzung und Vereinsordnung werden **direkt auf der Webseite** bearbeitet (kein Datei-Upload).
- **Weitere Dokumente** können sowohl als Text auf der Webseite angelegt als auch als Datei hochgeladen werden.
- Änderungen werden in einem **Versionsverlauf** festgehalten.
- Der Texteditor bietet **grundlegende Formatierungsmöglichkeiten**: fett, kursiv, Aufzählungen, nummerierte Listen und Links.
- Dieser Editor wird in **allen längeren Textfeldern** verwendet: Satzung, Vereinsordnung, weitere Dokumente sowie Spielbeschreibung, Besonderheiten und Varianten im Spielekatalog.
- Bearbeiten darf, wessen Rolle das Recht „Dokumente“ hat (z. B. der Schriftführer).

### Satzung

- Die Satzung besteht aus **einzelnen Paragraphen**, jeder Paragraph ist ein eigenes Textfeld.
- Die Webseite bringt eine **Vorlage** mit **Pflicht-Paragraphen** und **optionalen Paragraphen** mit.
- Die **Organe des Vereins** (z. B. Vorsitzender, Kassenwart, Schriftführer) werden **automatisch aus den Rollen** und deren Mitgliedern befüllt.

### Vereinsordnung

- Enthält die Regeln des Clubs.
- Der **Strafenkatalog** wird automatisch eingebunden. Er wird wie ein Abschnitt an einer **frei wählbaren Stelle** positioniert.
- Die Vereinsordnung besteht aus **einzelnen Abschnitten**, jeweils mit **Überschrift und Inhalt**.
- Die Abschnitte werden von den berechtigten Personen **frei angelegt** (keine Vorlage wie bei der Satzung).

---

## 9. Statistiken

Statistiken beruhen auf **Positionen** (und den daraus berechneten **Punkten**) in den gespielten Spielen, auf **Strafen** und auf der **Anwesenheit**.

- Pudelkönig der Saison (meiste Pudel)
- Pudelkönig des Abends (trägt laut Vereinsordnung beim nächsten Abend die Pudelmütze)
- **Ranglistenführer des Abends** und **der Saison** (meiste Punkte, siehe Regeln) – der Ranglistenführer der Saison ist der **beste Kegler der Saison**
- Gewonnene Spiele (wird zusätzlich zu den Punkten geführt)
- Rangliste pro Abend
- Strafenkönig
- Anwesenheitsquote
- Auskegeln: wie oft ausgekegelt wurde und wer beteiligt war
- Entwicklung über die Zeit
- Vergleich zweier Mitglieder
- **Durchschnitt der gesamten Truppe**, mit dem sich jedes Mitglied vergleichen kann
- **Ranglisten** zu einzelnen Statistiken

Rekorde pro Spiel sind **nicht möglich**, da nur Positionen und keine Ergebnisse erfasst werden.

### Regeln

- **Gewonnenes Spiel:** Jeder erste Platz zählt als gewonnenes Spiel – auch ein geteilter erster Platz und ein Sieg im Teamspiel.
- **Punkte nach Platzierung:** Für jede Platzierung in einem Spiel gibt es Punkte. Die Punkte hängen von der **Anzahl der Spieler des Spiels** ab: Der Erste erhält so viele Punkte, wie Spieler mitspielen, jeder folgende Platz einen Punkt weniger (bei 6 Spielern: 6, 5, 4, 3, 2, 1).
  - Es zählt die Anzahl der Spieler und nicht die der Anwesenden, da z. B. Verspätete oder früher Gehende für den Abend als anwesend gelten, aber nicht jedes Spiel mitspielen.
  - **Geteilte Plätze:** Alle Spieler auf einem geteilten Platz erhalten die Punkte dieses Platzes (bei 1., 2., 2., 4. erhalten beide Zweiten die Punkte des 2. Platzes).
  - **Teamspiele:** Alle Spieler des Gewinnerteams erhalten die Punkte des 1. Platzes, alle Spieler des Verliererteams die Punkte des **tatsächlich letzten Platzes**.
    Beispiel 2 Teams à 3 Spieler (6 Spieler): Gewinner je 6 Punkte, Verlierer je 1 Punkt.
  Wer die meisten Punkte sammelt, ist **Ranglistenführer** des Abends bzw. der Saison.
- **Gleichstand:** Bei Gleichstand wird der Titel bzw. Platz **geteilt** (z. B. zwei beste Kegler der Saison).
- **Pudelkönig des Abends:** Bei Gleichstand wird am Ende des Abends **ausgekegelt**.
  - Am Auskegeln nehmen nur die Gleichstehenden teil. Wer **zuerst einen Pudel** wirft, wird Pudelkönig.
  - Dieser Pudel wird **normal als Strafe dokumentiert** und entscheidet so den Gleichstand. Der Pudelkönig ergibt sich damit automatisch aus der Anzahl der Pudel.
  - Haben am Ende des Abends trotzdem mehrere gleich viele Pudel, wird die Würde **geteilt**.
  - Auch alle übrigen beim Auskegeln entstehenden Strafen (z. B. Kackstuhl, Stine, Kugel kommt zurück) werden normal dokumentiert.
  - Das Auskegeln ist **kein Spiel** im eigentlichen Sinn: Es steht nicht im Spielekatalog, hat keinen Gewinner und zählt weder als gespieltes noch als gewonnenes Spiel.
  - Beim Abend wird festgehalten, **dass ausgekegelt wurde und wer beteiligt war**.

---

## 10. Ausbaustufen

Folgende Punkte sind für spätere Ausbaustufen vorgesehen und **nicht** Teil des ersten Umfangs:

- **Weitere Veranstaltungsarten** neben dem Kegelabend (z. B. Kegeltour, Königskegeln, sonstige Treffen), bei denen ebenfalls Strafen anfallen können.
- **Teamspiele mit mehr als zwei Teams** (dann ist festzulegen, welche Punkte mittlere Teams erhalten).
- **Kassenwart-Funktionen**, z. B. Pflege eines Bezahlt-Status von Strafen und Beiträgen.
- **Verlorene Spiele automatisch** aus der erreichten Position ableiten statt sie als Strafe einzutragen.

---

## 11. Offene Punkte

### Von dir noch zu entscheiden

| # | Thema | Frage |
|---|---|---|
| w | Vordruck | Wie soll der druckbare Vordruck für den Kegelabend aussehen und was enthält er? Hinweis: Damit Strafen pro Vergehen ausgewertet werden können, braucht der Vordruck – anders als der bisherige Zettel mit Spalten je Betrag – eine Spalte (oder Zeile) je Strafe. |

---

## 12. Rahmenbedingungen

- **Betrieb** in Docker-Containern.
- Bei jedem **Release** werden die Images gebaut und veröffentlicht.
- **Dokumentation** liegt im Ordner `docs` als Markdown.
- Der **Technologie-Stack** wird vor Beginn der Entwicklung festgelegt.
- **Vorgehen:** Konzept → Spezifikation → Entwicklung. Die Entwicklung beginnt erst nach Freigabe der Spezifikation.
