# Notatki deweloperskie (stan projektu dla kontynuacji pracy)

Repo: `git@github.com:jkbmaj/internal-combustion-engines.git`, gałąź `main`.
Jakub commituje… a właściwie: asystent commituje lokalnie po każdej zmianie,
Jakub robi `git push` ze swojego komputera (SSH z sandboksa zablokowane).

## Pliki (17)

`index.html` — przeglądarka wszystkich silników (kafelki + iframe, jeden naraz).
Silniki (samodzielne pliki, wspólna konwencja):
r4/v6/v8 ×(benzyna|diesel), r6, vr6, v10, v12, v16, w16, boxer, gwiazdowy,
dwusuw, wankel (poza dwusuwem i wanklem wszystkie czterosuwowe).
`README.md` — tabela z linkami htmlpreview.github.io (renderują od razu).

## Architektura pliku silnika

Jeden `<script>`: stałe → `gasStyle` (kolory faz) → `strokeChip` → `GEO/DECK/LINER`
→ `slider(ph)` (kinematyka korbowa) → `chain/sprocket` → `drawCyl(g, bx, by, phi,
ph, shade, front, mir)` → blok silnika (`V6`/`I4`/`RD` const + `renderXX`) →
`OCFG` + overlay (HUD kąta, wykres p(θ), etykiety, `torqueMul` pulsy, turbo
w dieslach) → pętla (pauza, +15°, etykiety, prędkość, auto-suspend przy blur).

Kluczowe konwencje:
- cykl 4T: `t ∈ [0, 4π)`, TDC przy ph=0 mod 2π; 2T: `[0, 2π)`; pętle bezszwowe
- widoki: R4/R6/VR6/dwusuw/wankel z boku; V/W/boxer/gwiazdowy wzdłuż wału
  (kolejne wykorbienia pionowo w górę, D px na poziom)
- `mir=true` dla lewych banków (odbicie osprzętu głowicy — dolot w dolinie V);
  czop/korbowód bez odbicia
- diesel = brak iskry, wtryskiwacz centralny + świeca żarowa (żarzy ~3 s co 10 s),
  dolot samo powietrze, moduł turbo w overlay
- benzyna = GDI (boczny wtryskiwacz, spray przy otwartym ssaniu), iskra przed TDC
- wszystko kręci się w prawo (łańcuch: offset ujemny w `chain()`)

## Zmiany robione są patcherami

Preferowany sposób edycji wielu plików: python w bashu, `str.replace` z assertem
liczby wystąpień (patrz historia commitów). Po każdej zmianie: `node --check`
na wyciętym skrypcie + commit z opisem po polsku (bez polskich znaków w commit msg).

## Wiedza merytoryczna (zweryfikowana)

Kolejności zapłonu: R4 1-3-4-2 · R6/VR6 1-5-3-6-2-4 · boxer 1-3-2-4 ·
gwiazdowy 1-3-5-2-4 · V6 60°/120° · V8 flat-plane 90°/90° · V10 72°/72° ·
V12 60°/60° · V16 45°/45° · W16 = 2×VR 15° pod 90° (±37,5°/±52,5°), 4 wykorbienia
× 4 cylindry. Wankel: epitrochoida `P(a)=e·(cos3a,sin3a)+R·(cosa,sina)`,
wirnik ⅓ obrotów wału, świeca przy końcu długiej osi. Uproszczenia opisane
w README (sekcja „Zgodność ze schematami").

## Do zrobienia / otwarte

- `git push` (Jakub) i włączenie GitHub Pages → wtedy index + nawigacja działają
  pod jkbmaj.github.io/internal-combustion-engines
- ewentualne pomysły niewdrożone: dwie świece w Wanklu, cross-plane V8 jako
  wariant, dźwięk, tryb mobilny
