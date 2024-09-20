---
title: Automatyczne dopasowanie do okna
linktitle: Automatyczne dopasowanie do okna
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak automatycznie dopasować tabelę do okna za pomocą Aspose.PDF dla .NET w tym szczegółowym przewodniku krok po kroku. Idealny do tworzenia dopracowanych i dobrze dopasowanych tabel w plikach PDF.
type: docs
weight: 50
url: /pl/net/programming-with-tables/auto-fit-to-window/
---
## Wstęp

Podczas pracy z plikami PDF często mamy do czynienia z tabelami, a czasami potrzebujemy, aby tabele idealnie pasowały do szerokości strony. W tym samouczku pokażemy, jak automatycznie dopasować tabelę do okna za pomocą Aspose.PDF dla .NET. Dzięki temu tabele będą wyglądać schludnie i uporządkowanie, zapobiegając problemom takim jak przepełnienie lub nierówne kolumny. Gotowy do nauki? Zaczynajmy!

## Wymagania wstępne

Zanim przejdziemy do szczegółowego przewodnika, jest kilka rzeczy, których będziesz potrzebować:

1. Aspose.PDF dla .NET zainstalowany w Twoim projekcie. Jeśli jeszcze go nie masz, możesz[pobierz tutaj](https://releases.aspose.com/pdf/net/) lub je zbadaj[bezpłatna wersja próbna](https://releases.aspose.com/).
2. Podstawowa znajomość programowania .NET.
3. Visual Studio lub dowolne środowisko IDE obsługujące platformę .NET zainstalowane w systemie.

>  PS Nie zapomnij, że będziesz potrzebować licencji, aby używać Aspose.PDF bez ograniczeń. Możesz ją kupić[Tutaj](https://purchase.aspose.com/buy) lub zdobądź[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby wypróbować wszystkie funkcje.

## Importuj pakiety

Zanim zagłębisz się w kod, musisz zaimportować niezbędne przestrzenie nazw:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Skoro już wszystko wiemy, podzielmy to na proste i zrozumiałe kroki, aby zrozumieć, jak można automatycznie dopasować tabelę do okna za pomocą Aspose.PDF dla platformy .NET.

## Krok 1: Zainicjuj obiekt dokumentu

Najpierw musisz utworzyć dokument PDF. Pomyśl o tym dokumencie jako o pustym arkuszu, do którego będziesz dodawać strony i tabele.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt PDF, wywołując jego pusty konstruktor
Document doc = new Document();
```
  
 Tutaj tworzymy nowy dokument za pomocą`Document` klasa z Aspose.PDF.`dataDir` jest miejscem, w którym zostanie zapisany plik PDF po zakończeniu pracy.

## Krok 2: Dodaj stronę do dokumentu

Dokument PDF potrzebuje stron, prawda? Dodajmy jedną.

```csharp
// Utwórz sekcję (stronę) w obiekcie Pdf
Page sec1 = doc.Pages.Add();
```
  
 Dodaliśmy nową stronę do dokumentu za pomocą`Pages.Add()` metoda. Możesz to sobie wyobrazić jako dodanie nowego arkusza do dokumentu, w którym umieścisz tabelę.

## Krok 3: Utwórz i skonfiguruj tabelę

Teraz czas utworzyć tabelę i dopasować ją do okna.

```csharp
// Utwórz obiekt tabeli
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Dodaj tabelę w kolekcji akapitów żądanej sekcji
sec1.Paragraphs.Add(tab1);
```
  
 Zainicjowaliśmy nowy`Table` obiekt i dodaliśmy go do kolekcji akapitów strony. Każda strona PDF może mieć różne akapity, a tutaj traktujemy tabelę jako akapit.

## Krok 4: Zdefiniuj szerokości kolumn i dopasuj je automatycznie do okna

Następnie ustawiamy szerokości kolumn i upewniamy się, że tabela dostosowuje się do rozmiaru okna.

```csharp
// Ustaw szerokości kolumn dla tabeli
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Ustawiliśmy stałe szerokości kolumn dla tabeli, ale dodaliśmy także`ColumnAdjustment.AutoFitToWindow`, co zapewnia dopasowanie rozmiaru tabeli do dostępnego okna.

## Krok 5: Ustaw obramowania i marginesy dla tabeli i komórek

Tabele bez obramowań są często nieczytelne. Zdefiniujmy obramowania i marginesy, aby wyglądały schludnie.

```csharp
// Ustaw domyślną ramkę komórki za pomocą obiektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ustaw obramowanie tabeli za pomocą innego dostosowanego obiektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

// Utwórz obiekt MarginInfo i ustaw jego marginesy: lewy, dolny, prawy i górny
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Ustaw domyślne wypełnienie komórki na obiekt MarginInfo
tab1.DefaultCellPadding = margin;
```
  
 Obramowania są dodawane zarówno do tabeli, jak i komórek za pomocą`BorderInfo` klasa, w której definiujesz grubość. Marginesy są ustawione, aby dać komórkom trochę miejsca na wypełnienie.

## Krok 6: Dodaj wiersze i komórki do tabeli

Tabela bez zawartości? To nic dobrego! Dodajmy kilka wierszy i komórek.

```csharp
//Utwórz wiersze w tabeli, a następnie komórki w wierszach
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Tworzymy dwa wiersze i dodajemy trzy komórki do każdego wiersza. Tutaj wprowadzisz swoje rzeczywiste dane (które mogą być wszystkim, od ciągów znaków po bardziej złożone elementy).

## Krok 7: Zapisz dokument

Gdy wszystko będzie już gotowe, należy zapisać nowo utworzony dokument PDF.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Zapisz zaktualizowany dokument zawierający obiekt tabeli
doc.Save(dataDir);
```
  
 Ten`doc.Save()` Metoda zapisuje plik PDF do określonego katalogu. W tym przypadku dokument zostanie zapisany jako`AutoFitToWindow_out.pdf` w zdefiniowanym przez Ciebie katalogu.

## Wniosek

masz! Właśnie utworzyłeś tabelę, która automatycznie pasuje do okna, używając Aspose.PDF dla .NET. To nie tylko zapewnia, że Twoja tabela wygląda profesjonalnie i jest dobrze dopasowana, ale także daje Ci elastyczność podczas pracy z różnymi rozmiarami danych. Niezależnie od tego, czy tworzysz raporty, faktury czy jakikolwiek dokument wymagający tabel, ta metoda jest świetnym sposobem na utrzymanie czystych i czytelnych układów.

## Najczęściej zadawane pytania

### Czy mogę dynamicznie dodawać więcej wierszy?  
 Tak, możesz nadal dodawać wiersze za pomocą`tab1.Rows.Add()` metoda dynamicznie oparta na zawartości.

### Jak wyregulować stół, jeśli nie chcę, aby dopasowywał się automatycznie?  
 Możesz ustawić ręcznie`ColumnWidths` bez użycia`ColumnAdjustment.AutoFitToWindow` aby zachować stałą szerokość tabeli.

### Czy mogę dodać obrazy i inną treść do komórek?  
Tak, Aspose.PDF pozwala na dodawanie obrazów, tekstu, a nawet innych tabel wewnątrz komórek!

### A co jeśli potrzebuję bardziej złożonych stylów tabeli?  
Możesz dodatkowo dostosować style tabeli i komórek, używając właściwości, takich jak kolor tła, wyrównanie tekstu i ustawienia czcionki.

### Czy można wyeksportować tę tabelę do innych formatów niż PDF?  
Oczywiście! Aspose.PDF obsługuje eksportowanie do różnych formatów, takich jak HTML, DOCX i inne.