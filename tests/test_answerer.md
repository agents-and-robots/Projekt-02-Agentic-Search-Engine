# Test: Answerer

## Natürliche Sprache
Der Answerer soll eine Antwort generieren, wenn Ergebnisse vorhanden sind.

## Maschinenlesbare Struktur
input:
  query: "hello"
  results:
    - doc: "hello world"
      snippet: "hello world"
      relevance: 1.0

expected_contains:
  "hello"
