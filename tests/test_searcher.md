# Test: Searcher

## Natürliche Sprache
Der Searcher soll Treffer finden, wenn ein Query im Dokument vorkommt.

## Maschinenlesbare Struktur
input:
  query: "hello"
  documents:
    - "hello world"
    - "no match here"

expected:
  results:
    - doc: "hello world"
