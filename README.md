# Home Cinema - Online Movie Lists

Tyto JSON soubory obsahují seznamy filmů pro Kodi addon Home Cinema.
Hostuj je na GitHub Pages nebo vlastním serveru.

## Struktura

```
home-cinema-lists/
├── csfd_top_300.json      # Top 300 filmů všech dob
├── csfd_czech_100.json    # Top 100 českých filmů
├── csfd_slovak_50.json    # Top slovenských filmů (TODO)
└── collections/           # Kolekce filmů (TODO)
    ├── marvel.json
    ├── nolan.json
    └── ...
```

## Formát JSON

Každý soubor obsahuje pole objektů:

```json
[
  {
    "title": "Název filmu",
    "year": 1994,
    "genre": "Drama / Komedie",
    "imdb_id": "tt0111161"
  }
]
```

## Hosting na GitHub Pages

1. Vytvoř nový repository: `home-cinema-lists`
2. Nahraj JSON soubory
3. Zapni GitHub Pages v Settings → Pages
4. URL bude: `https://USERNAME.github.io/home-cinema-lists/`

## Konfigurace v addonu

V souboru `online_lists.py` změň BASE_URL:

```python
BASE_URL = 'https://USERNAME.github.io/home-cinema-lists/'
```

## Aktualizace seznamů

1. Uprav JSON soubor
2. Commitni a pushni změny
3. Uživatelé uvidí změny do 6 hodin (cache TTL)

Pro okamžitou aktualizaci mohou uživatelé:
- Smazat cache v nastavení addonu
- Nebo počkat na expiraci cache
