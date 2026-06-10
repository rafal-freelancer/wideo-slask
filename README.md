# Strona — depilacja laserowa premium

Landing page Rafała Małoty: system pozyskiwania klientek premium na depilację laserową.

---

## Co jest w pakiecie

| Plik | Co to | Rozmiar |
|---|---|---|
| `index.html` | Cała strona — HTML, CSS i JavaScript w jednym pliku | ~70 KB |
| `depilacja.png` | Screen wyników kampanii Warszawa (60 leadów, 24,97 zł/lead) | ~512 KB |
| `mezoterapia.png` | Screen wyników kampanii Gdańsk (37 leadów, 40,37 zł/lead) | ~688 KB |
| `makijaz.png` | Screen wyników kampanii Kielce (25 leadów, 59,65 zł/lead) | ~675 KB |
| `rafal.png` | Twój portret do sekcji „O mnie" | ~1,2 MB |
| `portfolio-1.jpg` … `portfolio-9.jpg` | 9 zdjęć z sesji do sekcji Portfolio (grid 3×3) | ~45–130 KB każde |
| `opinia-poster.jpg` | Miniatura pod wideo z opinią klientki (poziome 16:9) | ~75 KB |
| `moma-1.jpg` … `moma-6.jpg` | 6 zdjęć z sesji moma beauty lounge (grid 3×2) | ~42–70 KB każde |

**Ważne:** nazwy plików muszą być dokładnie takie jak wyżej (małe litery, bez polskich znaków). Plik `index.html` odwołuje się do nich po nazwie.

---

## Dwa wideo w sekcji Portfolio — jak podpiąć

W sekcji „Portfolio · realizacje" są dwa miejsca na wideo (9:16, pionowe). Teraz pokazują tylko miniaturkę ze zdjęciem — nie odtwarzają się, dopóki nie wkleisz ID filmu z YouTube.

1. Wgraj oba filmy na YouTube (mogą być niepubliczne / „niepubliczne z linkiem")
2. Skopiuj ID każdego filmu z adresu — np. w `youtube.com/watch?v=AFnpVkSqo58` ID to `AFnpVkSqo58`
3. W `index.html` znajdź `data-yt="ID_WIDEO_1"` (realizacja Kielce) i `data-yt="ID_WIDEO_2"` (realizacja Warszawa)
4. Podmień `ID_WIDEO_1` i `ID_WIDEO_2` na realne ID swoich filmów
5. Wideo z opinią klientki: znajdź `data-yt="ID_WIDEO_OPINIA"` i podmień na ID filmu z opinią (do tego czasu wyświetla się miniatura `opinia-poster.jpg`)

Po podmianie kliknięcie w miniaturkę odpali wideo. Dopóki tego nie zrobisz, miniaturka po prostu nie reaguje na klik (żeby nie pokazywać błędu).

Możesz też podmienić zdjęcia-miniaturki pod wideo — szukaj `portfolio-4.jpg` (Kielce) i `portfolio-9.jpg` (Warszawa) w sekcji portfolio.

---

## Jak wrzucić na GitHub (Twoje obecne repo `wideo-slask`)

### 1. Usuń stare pliki z repo

W GitHubie wejdź do repozytorium `wideo-slask` i usuń wszystkie obecne pliki:
- `index.html` (stary)
- `photo.jpg`
- `photo.png`
- `wyniki1.png`
- `wyniki2.webp`
- `wyniki3.png`
- `wyniki4.png`
- `wyniki5.webp`
- `wyniki6.png`

Klikasz każdy plik → ikona kosza w prawym górnym rogu → Commit changes.

### 2. Wgraj nowe pliki

W repo kliknij **Add file → Upload files**. Przeciągnij wszystkie pliki z tego pakietu naraz:
- `index.html`
- `depilacja.png`
- `mezoterapia.png`
- `makijaz.png`
- `rafal.png`
- `portfolio-1.jpg` … `portfolio-9.jpg` (dziewięć zdjęć)

Klikasz **Commit changes**.

### 3. Sprawdź GitHub Pages

W repo wejdź w **Settings → Pages** i upewnij się, że:
- **Source:** Deploy from a branch
- **Branch:** `main` (lub `master`), folder: `/ (root)`
- Klikasz **Save**

GitHub Pages automatycznie wdraża po commicie — czas wdrożenia to zwykle 1–2 minuty. Adres strony pozostaje ten sam co teraz (najpewniej `https://rafal-freelancer.github.io/wideo-slask/`).

---

## Co warto sprawdzić po wdrożeniu

**Desktop:**
- Hero — VSL siedzi centralnie, miniaturka się ładuje, kliknięcie odpala wideo z autoplay
- Wyniki — 3 screeny w jednej linii: Warszawa / Gdańsk / Kielce
- Cennik — dwie kolumny, biała karta cennika obok ciemnej karty budżetu, tej samej wysokości
- Portret w „O mnie" wypełnia kontener

**Mobile (otwórz na telefonie):**
- Sticky CTA „Umów konsultację telefoniczną" zawsze widoczne na dole ekranu
- Wszystkie sekcje schodzą do jednej kolumny
- Hero VSL ładuje się na pełnej szerokości

---

## Co zmienić w treści, jak chcesz

Wszystko jest w `index.html`. Otwierasz w edytorze (VS Code, Sublime, Notepad++) i szukasz tekstu, który chcesz zmienić.

**Typowe edycje:**

| Co | Gdzie szukać w `index.html` |
|---|---|
| Tytuł hero | Linia z `Depilacja laserowa,` |
| Cytat w sekcji bólu | Linia z `Jaka cena<br>zabiegu?` |
| Cena 2 500 zł | Linia z `<div class="price-figure">2 500` |
| Link do YouTube w VSL | Szukaj `AFnpVkSqo58` (2 miejsca — poster i embed) |
| Email / telefon | Linki w stopce — sekcja `<footer>` |
| Instagram / Facebook | Linki w stopce — sekcja `ft-socials` |

---

## Co dorobić w przyszłości (nieobowiązkowe)

- **Domena własna** zamiast `github.io` — w Settings → Pages dodajesz Custom domain, np. `rafalmalota.pl/depilacja-laserowa`
- **Favicon** — dodajesz plik `favicon.ico` w głównym katalogu, automatycznie się załaduje
- **Open Graph** — tagi dla podglądu linku przy udostępnianiu w social media (dorzucam jeśli będziesz chciał)
- **Backend formularza** — w tej chwili formularz nie wysyła nic. Trzeba podpiąć np. Formspree, Tally albo własny endpoint
- **Tracking pixel Meta** — żeby kampanie Meta widziały konwersje z formularza

Jak będziesz potrzebować któregoś z tych punktów, daj znać — zrobię.
