
==============================
Code-Filter-Projekt – README
Letzte Sicherung: 2025-07-31 21:20 Uhr
==============================

INHALT:
-------
1. Projektübersicht
2. Benötigte Dateien
3. Anforderungen an die Codesuche
4. Bekannte Probleme dieser Version
5. Step-by-Step Plan für den Neuanfang
6. Hinweise zur lokalen Ausführung


1. PROJEKTÜBERSICHT:
--------------------
Dies ist eine Webanwendung zur Darstellung, Filterung und Durchsuchung von HTML-Storydateien (ca. 10.000)
mithilfe zweier CSV-Dateien (stories.csv und codes.csv).

Ziel ist eine dynamische Weboberfläche mit Sortierung, Filterung, Autorennavigation und komfortabler Paginierung.


2. BENÖTIGTE DATEIEN:
---------------------
- public/
    ├── index.html           → Hauptliste aller Stories
    ├── codes.html           → Code-basierte Filterseite
    ├── scripts/
    │     └── script.js      → Logik für index.html
    │     └── codes.js       → Logik für codes.html
    ├── style.css            → Gemeinsames Layout
    ├── stories.csv          → CSV mit Storydaten (Titel, Autor, Datum, etc.)
    ├── codes.csv            → CSV mit Codes und Subkategorien
    └── storydata/*.html     → Die eigentlichen Storydateien

- server.js
- package.json


3. ANFORDERUNGEN AN DIE CODE-SUCHSEITE:
---------------------------------------
🗂 Gruppierung der Codes nach Sub-Kategorie
✅ Drei Auswahlzustände pro Code: "Yes", "No", "Maybe" → Icons statt Buttons
🔍 Freitextsuche über Titel/Autor (optional)
🟢 "Maybe" ist Defaultwert
🎯 Nur wenn ein Code explizit auf Yes/No gesetzt ist, wird er berücksichtigt
📄 Ergebnisliste mit:
    - Titel
    - Autor (anklickbar → Filter nach Autor)
    - Bewertung, Stimmen, Datum
    - Bei Klick: Synopse und Storycodes
📌 Titel wird erst beim Aufklappen verlinkt zur Story
📜 Sortierbare Spaltenüberschriften
🔁 Paginierung: 25/50/100 pro Seite + Navigation um ±1/±5/±10 Seiten
💾 Filterprofile speichern/laden (optional, aber gewünscht)
📦 Alle Funktionalitäten clientseitig – CSV wird im Browser geladen


4. BEKANNTE PROBLEME DIESER VERSION:
------------------------------------
⚠️ Letzter Build enthält Syntaxfehler (fehlende oder überflüssige Klammern)
⚠️ applyFiltersAndRenderResults() war zeitweise undefiniert
⚠️ grouping nach SubCategory funktionierte nicht stabil
⚠️ EventListener doppelt oder unvollständig initialisiert


5. STEP-BY-STEP PLAN FÜR DEN NEUBEGINN:
---------------------------------------
1. Neues `codes.html` + `codes.js` Grundgerüst aufbauen
2. codes.csv laden & Subkategorien gruppieren
3. Rendern der Code-Buttons mit drei Zuständen + Icons
4. Ergebnisliste initialisieren (Tabellenstruktur)
5. Filterlogik definieren (Nur aktive Yes/No beeinflussen Filterung)
6. Filter anwenden + Ergebnisse anzeigen
7. Sortierung + Paginierung hinzufügen
8. Aufklappbare Zeilen mit Synopse & Storycodes
9. Titel verlinken (nach Aufklappen), Autorenfilter bauen
10. Filterprofile (optional)


6. ANWEISUNGEN ZUR LOKALEN AUSFÜHRUNG:
--------------------------------------
Voraussetzung: Node.js installiert (https://nodejs.org)

Im Projektverzeichnis:
> npm install
> node server.js

Dann im Browser:
→ http://localhost:3000/

Fragen? → Frag Cleo, die kennt sich aus 😉

