# Silniki spalinowe — interaktywne wizualizacje cyklu czterosuwowego

Zestaw animacji HTML/Canvas przeznaczony jako pomoc dydaktyczna przy tłumaczeniu
zasady działania silnika spalinowego osobom, które nie miały z nią wcześniej
styczności. Każda animacja prezentuje w czasie rzeczywistym wszystkie cztery suwy —
**ssanie, sprężanie, pracę i wydech** — wraz z pełnym łańcuchem zależności
mechanicznych: od obrotu wału korbowego, przez korbowody i tłoki, po rozrząd
sterujący zaworami. Przebieg każdego cylindra można śledzić niezależnie dzięki
wskaźnikom faz, a tempo animacji dostosować do tempa prezentacji.

## Silniki

W poziomie — konfiguracje (liczba i układ cylindrów), w pionie — rodzaj zasilania.

| | **R4** — rzędowy, 4 cylindry<br><sub>widok z boku, zapłon 1‑3‑4‑2 co 180°</sub> | **V6** — widlasty 60°, 6 cylindrów<br><sub>widok wzdłuż wału, zapłon co 120°</sub> | **V8** — widlasty 90°, 8 cylindrów<br><sub>widok wzdłuż wału, zapłon co 90°</sub> | **R1 dwusuw** — 1 cylinder<br><sub>widok z boku, cykl w 360°</sub> | **Wankel** — 1 wirnik<br><sub>widok z boku, 3 komory robocze</sub> |
|---|---|---|---|---|---|
| **Benzyna** <sub>zapłon iskrowy</sub> | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/r4-benzyna.html) · [źródło](r4-benzyna.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/v6-benzyna.html) · [źródło](v6-benzyna.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/v8-benzyna.html) · [źródło](v8-benzyna.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/dwusuw-benzyna.html) · [źródło](dwusuw-benzyna.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/wankel-benzyna.html) · [źródło](wankel-benzyna.html) |
| **Diesel** <sub>zapłon samoczynny</sub> | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/r4-diesel.html) · [źródło](r4-diesel.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/v6-diesel.html) · [źródło](v6-diesel.html) | [Podgląd](https://jkbmaj.github.io/internal-combustion-engines/v8-diesel.html) · [źródło](v8-diesel.html) | — | — |

Silniki czterosuwowe mają wtrysk bezpośredni (benzyna — GDI, diesel — wtrysk
centralny przy GMP). Dwusuw zasilany jest mieszanką przygotowaną w gaźniku
i przepłukiwany przez skrzynię korbową — bez zaworów i rozrządu, z zapłonem
co obrót. Silnik Wankla ma wtrysk do kanału dolotowego; jego trójkątny wirnik
obraca się trzykrotnie wolniej od wału mimośrodowego, a każda z trzech komór
przechodzi pełny cykl czterosuwowy na jeden obrót wirnika.

Linki „Podgląd" wymagają włączenia GitHub Pages dla tego repozytorium
(*Settings → Pages → Deploy from a branch → `main`*). Do czasu włączenia Pages
pliki można otworzyć lokalnie — są samodzielne i nie wymagają serwera ani
zewnętrznych zależności; wystarczy dowolna współczesna przeglądarka. Każda strona
zawiera pasek nawigacji umożliwiający przejście do pozostałych wariantów.

## Co pokazują animacje

**Cykl pracy.** Ładunek w cylindrze zmienia barwę zgodnie z fazą: niebieskie
powietrze podczas ssania, ciemniejący błękit sprężania, biało‑pomarańczowy błysk
spalania i suw pracy, szare spaliny podczas wydechu. Pod sufitem każdej strony
wskaźniki C1–Cn pokazują bieżący suw i jego postęp dla każdego cylindra z osobna,
co pozwala wytłumaczyć przesunięcie faz między cylindrami i równomierność pracy.

**Układ korbowy.** Ruch tłoka wynika z dokładnej kinematyki mechanizmu
korbowo‑wodzikowego (`y = R·cos θ + √(L² − R²·sin² θ)`), a nie z uproszczonej
sinusoidy — widać charakterystyczną asymetrię prędkości tłoka. Narysowane są
korbowody z pokrywami łożysk, pierścienie tłokowe, sworznie, przeciwwagi
i czopy wału.

**Rozrząd.** Nad każdą głowicą pracują dwa wałki rozrządu (DOHC) obracające się
z połową prędkości wału korbowego; krzywki naciskają szklanki zaworów, a sprężyny
zaworowe wyraźnie ściskają się przy otwarciu. Łańcuch rozrządu z ruchomymi
ogniwami łączy koło na wale korbowym z kołami wałków — na znacznikach kół widać
przełożenie 2:1. Wszystkie elementy obracają się zgodnie, w prawo.

**Zasilanie i zapłon.** W wersji benzynowej wtryskiwacz boczny podaje paliwo
bezpośrednio do cylindra w trakcie suwu ssania, a świeca zapłonowa generuje
widoczną iskrę tuż przed górnym martwym położeniem. W wersji wysokoprężnej
paliwo jest wtryskiwane centralnie w okolicy GMP i zapala się samoczynnie
od sprężonego powietrza, a świeca żarowa cyklicznie (co około 10 sekund)
rozżarza się, ilustrując wspomaganie zimnego rozruchu.

## Sterowanie

Przycisk **Pauza** zatrzymuje animację w dowolnym momencie — przydatne przy
omawianiu konkretnej fazy. Suwak **Prędkość** (0,2–3×) pozwala zwolnić przebieg
na czas tłumaczenia lub przyspieszyć go do naturalnego tempa. Animacja zapętla
się bezszwowo co pełny cykl 720°, a gdy okno lub karta przeglądarki traci fokus,
renderowanie jest automatycznie wstrzymywane dla oszczędności zasobów
i wznawiane po powrocie.

## Szczegóły techniczne

Pojedynczy plik HTML na wariant, czysty JavaScript i Canvas 2D bez bibliotek
zewnętrznych. Rendering w natywnej rozdzielczości ekranu (HiDPI). Plik
`four-stroke-engine.html` to starsza wersja zbiorcza z trzema silnikami
benzynowymi na jednej stronie, zachowana dla porównania.
