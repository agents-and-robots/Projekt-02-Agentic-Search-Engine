# Agentic Search Engine (Offline, CPU-only)

Dieses Projekt implementiert eine agentische Suchmaschine, die ohne Internetzugang arbeitet.
Sie durchsucht lokale Dokumente, plant Suchstrategien, bewertet Ergebnisse und beantwortet Fragen.

Das Projekt demonstriert:
- agentische Planung
- iterative Suche
- Bewertung von Ergebnissen
- deterministische Offline-Analyse
- Prompt-Driven Development (PDD)

## Funktionen

- lokale Dokumente durchsuchen (Textdateien)
- Suchstrategien planen (Agent)
- Ergebnisse scoren
- Antworten generieren (regelbasiert, ohne LLM)
- Feedback-Loop zur Verbesserung der Suchstrategie

## Projektstruktur

/src  
    agent.py  
    searcher.py  
    scorer.py  
    answerer.py  

/docs  
    architecture.md  

/tests  
    test_agent.md  
    test_searcher.md  
    test_scorer.md  
    test_answerer.md  

hardware-requirements.md  
instructions.md  
README.md  
credits.md

## Hardware Requirements

Dieses Projekt ist vollständig lokal ausführbar und benötigt keine spezielle Hardware.
Siehe `hardware-requirements.md`.

## Lizenz

MIT License (siehe README).

## Credits

Siehe `credits.md`.
# Projekt-02-Agentic-Search-Engine
Eine lokale, CPU‑freundliche, offline‑fähige „Agentic Search Engine“, die:      
- Dokumente durchsucht
- Fragen beantwortet
- Suchstrategien plant
- Ergebnisse bewertet
- alles ohne Internet,
- ohne GPU, ohne große Modelle

Sie simuliert eine agentische Suche — ohne echte Websuche, damit sie auf jedem Laptop läuft.
