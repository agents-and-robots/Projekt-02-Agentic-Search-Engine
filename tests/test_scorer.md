# Test: Scorer

## Natürliche Sprache
Der Scorer soll Ergebnisse unverändert zurückgeben (Baseline).

## Maschinenlesbare Struktur
input:
  results:
    - doc: "a"
      snippet: "a"
      relevance: 0.5

expected:
  results:
    - doc: "a"
