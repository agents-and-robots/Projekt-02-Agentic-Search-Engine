# Architektur – Agentic Search Engine

## Module

- agent.py – orchestriert Suche, Scoring, Antwort
- searcher.py – durchsucht lokale Dokumente
- scorer.py – bewertet Ergebnisse
- answerer.py – generiert regelbasierte Antworten

## Datenfluss

1. Agent erhält Query
2. Searcher durchsucht Dokumente
3. Scorer bewertet Ergebnisse
4. Answerer erzeugt Antwort
5. Feedback-Loop bei Bedarf
