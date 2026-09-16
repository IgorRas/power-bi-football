# ⚽ Panel analityczny klubów piłkarskich

Interaktywny dashboard wykonany w **Microsoft Power BI**, służący do analizy danych dotyczących klubów piłkarskich, zawodników, transferów oraz meczów.

Projekt skupia się na praktycznym wykorzystaniu **modelowania danych, języka DAX oraz interaktywnych wizualizacji** do tworzenia dynamicznego raportu analitycznego.

---

## ✨ Features

* 🔎 **Dynamiczne filtrowanie** danych za pomocą slicerów
* 📈 Analiza wyników i statystyk meczowych
* 💰 Analiza transferów i bilansu transferowego
* 👥 Analiza zawodników i ich wartości
* 🏟️ Analiza frekwencji oraz stadionów
* 📊 Dynamiczne KPI i miary
* 🎨 Conditional formatting dla czytelniejszej prezentacji danych
* 🔄 Automatyczna aktualizacja wizualizacji na podstawie wybranych filtrów

---

## 🛠️ Tech Stack

| Technologia                | Zastosowanie                           |
| -------------------------- | -------------------------------------- |
| **Power BI**               | Dashboard i wizualizacja danych        |
| **DAX**                    | Miary, obliczenia i logika analityczna |
| **Data Modeling**          | Model danych i relacje między tabelami |
| **Power BI Slicers**       | Interaktywne filtrowanie               |
| **Conditional Formatting** | Dynamiczne formatowanie wizualizacji   |

---

## 🗂️ Model danych

Projekt wykorzystuje relacyjny model danych składający się z tabel dotyczących m.in.:

* klubów,
* zawodników,
* transferów,
* meczów,
* stadionów,
* frekwencji.

Relacje między tabelami umożliwiają propagowanie filtrów oraz analizowanie danych w zależności od wybranego klubu.

### Przykładowy przepływ filtrowania

```text
Wybór klubu
     ↓
Slicer
     ↓
Kontekst filtrowania
     ↓
Miary DAX
     ↓
Wizualizacje / KPI
```

---

## 🧮 DAX

W projekcie wykorzystano zarówno podstawowe funkcje agregujące, jak i funkcje pozwalające na pracę z kontekstem filtrowania.

W przypadku bardziej złożonych obliczeń wykorzystano również zmienne `VAR`, aby zwiększyć czytelność i ułatwić ponowne wykorzystanie wyników pośrednich.

### Przykład

```DAX
Home Attendance =
VAR SelectedClub =
    SELECTEDVALUE(clubs[club_id])

VAR Attendance =
    CALCULATE(
        AVERAGE(games[attendance]),
        games[home_club_id] = SelectedClub
    )

RETURN
    Attendance
```

Miara wykorzystuje wartość wybraną przez użytkownika w slicerze i na jej podstawie oblicza średnią frekwencję dla meczów domowych danego klubu.

---

## 🎛️ Interaktywność

Jednym z głównych założeń projektu było stworzenie raportu, który reaguje na wybory użytkownika.

Przykładowo:

**Wybór klubu → aktualizacja KPI → aktualizacja wykresów → aktualizacja statystyk**

Pozwala to analizować konkretny klub bez konieczności tworzenia osobnych raportów lub wizualizacji dla każdego przypadku.

---

## 🎯 Cel projektu

Projekt został stworzony w celu rozwijania praktycznych umiejętności związanych z:

* **Power BI**
* **DAX**
* **modelowaniem danych**
* **analizą danych**
* **tworzeniem interaktywnych dashboardów**
* **wizualizacją danych**

Projekt stanowi przykład wykorzystania narzędzi Business Intelligence do analizy danych sportowych i prezentowania wyników w przystępnej, interaktywnej formie.

