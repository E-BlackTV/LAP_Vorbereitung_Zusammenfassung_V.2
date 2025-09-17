# Zusammenfassung zur Vorbereitung auf die LAP Applikationsentwicklung – Coding

Nur für mich selber gedacht aber wer will darf sich bedienen
---

## **Kapitel 1: Datenbanken, Datenmodelle und -strukturen**

### **Thema 1.1: ER-Modell und Beziehungen**
*   **ER-Modell:** Bauplan für Daten; definiert "Dinge" (**Entitäten**) und deren Zusammenhänge (**Beziehungen**).
*   **Beziehungstypen:** 1:1, 1:n (häufig), n:m (wird mit Kopplungstabelle aufgelöst).

### **Thema 1.2: Normalisierung – Praktisch erklärt**
*   **Ziel:** Daten-Wiederholungen (Redundanz) vermeiden und Fehler (Anomalien) verhindern.
*   **Prozess:** Eine große, unübersichtliche Tabelle wird schrittweise (1NF, 2NF, 3NF) in mehrere kleine, logische Tabellen aufgeteilt, die über Schlüssel verbunden sind.
*   **Ergebnis (3NF):** Jede Information ist nur an einem Ort gespeichert, was die Datenintegrität sicherstellt.

### **Thema 1.3: Schlüssel & Indizes**
*   **Primärschlüssel (PK):** Identifiziert eine Zeile in einer Tabelle **eindeutig**.
*   **Fremdschlüssel (FK):** **Verweist** auf den PK einer anderen Tabelle und stellt so die Beziehung her.
*   **Index:** Ein separates "Inhaltsverzeichnis" für Spalten, das `SELECT`-Abfragen **beschleunigt**.
    *   **Vorteile:** Massiv beschleunigte Lesezugriffe.
    *   **Nachteile:** Benötigt Speicherplatz, verlangsamt Schreiboperationen (`INSERT`, `UPDATE`, `DELETE`).

### **Thema 1.4: SQL (Abfragen und Auswertungen)**
*   **`SELECT`/`FROM`/`WHERE`**: Daten aus einer Tabelle holen und nach Zeilen filtern.
*   **`INNER JOIN`**: Daten aus mehreren Tabellen über PK-FK-Beziehungen verbinden.
*   **`GROUP BY`**: Fasst Zeilen zu Gruppen zusammen. Wird mit Aggregatfunktionen (`COUNT`, `SUM`) benutzt.
*   **`HAVING`**: Filtert das Ergebnis von `GROUP BY`.

### **Thema 1.5: Views & Constraints**
*   **`VIEW`**: Eine gespeicherte `SELECT`-Abfrage, die als virtuelle Tabelle dient (Vereinfachung, Sicherheit).
*   **Constraints**: Regeln für Datenqualität (`NOT NULL`, `UNIQUE`, `CHECK`, `DEFAULT`).

### **Thema 1.6: Weitere DB-Begriffe (Ergänzung)**
*   **Datenbanksysteme:** RDB (relational, Standard), Objektorientierte DB, Data Warehouse (für Analysen).
*   **DBMS:** Die Software, die die DB verwaltet (z.B. MySQL Server).
*   **CMS:** Anwendungssoftware zur Verwaltung von Inhalten (z.B. WordPress), die eine DB nutzt.
*   **Sicherung/Recovery & Locking:** Erstellen von Backups und deren Wiederherstellung; Sperren von Datensätzen bei Änderungen, um Konflikte zu vermeiden.
*   **Unternehmenssysteme:** ERP (steuert Kernprozesse, z.B. SAP), BI/BW (analysiert Geschäftsdaten).
*   **Transaktionskonzept (ACID):** Stellt sicher, dass Transaktionen **A**tomar, **C**onsistent, **I**soliert und **D**auerhaft sind.

---

## **Kapitel 2: Bedienoberfläche / Web**

### **Thema 2.1: HTML-Grundgerüst und Bootstrap**
*   **HTML:** Das Skelett der Seite, gibt die Struktur vor.
*   **Bootstrap:** CSS/JS-Framework für fertige, responsive Komponenten und ein Grid-Layout-System.
*   **`<meta name="viewport"...>`:** Essentiell für Responsive Design.

### **Thema 2.2: HTML-Formulare**
*   **`id` vs. `name`**: `id` ist für Frontend (CSS, JS), `name` ist für Backend (PHP).

### **Thema 2.3: Clientseitige Validierung mit JavaScript**
*   **Zweck:** Sofortiges Feedback für den Benutzer. Reines Komfort-Feature, **kein Sicherheitsmerkmal**.

### **Thema 2.4: Serverseitige Verarbeitung mit PHP und PDO**
*   **Serverseitige Validierung:** **Zwingend erforderlich!**
*   **Prepared Statements:** Schutz vor **SQL Injection** durch Trennung von Befehl und Daten.

### **Thema 2.5: SEO & CMS**                                                                                                                                                
*   **SEO (Search Engine Optimization):** Maßnahmen, um bei Google besser gefunden zu werden (gute Inhalte, saubere HTML-Struktur, Backlinks).                              
*   **CMS (Content Management System):** Software zur einfachen Verwaltung von Web-Inhalten (z.B. WordPress). Benötigt Webserver, Skriptsprache (PHP) und Datenbank.

### **Thema 2.6: Zeichencodierung**                                                                                                                                         
*   **ASCII:** Alter 7-Bit-Standard, nur für englische Zeichen.                                                                                                             
*   **ISO-8859-1 (Latin-1):** 8-Bit-Erweiterung für westeuropäische Zeichen (inkl. Umlaute).                                                                                
*   **Unicode (UTF-8):** Moderner, universeller Standard für alle Zeichen der Welt. Immer verwenden (`<meta charset="UTF-8">`).

### **Thema 2.7: Standards & Webservices**                                                                                                                                  
*   **Standards (ANSI, ISO, IEEE):** Gremien, die technische Normen festlegen.                                                                                              
*   **Webservices:** Ermöglichen die Kommunikation zwischen verschiedenen Anwendungen über das Internet.                                                                    
*   **SOAP:** Älteres, starres, XML-basiertes Protokoll.                                                                                                                    
*   **REST:** Moderner, flexibler Architekturstil, der auf HTTP-Methoden (`GET`, `POST` etc.) aufbaut.                                                                      
*   **JSON:** Leichtgewichtetes Datenaustauschformat, heute Standard für REST-APIs.

### **Thema 2.8: Frameworks & Konzepte**
*   **jQuery:** Ältere JavaScript-Bibliothek, die DOM-Manipulation vereinfacht hat. Heute seltener benötigt.
*   **AngularJS (v1):** Frühes Framework für Single-Page-Applications. Nachfolger ist **Angular** (v2+).
*   **Reaktive Programmierung:** Programmierparadigma, bei dem die Anwendung auf Datenänderungen automatisch "reagiert". Basis moderner Frontend-Frameworks.
*   **Mobile-First:** Design-Strategie, bei der zuerst für mobile Geräte entwickelt wird. Führt zu besserer Performance und durchdachterem Design.

### **Thema 2.9: Sprachen & Plattformen**
*   **Aktuelle Programmiersprachen:** Python (Backend, AI), JavaScript/TypeScript (Frontend/Backend), Java (große Unternehmenssysteme), C# (mit .NET), Go (schnelle
      Backend-Services), Swift (iOS), Kotlin (Android).
*   **Java-Web (Jakarta EE):** **Servlets** sind Java-Programme, die auf einem Webserver laufen und Anfragen bearbeiten. **JSP (JavaServer Pages)** ist eine Technologie, um
      Java-Code in HTML-Seiten einzubetten (ähnlich wie PHP).
*   **.NET (ASP.NET):** Das Web-Framework von Microsoft, primär mit der Sprache C# genutzt, um robuste Webanwendungen und -services zu erstellen.
*   **Cross-Plattform:** Die Entwicklung von Apps, die auf mehreren Betriebssystemen (z.B. iOS und Android) laufen. Bekannte Frameworks sind React Native, Flutter und Xamarin.

### **Thema 2.10: Prinzipien & Prozesse**
*   **KISS (Keep It Simple, Stupid):** Ein Design-Prinzip, das Einfachheit in Design und Implementierung anstrebt und unnötige Komplexität vermeidet.
*   **DRY (Don't Repeat Yourself):** Ein Prinzip der Softwareentwicklung, das darauf abzielt, die Wiederholung von Code und Logik zu reduzieren. Statt Code zu kopieren, wird er in
      wiederverwendbare Einheiten (z.B. Funktionen, Klassen) abstrahiert.
*   **Continuous Integration (CI):** Die Praxis, Code-Änderungen von mehreren Entwicklern regelmäßig und automatisch in ein zentrales Repository zu integrieren. Nach jeder
Integration wird ein automatisierter Build- und Testlauf gestartet.
*   **Continuous Deployment/Delivery (CD):** Baut auf CI auf. Jede bestandene Änderung wird automatisch für die Veröffentlichung vorbereitet (**Delivery**) oder sogar direkt live
geschaltet (**Deployment**).
---

## **Kapitel 3: Softwareentwicklung, Methoden & Qualität**

### **Thema 3.1: Vorgehensmodelle (Wasserfall vs. Agil)**
*   **Wasserfall:** Klassisch, linear, starr.
*   **Agil (z.B. Scrum):** Modern, iterativ, flexibel.

### **Thema 3.2: Scrum im Detail**
*   **3 Rollen:** Product Owner (Was), Development Team (Wie), Scrum Master (Coach).
*   **4 Meetings:** Sprint Planning, Daily Scrum, Sprint Review (Produkt-Feedback), Sprint Retrospective (Prozess-Feedback).
*   **3 Artefakte:** Product Backlog, Sprint Backlog, Product Increment.

### **Thema 3.3: Software-Tests & Qualität**
*   **Black-Box-Test:** Testen von außen, ohne Code-Kenntnis.
*   **White-Box-Test:** Testen von innen, mit Code-Kenntnis.
*   **Schreibtischtest:** Manuelle Simulation des Codes auf dem Papier.
*   **Code-Review:** Ein Kollege prüft den Code.
*   **Changemanagement:** Kontrollierter Prozess für geplante Änderungen.
*   **Problemmanagement:** Prozess zur Findung der Ursache von Störungen.

### **Thema 3.4: Projektmanagement-Basics**
*   **Projekt:** Ein einmaliges, zeitlich befristetes Vorhaben mit einem definierten Ziel.
*   **Magisches Dreieck:** Die konkurrierenden Ziele Umfang (Scope), Zeit (Time) und Kosten (Cost).
*   **Projektauftrag:** Das offizielle Startdokument des Projekts.
*   **Projektstrukturplan (PSP):** Zerlegt das Projekt in hierarchische, kleinere Arbeitspakete.
*   **Arbeitspaket:** Die kleinste plan- und steuerbare Einheit im PSP.
*   **Meilenstein:** Ein wichtiges Ereignis im Projektverlauf ohne Zeitdauer (z.B. "Testphase abgeschlossen").
*   **Struktogramm vs. Flowchart:** Struktogramme dienen dem Algorithmen-Entwurf, Flowcharts der allgemeinen Prozess-Visualisierung.
*   **Lastenheft vs. Pflichtenheft:** Das Lastenheft (Kunde) beschreibt das "Was", das Pflichtenheft (Entwickler) beschreibt das "Wie".

### **Thema 3.5: Weitere Methoden & Begriffe**
*   **DevOps:** Eine Kultur, die Entwicklung (Dev) und IT-Betrieb (Ops) durch Automatisierung und Zusammenarbeit verbindet, um Software schneller und zuverlässiger zu liefern.
*   **V-Modell:** Ein Vorgehensmodell, das jeder Entwicklungsphase eine Testphase direkt gegenüberstellt. Systematischer als Wasserfall, aber ähnlich unflexibel.
*   **Prototyp:** Ein frühes, lauffähiges Versuchsmodell einer Anwendung, um schnell Feedback von Nutzern und Kunden zu erhalten.
*   **Soll-Ist-Analyse:** Ein Werkzeug im Projektcontrolling, das den geplanten Fortschritt (Soll) mit dem tatsächlichen Fortschritt (Ist) vergleicht.

*   **Thema 3.6: Qualitätsmerkmale & Versionierung**
*   **Qualitätsmerkmale (n. ISO 25010):** Kriterien zur Bewertung von Software, z.B. Funktionalität, Zuverlässigkeit, Benutzbarkeit, Effizienz, Wartbarkeit.
*   **Versionierung und Nutzen:** Die Verwaltung von Code-Versionen (z.B. mit Git). Der Nutzen für die Qualität liegt in der Nachvollziehbarkeit von Änderungen und der Möglichkeit, bei Fehlern auf eine frühere, stabile Version zurückzuspringen (Rollback).

---

## **Kapitel 4: Sicherheit, Recht & Netzwerkdienste**

### **Thema 4.1: DSGVO im Detail**
*   **Prinzipien:** Verbot mit Erlaubnisvorbehalt, Zweckbindung, Datenminimierung.
*   **Rollen:** Verantwortlicher (entscheidet), Auftragsverarbeiter (handelt auf Anweisung).
*   **Kopplungsverbot:** Dienst darf nicht von unnötiger Einwilligung abhängen.
*   **Data Breach:** Meldepflicht an Behörde (innert 72h).

### **Thema 4.2: Weitere rechtliche Bestimmungen**
*   **Rechte der Betroffenen:** Auskunft, Berichtigung, Löschung.
*   **Impressumspflicht (ECG):** "Namensschild" der Webseite.
*   **Urheberrecht:** Lizenzen für Code, Bilder etc. beachten.
*   **Gewährleistung vs. Garantie:** Gesetzlich vs. freiwillig.
*   **TKG:** Fernmeldegeheimnis.
*   **Entsorgung & Bildschirmpausen:** Umweltgerechte Entsorgung; Gesetzliche Pausen.

### **Thema 4.3: Netzwerk & Cloud**
*   **Mail-Protokolle:** SMTP (senden), POP3 (herunterladen), IMAP (synchronisieren).
*   **FTP/FTPS:** Dateiübertragung (unverschlüsselt/verschlüsselt).
*   **Cloud-Modelle:** IaaS (Infrastruktur), PaaS (Plattform), SaaS (Software).

### **Thema 4.4: Weitere rechtliche & Netzwerk-Aspekte**
*   **Pflichtangaben im E-Mail-Verkehr:** Geschäftliche E-Mails müssen, ähnlich einem Impressum, die wesentlichen Firmendaten (Name, Sitz, Firmenbuchnummer etc.) enthalten.
*   **Domain-Aufbau:** Eine Domain wie `shop.meine-firma.at` gliedert sich in Sub-Domain (`shop`), Domain (`meine-firma`) und Top-Level-Domain (`.at`).
*   **HTTP vs. HTTPS:** HTTP überträgt Daten unverschlüsselt (Klartext). HTTPS nutzt ein SSL/TLS-Zertifikat, um die Verbindung zu verschlüsseln und sorgt für Vertraulichkeit, Integrität und Authentizität.

### **Thema 4.5: IT-Security Ergänzungen**
*   **Spyware:** Spionage-Software, die heimlich Nutzerdaten sammelt.
*   **Zero-Day-Exploit:** Ein Angriff, der eine bisher unbekannte Sicherheitslücke ausnutzt, für die es noch keinen Patch gibt.
*   **Systemhärtung:** Das Reduzieren der Angriffsfläche eines Systems durch Deaktivieren unnötiger Dienste, Ports und Accounts.

### **Thema 4.6: Cloud-Dienste & Einsatzkriterien**
*   **Marktbekannte Dienste:** AWS (Amazon Web Services), Microsoft Azure, Google Cloud Platform (GCP).
*   **Einsatzkriterien:** Kosten, Sicherheit & Compliance (DSGVO!), Skalierbarkeit, Performance, Stabilität der eigenen Internetverbindung, Vermeidung von Vendor-Lock-in.

### **Thema 4.7: Informatik & Gesellschaft**
*   **e-Government:** Digitale Erledigung von Behördenwegen (z.B. FinanzOnline) mittels **Digitaler Signatur** (ID Austria).
*   **Netzneutralität:** Prinzip der Gleichbehandlung aller Datenpakete im Internet.
*   **Tracking:** Wiedererkennung von Nutzern, klassisch über **Cookies**, zunehmend über **Cookieless**-Methoden (z.B. Fingerprinting).
*   **Biometrie:** Erkennung per Fingerabdruck/Gesicht. Vorteil: bequem. Nachteil: Merkmale sind bei Diebstahl permanent kompromittiert.

### **Thema 4.8: Ergonomie am Arbeitsplatz**
*   **Ziel:** Vermeidung von gesundheitlichen Schäden durch korrekte Einrichtung des Arbeitsplatzes.
*   **Regeln:** Bildschirm seitlich zum Fenster (gegen Blendung), Oberkante auf Augenhöhe, 90-Grad-Winkel im Ellbogen, Füße am Boden, regelmäßige Pausen.
---

## **Kapitel 5 & 15: Grundlagen & Programmierung (Nachträge)**

### **Thema 5.1: Zahlensysteme & Logik**
*   **Zahlensysteme:** Binär (0/1), Hexadezimal (0-F) als Kurzschrift.
*   **Logik-Gatter:** `AND`, `OR`, `NOT`.

### **Thema 5.2: Lastenheft vs. Pflichtenheft**
*   **Lastenheft:** Kunde beschreibt das "Was".
*   **Pflichtenheft:** Entwickler beschreibt das "Wie".

### **Thema 5.3: Betriebssystem-Begriffe**
*   **Multitasking:** Quasi-gleichzeitige Ausführung mehrerer Prozesse.
*   **Multi-User:** Mehrere Benutzer arbeiten getrennt am selben System.



## **Kapitel 15: Grundkenntnisse des Programmierens (Ergänzungen)**

### **Thema 15.1: Interpreter vs. Compiler**
*   **Compiler:** Übersetzt vorab.
*   **Interpreter:** Übersetzt zur Laufzeit.

### **Thema 15.2: Datenstrukturen**
*   **Stack (LIFO):** Stapel (`push`/`pop`).
*   **Queue (FIFO):** Warteschlange (`enqueue`/`dequeue`).

### **Thema 15.3: Variable vs. Konstante**
*   **Variable:** Veränderbarer Wert.
*   **Konstante:** Nicht veränderbarer Wert.

### **Thema 15.4: Rekursive Funktionen**
*   **Definition:** Funktion, die sich selbst aufruft. Benötigt **Basisfall** (Abbruch).

### **Thema 15.5: Programmentwicklung & Sprachelemente**
*   **Ablauf der Programmentwicklung:** Analyse -> Entwurf -> Implementierung -> Test -> Dokumentation -> Wartung.
*   **Syntax vs. Semantik:** Syntax ist die Grammatik der Sprache, Semantik ist die Bedeutung des Befehls.
*   **Schlüsselwörter:** Reservierte Wörter einer Sprache (`if`, `for`, `while`).

### **Thema 15.6: Werkzeuge & Low-Level**
*   **Debugger:** Werkzeug zur Fehlersuche, erlaubt schrittweise Ausführung und das Setzen von Breakpoints.
*   **Assembler:** Low-Level-Sprache, die fast direkt Maschinencode abbildet.

### **Thema 15.7: Kontrollstrukturen & Gültigkeitsbereiche**
*   **Gültigkeitsbereich (Scope):** Der Bereich, in dem eine Variable sichtbar ist (z.B. lokal in einer Funktion).
*   **Kopfgesteuerte Schleife (`while`, `for`):** Prüft die Bedingung vor dem ersten Durchlauf (läuft 0- bis n-mal).
*   **Fußgesteuerte Schleife (`do-while`):** Prüft die Bedingung nach dem ersten Durchlauf (läuft 1- bis n-mal).
*   **Fallunterscheidung:** `if-else` (für Bedingungen), `switch-case` (für Werte).

### **Thema 15.8: OOP-Basics**
*   **Klasse:** Ein Bauplan für Objekte (definiert Attribute und Methoden).
*   **Objekt:** Eine konkrete Instanz einer Klasse im Speicher.
*   **Vererbung:** Eine Klasse kann Eigenschaften und Methoden von einer anderen Klasse erben und diese erweitern oder überschreiben.

---

## **Kapitel 17: Systementwicklung/Testkonzepte (Ergänzungen)**

### **Thema 17.1: Funktionen im Detail**
*   **Schnittstelle (Signatur):** Definiert eine Funktion durch Name, Parameter (Eingabewerte) und Rückgabewert.
*   **Call-by-Value:** Die Funktion erhält nur eine **Kopie** eines Werts. Das Original bleibt unberührt.
*   **Call-by-Reference:** Die Funktion erhält einen **Verweis** auf das Original. Änderungen in der Funktion verändern auch das Original.

### **Thema 17.2: Klassen im Detail**
*   **Konstruktor:** Spezielle Methode, die bei der Erzeugung eines Objekts (`new`) aufgerufen wird, um es zu initialisieren.
*   **Destruktor:** Spezielle Methode, die vor der Zerstörung eines Objekts aufgerufen wird, um Ressourcen freizugeben.
*   **Zugriffsmodifikatoren:** Regeln die Sichtbarkeit von Attributen und Methoden.
     *   `public`: Von überall sichtbar.
     *   `private`: Nur innerhalb der eigenen Klasse sichtbar (Datenkapselung).
     *   `protected`: Sichtbar in der eigenen und in erbenden Klassen.
*   **Standardbibliothek:** Eine mit der Sprache mitgelieferte Sammlung nützlicher, vordefinierter Klassen und Funktionen.

### **Thema 17.3: Testkonzepte & Auswertung**
*   **Testkonzept:** Der "Schlachtplan" für das Testen. Definiert Was, Wie, Wer und Wann getestet wird.
*   **Testprotokoll & Auswertung:** Dokumentiert die Testergebnisse. Gefundene Fehler (Bugs) werden in einem Bug-Tracking-System (z.B. Jira) erfasst.

### **Thema 17.4: Testkriterien für DB-Felder**
*   **Prinzip:** Testen von Eingabefeldern mit Positiv- und Negativfällen sowie Grenzwerten.
*   **Beispiel E-Mail:** Test mit gültiger, ungültiger (ohne @), leerer und zu langer Eingabe.
*   **Beispiel Zahl (Grenzwert):** Wenn ein Wert zwischen 0-1000 liegen muss, teste -1, 0, 1 und 999, 1000, 1001.

### **Thema 17.5: Fehlerarten & Testautomatisierung**
*   **Reproduzierbarer Fehler:** Kann zuverlässig mit denselben Schritten ausgelöst werden. Gut zu debuggen.
*   **Nicht-reproduzierbarer Fehler ("Heisenbug"):** Tritt nur sporadisch auf. Schwer zu finden, oft durch Timing-Probleme (Race Conditions) verursacht.
*   **Testautomatisierung:** Einsatz von Tools (z.B. Selenium, JUnit), um Tests automatisch auszuführen. Essentiell für CI/CD-Pipelines und Regressionstests.