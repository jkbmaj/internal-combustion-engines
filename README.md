# Silniki spalinowe — interaktywne wizualizacje

Zestaw animacji HTML/Canvas (bez zależności) przeznaczony jako pomoc dydaktyczna
przy tłumaczeniu zasady działania silników spalinowych osobom, które nie miały
z nią wcześniej styczności. Każda animacja pokazuje w czasie rzeczywistym pełny
cykl pracy — w czterosuwach ssanie, sprężanie, pracę i wydech na przestrzeni
720° obrotu wału — wraz z kompletem zależności mechanicznych: układem korbowym,
rozrządem, zasilaniem i zapłonem.

**Start:** [otwórz przeglądarkę silników (index)](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/index.html) —
wszystkie konstrukcje w jednym miejscu, ładowana jest tylko wybrana.
Pełna funkcjonalność (w tym nawigacja między silnikami) po włączeniu GitHub Pages
(*Settings → Pages → Deploy from a branch → `main`*), wtedy całość działa pod
adresem `https://jkbmaj.github.io/internal-combustion-engines/`.

## Silniki

Linki „Podgląd" otwierają działającą animację bezpośrednio z GitHuba.

| Silnik | Układ i zapłon | Podgląd | Źródło |
|---|---|---|---|
| **R4** benzyna | rzędowy 4-cyl, widok z boku · 1-3-4-2 co 180° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/r4-benzyna.html) | [kod](r4-benzyna.html) |
| **R4** diesel | jak wyżej · wtrysk przy GMP, świeca żarowa, turbo | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/r4-diesel.html) | [kod](r4-diesel.html) |
| **R6** | rzędowy 6-cyl · 1-5-3-6-2-4 co 120° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/r6-benzyna.html) | [kod](r6-benzyna.html) |
| **VR6** | wąskie V 15°, jedna głowica · 1-5-3-6-2-4 co 120° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/vr6-benzyna.html) | [kod](vr6-benzyna.html) |
| **V6** benzyna | rozwarcie 60° · zapłon co 120° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v6-benzyna.html) | [kod](v6-benzyna.html) |
| **V6** diesel | jak wyżej · zapłon samoczynny, turbo | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v6-diesel.html) | [kod](v6-diesel.html) |
| **V8** benzyna | rozwarcie 90°, wał płaski · zapłon co 90° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v8-benzyna.html) | [kod](v8-benzyna.html) |
| **V8** diesel | jak wyżej · zapłon samoczynny, turbo | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v8-diesel.html) | [kod](v8-diesel.html) |
| **V10** | rozwarcie 72° · zapłon co 72° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v10-benzyna.html) | [kod](v10-benzyna.html) |
| **V12** | rozwarcie 60° · zapłon co 60° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v12-benzyna.html) | [kod](v12-benzyna.html) |
| **V16** | rozwarcie 45° · zapłon co 45° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/v16-benzyna.html) | [kod](v16-benzyna.html) |
| **W16** | dwa VR 15° pod 90° (±37,5° i ±52,5°) · co 45° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/w16-benzyna.html) | [kod](w16-benzyna.html) |
| **Boxer B4** | cylindry przeciwsobne · 1-3-2-4 co 180° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/boxer-benzyna.html) | [kod](boxer-benzyna.html) |
| **Gwiazdowy R5** | 5 cylindrów co 72° · 1-3-5-2-4 co 144° | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/gwiazdowy-benzyna.html) | [kod](gwiazdowy-benzyna.html) |
| **Dwusuw R1** | cykl w 360°, sterowanie tłokiem | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/dwusuw-benzyna.html) | [kod](dwusuw-benzyna.html) |
| **Wankel** | 1 wirnik, 3 komory, wirnik ⅓ obrotów wału | [Podgląd](https://htmlpreview.github.io/?https://github.com/jkbmaj/internal-combustion-engines/blob/main/wankel-benzyna.html) | [kod](wankel-benzyna.html) |

## Co pokazują animacje

**Cykl pracy.** Ładunek w cylindrze zmienia barwę zgodnie z fazą: niebieskie
powietrze podczas ssania, ciemniejący błękit sprężania, biało-pomarańczowy
błysk spalania i suw pracy, szare spaliny podczas wydechu. Wskaźniki C1–Cn
pokazują bieżący suw i jego postęp dla każdego cylindra z osobna.

**Układ korbowy.** Ruch tłoka wynika z dokładnej kinematyki mechanizmu
korbowo-wodzikowego (`y = R·cos θ + √(L² − R²·sin² θ)`); narysowane są
korbowody z pokrywami łożysk, pierścienie tłokowe, sworznie, przeciwwagi
i czopy. Prędkość wału delikatnie pulsuje w takt suwów pracy — im mniej
cylindrów, tym wyraźniej.

**Rozrząd.** Wałki DOHC obracają się z połową prędkości wału, krzywki naciskają
szklanki, sprężyny zaworowe ściskają się przy otwarciu, a łańcuch rozrządu
z ruchomymi ogniwami łączy koła o przełożeniu 2:1. Dwusuw i Wankel celowo nie
mają rozrządu — wymianą ładunku steruje tłok lub wirnik.

**Zasilanie i zapłon.** Benzyna: wtrysk bezpośredni podczas ssania i widoczna
iskra tuż przed GMP. Diesel: wtrysk centralny przy GMP, zapłon samoczynny,
okresowo rozżarzająca się świeca żarowa oraz moduł turbosprężarki.

## Narzędzia prezentacyjne

Pauza · krok **+15°** obrotu wału · przełącznik **Etykiety** z opisami części ·
wskaźnik kąta wału (720° dla czterosuwów, 360° dla dwusuwu) · wykres ciśnienia
**p(θ)** z markerem bieżącej fazy · regulacja prędkości 0,2–3×. Rendering jest
automatycznie wstrzymywany, gdy karta traci fokus.

## Zgodność ze schematami

Kolejności zapłonu i geometrie zweryfikowane z literaturą: R4 1-3-4-2,
R6 i VR6 1-5-3-6-2-4, boxer 1-3-2-4, gwiazdowy 1-3-5-2-4 (nieparzysta liczba
cylindrów), V6 60°/120°, V10 72°/72°, V12 60°/60°, W16 jako dwa zespoły VR
rozchylone o 90°, Wankel na dokładnej epitrochoidzie z wirnikiem o ⅓ prędkości
wału. Świadome uproszczenia: V8 pokazano z wałem płaskim (równy odstęp 90°,
naprzemienne banki — jak w silnikach sportowych; wał krzyżowy ma nierówną
sekwencję w bankach), gwiazdowy narysowano z głowicami DOHC zamiast popychaczy
z pierścieniem krzywkowym, dwusuw łączy zawór płytkowy z dolotem sterowanym
tłokiem, a Wankel ma jedną świecę zamiast dwóch. Fazy rozrządu i kąt wtrysku
pokazano bez wyprzedzeń regulacyjnych.

## Technika

Każdy silnik to samodzielny plik HTML (czysty JavaScript + Canvas 2D, zero
bibliotek); `index.html` to przeglądarka wszystkich konstrukcji. Rendering
w natywnej rozdzielczości ekranu, pętla animacji bezszwowa co pełny cykl.
