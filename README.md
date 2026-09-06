# PrimeShield Qwen Color Visualizer v6 – Rich Catalog

Wersja przygotowana do wdrożenia jako moduł strony PrimeShield. Mechanika Make/Qwen oraz webhook pozostają zgodne z v5, ale katalog jest przeniesiony do osobnego pliku i zastąpiony rzeczywistymi pozycjami z dostarczonego PDF.

## Struktura
- `index.html` – tylko struktura strony
- `visualizer.css` – styl modułu zgodny z PrimeShield
- `visualizer.js` – upload, wyszukiwarka, filtry, Make/Qwen, wynik
- `data/films.json` – 289 bogatych rekordów katalogowych
- `data/films.csv` – wygodny audyt danych
- `samples/reference/` – próbki wysyłane do Qwen jako drugie zdjęcie
- `samples/source-card/` – źródłowy wycinek karty katalogowej do kontroli
- `make-blueprint-primeshield-qwen.json` – scenariusz Make

## Ważne
Katalog zawiera 289 rekordów i 286 różnych kodów. W źródłowym PDF występują trzy kody przypisane do dwóch różnych nazw; nie zostały arbitralnie nadpisane. Lista jest w `data/source-code-conflicts.json`.

## Metallic
Produkty jawnie oznaczone `Metallic` / `Liquid Metallic` mają rozbudowany profil renderowania i osobny prompt wymuszający widoczne drobne metaliczne ziarno. Produkty łączone, np. `Satin Liquid Metallic Blue`, zachowują jednocześnie efekt metaliczny i satynową charakterystykę odbić.

## Dodawanie produktu
Dodaj rekord do `data/films.json` i obraz referencyjny do `samples/reference/`. Frontendu ani Make nie trzeba przebudowywać.

## Hosting
Wgraj cały folder. `index.html` pobiera `data/films.json` przez `fetch`, więc samo otwarcie pliku z `file://` może nie działać; na Cloudflare Pages działa normalnie.
