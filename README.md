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
| `portfolio-1.jpg` … `portfolio-9.jpg` | Zdjęcia z sesji Remedy. W galerii użyte jest 6: 1, 2, 4, 5, 6, 9 (grid 3 rzędy × 2). Pliki 3, 7, 8 zostają w paczce, ale nie są używane | ~45–130 KB każde |
| `opinia-poster.jpg` | Miniatura-fallback pod wideo z opinią (póki nie ma ID z YouTube) | ~75 KB |
| `moma-1.jpg` … `moma-6.jpg` | 6 zdjęć z sesji moma beauty lounge (grid 3 rzędy × 2) | ~42–70 KB każde |

**Ważne:** nazwy plików muszą być dokładnie takie jak wyżej (małe litery, bez polskich znaków). Plik `index.html` odwołuje się do nich po nazwie.

---

## Wideo: 6 realizacji + opinia — jak podpiąć

W sekcji „Realizacje · reklamy wideo" jest **6 miejsc na pionowe reele (9:16)**, ułożone 3 w rzędzie × 2 rzędy (na telefonie 2 w rzędzie). Osobno, niżej, jest **wideo z opinią klientki** (poziome 16:9).

**Miniatury pobierają się automatycznie z YouTube** — nie trzeba żadnych plików-posterów. Strona sama zaciąga miniaturę z serwera YouTube: dla pionowych reeli bierze kadr w oryginalnych (pionowych) proporcjach, dla opinii (16:9) wersję hi-res.

**Filmy są już wpięte** — ID wszystkich 7 filmów są podstawione w `index.html`, nic nie trzeba podmieniać. Warunek: filmy na YouTube muszą być **publiczne** albo **niepubliczne (z linkiem)** — przy ustawieniu „prywatny" miniatura i odtwarzanie nie zadziałają.

Wpięte ID (gdyby kiedyś trzeba było zmienić — szukaj `data-yt="..."` w `index.html`):

| Miejsce | ID |
|---|---|
| Opinia (16:9) | `a29EvlRRqq8` |
| Realizacja 1 | `H7qjE0vkblI` |
| Realizacja 2 | `lQuFrrre3OY` |
| Realizacja 3 | `ra1ebdzxq8M` |
| Realizacja 4 | `FQaXFT-HjSo` |
| Realizacja 5 | `UtpQqg5B8iA` |
| Realizacja 6 | `_edr_0yScbQ` |

Kliknięcie w kafelek odpala film w miejscu (bez wychodzenia ze strony).

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
