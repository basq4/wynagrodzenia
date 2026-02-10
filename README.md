# 💰 Kalkulator Wynagrodzenia Netto 2026

Lekka aplikacja webowa do obliczania wynagrodzenia netto z umowy o pracę na rok 2026. Uwzględnia wszystkie składki ZUS, składkę zdrowotną, podatek PIT (progresywny), PPK, ulgi podatkowe oraz limity roczne.

## ✨ Funkcje

- ✅ **Pełne rozliczenie miesięczne** — ZUS (emerytalna, rentowa, chorobowa), zdrowotna, PIT
- ✅ **Limit 30-krotności** — automatyczne wyłączanie składek emerytalnej/rentowej po przekroczeniu 282 600 zł
- ✅ **Progresywny PIT** — 12% do 120 000 zł, 32% powyżej
- ✅ **Kwota wolna** — 30 000 zł rocznie (PIT-2)
- ✅ **Ulga dla młodych** — zwolnienie z PIT do 85 528 zł dla osób do 26. roku życia
- ✅ **PPK** — składki pracownika (0,5–4%) i pracodawcy (1,5–4%)
- ✅ **Koszty uzyskania przychodu** — 0/250/300 zł miesięcznie
- ✅ **Premie miesięczne** — możliwość dodania zmiennych składników wynagrodzenia
- ✅ **Wykres i tabele** — wizualizacja zmian netto w poszczególnych miesiącach
- ✅ **Koszt pracodawcy** — pełne zestawienie obciążeń (FP, FGŚP, składki)

## 🚀 Szybki start

### Uruchomienie lokalnie

```bash
# Otwórz plik bezpośrednio w przeglądarce
open index.html

# lub uruchom prosty serwer HTTP
python3 -m http.server 8000
# Otwórz: http://localhost:8000
```

### Uruchomienie w Docker

```bash
# Zbuduj i uruchom
docker compose up -d

# Aplikacja dostępna pod:
# http://localhost:8080
```

### Zatrzymanie kontenera

```bash
docker compose down
```

## 📋 Wymagania

- **Lokalne uruchomienie**: Przeglądarka (Chrome, Firefox, Safari, Edge)
- **Docker**: Docker Engine + Docker Compose

## 🔧 Parametry do dostosowania

Kalkulator pozwala na edycję wszystkich stawek i limitów w sekcji **„Zaawansowane"**:

| Parametr | Wartość domyślna (2026) |
|----------|-------------------------|
| Składka emerytalna | 9,76% |
| Składka rentowa | 1,50% |
| Składka chorobowa | 2,45% |
| Składka zdrowotna | 9,00% |
| PIT I próg | 12% (do 120 000 zł) |
| PIT II próg | 32% (powyżej 120 000 zł) |
| Kwota wolna | 30 000 zł |
| Limit ZUS 30-krotność | 282 600 zł |
| Limit ulgi <26 | 85 528 zł |

## 📖 Jak korzystać

1. Wpisz **wynagrodzenie brutto miesięczne**
2. Wybierz **koszty uzyskania przychodu** (0/250/300 zł)
3. Zaznacz **PIT-2**, jeśli złożyłeś oświadczenie u pracodawcy
4. Opcjonalnie: zaznacz **PPK**, **ulgę <26**, dodaj **premie miesięczne**
5. Kliknij **„Oblicz wynagrodzenie netto"**

Wyniki obejmują:
- Roczne i miesięczne podsumowanie netto
- Wykres zmian netto w poszczególnych miesiącach
- Szczegółową tabelę z rozpisaniem składek i podatku
- Całkowity koszt pracodawcy (z FP, FGŚP, PPK)

## 🛠️ Technologie

- **HTML5** + **JavaScript (vanilla)** — zero zależności
- **Pico CSS** — lekki framework CSS (~10 KB)
- **Docker** — konteneryzacja z nginx:alpine

## 📊 Zakres obliczeń

Kalkulator stosuje metodę **kumulatywną** naliczania zaliczek na podatek dochodowy, zgodnie z przepisami obowiązującymi w 2026 roku:

- Składki ZUS (społeczne) odliczane przed obliczeniem podstawy opodatkowania
- Składka zdrowotna nieodliczalna od podatku
- Kwota zmniejszająca podatek (300 zł/mies.) przy złożonym PIT-2
- PPK pracodawcy zwiększa podstawę opodatkowania (przychód podatkowy)
- Ulga dla młodych: zwolnienie do limitu 85 528 zł **przychodu brutto** rocznie

## ⚠️ Zastrzeżenia

Kalkulator ma **charakter informacyjny**. Rzeczywiste wynagrodzenie może się różnić w zależności od:
- indywidualnej sytuacji podatkowej,
- odliczeń i ulg podatkowych (np. ulga rehabilitacyjna, odliczenia składek zdrowotnych osób prowadzących działalność),
- zmian w przepisach w trakcie roku.

Zaleca się weryfikację obliczeń z działem kadr lub księgowym.

## 📄 Licencja

MIT License — możesz swobodnie używać i modyfikować.

## 🤝 Kontakt

W razie pytań lub sugestii:
- Otwórz **Issue** w repozytorium
- Wyślij **Pull Request** z poprawkami

---

**Wersja:** 1.0.0  
**Data wydania:** Luty 2026  
**Zgodność:** Przepisy 2026 (PIT, ZUS, składka zdrowotna)
