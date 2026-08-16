# Silniki spalinowe — animacje czterosuwu

Interaktywne animacje HTML/Canvas (bez zależności) pokazujące pełny cykl czterosuwowy:
ssanie → sprężanie → praca → wydech, z dokładną kinematyką układu korbowego
(mechanizm korbowo-wodzikowy), rozrządem DOHC z łańcuchem oraz kolorystycznym
rozróżnieniem gazów (mieszanka/powietrze, spalanie, spaliny).

## Pliki

| Plik | Silnik | Widok | Zapłon |
|---|---|---|---|
| `r4-benzyna.html` | R4 benzyna | z boku, kamera w poziomie | iskrowy, 1-3-4-2 co 180° |
| `r4-diesel.html` | R4 diesel | z boku, kamera w poziomie | samoczynny, wtrysk przy TDC |
| `v6-benzyna.html` | V6 60° benzyna | wzdłuż wału, kamera 45° w dół | iskrowy, co 120° |
| `v6-diesel.html` | V6 60° diesel | wzdłuż wału, kamera 45° w dół | samoczynny, co 120° |
| `v8-benzyna.html` | V8 90° benzyna | wzdłuż wału, kamera 45° w dół | iskrowy, co 90° |
| `v8-diesel.html` | V8 90° diesel | wzdłuż wału, kamera 45° w dół | samoczynny, co 90° |
| `four-stroke-engine.html` | R4 + V6 + V8 (benzyna) | zbiorczy, starsza wersja | — |

Pliki są samodzielne — wystarczy otworzyć w przeglądarce. Pasek nawigacji
linkuje między wariantami (pliki muszą leżeć w jednym folderze).

## Cechy

- dokładna kinematyka: `y = R·cosθ + √(L² − R²·sin²θ)`, pętla bezszwowa co 720°
- fazy per cylinder (chipy C1–Cn) + wspólne sterowanie Pauza/Prędkość
- rozrząd: wałki DOHC (½ prędkości wału), krzywki, szklanki, sprężyny zaworowe,
  łańcuch z ogniwami sprzężonymi z obrotem wału (wszystko kręci się w prawo)
- benzyna: świeca z iskrą przed TDC; diesel: wtryskiwacz + żarząca się świeca żarowa
- auto-pauza renderowania przy utracie fokusu okna/karty (oszczędność CPU)
- rendering HiDPI (devicePixelRatio)
