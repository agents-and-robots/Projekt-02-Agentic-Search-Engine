# LLM Instructions – Agentic Search Engine (Offline)

Diese Datei definiert alles, was ein LLM benötigt, um dieses Projekt vollständig selbständig umzusetzen:
- Input/Output-Protokoll
- Agenten-Logik
- Regelwerk
- Aufgabenbeschreibung
- Hardware-Constraints
- How-To-Use

---

## 1. Ziel

Erstelle eine agentische Suchmaschine, die lokale Textdateien durchsucht, Suchstrategien plant, Ergebnisse bewertet und Antworten generiert — vollständig offline.

---

## 2. Hardware Constraints

Dieses Projekt muss vollständig auf normaler Consumer-Hardware lauffähig sein:

- CPU-only
- keine GPU-Abhängigkeiten
- keine Modelle > 1 GB
- keine externen APIs oder Cloud-Dienste
- alles offline
- Python-Standardbibliothek

---

## 3. Modul-Spezifikationen

### 3.1 Agent (/src/agent.py)

Signatur: run(query: str, documents: list[str]) -> dict

Aufgaben:
- Suchstrategie planen
- searcher, scorer, answerer orchestrieren
- Feedback-Loop durchführen

Rückgabeformat:
- answer: string
- steps: list[str]
- scores: list[dict]

---

### 3.2 Searcher (/src/searcher.py)

Signatur: search(query: str, documents: list[str]) -> list[dict]

Rückgabeformat:
- results: Liste von Objekten:
  - doc: string
  - snippet: string
  - relevance: float (0–1)

---

### 3.3 Scorer (/src/scorer.py)

Signatur: score(results: list[dict]) -> list[dict]

Aufgabe:
- Ergebnisse bewerten
- Relevanz anpassen

---

### 3.4 Answerer (/src/answerer.py)

Signatur: answer(query: str, results: list[dict]) -> str

Aufgabe:
- einfache regelbasierte Antwort generieren
- kein LLM, keine KI, nur heuristische Regeln

---

## 4. Orchestrator-Logik

1. search_results = search(query, documents)
2. scored = score(search_results)
3. answer = answer(query, scored)
4. Wenn answer leer oder unbrauchbar:
   - neue Suchstrategie
   - zurück zu Schritt 1
5. Ergebnis zurückgeben

---

## 5. Regelwerk / Constraints

### Suche
- einfache Textsuche (substring, regex)
- keine externen APIs

### Scoring
- heuristisch (z. B. Trefferanzahl, Position, Kontext)

### Antwort
- regelbasiert
- keine KI, kein LLM

### Feedback-Loop
- max. 3 Iterationen

---

## 6. Aufgaben an das LLM

Das LLM soll:

1. agent.py implementieren  
2. searcher.py implementieren  
3. scorer.py implementieren  
4. answerer.py implementieren  
5. architecture.md ergänzen  
6. Tests in /tests aktualisieren  

---

## 7. How-To-Use (für Code-Assistenten)

1. Öffne das Repository.  
2. Öffne `instructions.md`.  
3. Markiere den gesamten Inhalt.  
4. Sende ihn an deinen Code-Assistenten mit:

„Lies diese instructions.md vollständig. Implementiere dann alle beschriebenen Module und Dateien. Halte dich strikt an das Input/Output-Protokoll, das Regelwerk und die Hardware-Constraints. Beginne mit searcher.py.“

Damit kann ein LLM das Projekt vollständig autonom umsetzen.
