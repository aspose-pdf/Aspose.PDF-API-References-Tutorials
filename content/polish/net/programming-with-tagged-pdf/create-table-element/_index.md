---
title: Utwórz element tabeli
linktitle: Utwórz element tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku, jak utworzyć element tablicy za pomocą Aspose.PDF dla platformy .NET. Łatwe generowanie dynamicznych plików PDF z tabelami.
type: docs
weight: 80
url: /pl/net/programming-with-tagged-pdf/create-table-element/
---
## Wstęp

Czy kiedykolwiek zastanawiałeś się, jak bez wysiłku tworzyć i dostosowywać elementy tabeli w pliku PDF przy użyciu .NET? Cóż, Aspose.PDF dla .NET to Twoje rozwiązanie! Niezależnie od tego, czy automatyzujesz generowanie raportów, czy dynamicznie tworzysz tabele dla różnych dokumentów, Aspose.PDF zapewnia bogate API do pracy z elementami tabeli. Ten przewodnik przeprowadzi Cię krok po kroku przez proces tworzenia tabeli, nadawania jej stylu, a nawet upewnienia się, że spełnia ona standardy zgodności PDF/UA. Brzmi ekscytująco, prawda? Zanurzmy się w tym!

## Wymagania wstępne

Zanim zaczniemy, będziesz potrzebować kilku rzeczy:
1.  Aspose.PDF dla .NET: Pobierz najnowszą wersję z[Aspose.PDF dla .NET Pobierz](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: dowolne środowisko IDE obsługujące platformę .NET (np. Visual Studio).
3. Podstawowa znajomość języka C#: Zalecana jest znajomość programowania w języku C#.

 Na koniec nie zapomnij o swojej licencji Aspose.PDF. Jeśli jej nie masz, możesz użyć[bezpłatny okres próbny](https://releases.aspose.com/) lub poproś o[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) żeby wszystko przetestować.

## Importuj pakiety

Najpierw najważniejsze — zaimportujmy niezbędne pakiety. Pozwoli nam to pracować ze wszystkimi odpowiednimi klasami do tworzenia tabel w dokumentach PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

W tej sekcji podzielimy proces tworzenia tabeli na kilka kroków. Każdy krok koncentruje się na różnych częściach procesu tworzenia i dostosowywania tabeli.

## Krok 1: Utwórz nowy dokument PDF

Pierwszą rzeczą, którą musimy zrobić, jest utworzenie nowego dokumentu PDF. Będzie on służył jako kontener dla naszej tabeli.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument PDF
Document document = new Document();
```

 Tutaj inicjujemy nową instancję`Document` class, który będzie naszym pustym plikiem PDF. Nie zapomnij zdefiniować ścieżki do pliku!

## Krok 2: Skonfiguruj oznaczoną treść

Następnie musimy włączyć oznaczoną zawartość, co zapewni dostępność tabeli. Oznaczone pliki PDF są wymagane do zgodności z PDF/UA (Universal Accessibility).

```csharp
// Włącz oznaczoną zawartość
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Ten krok ustawia tytuł i język dokumentu, zapewniając zgodność tabeli ze standardami dostępności. Posiadanie dostępnych dokumentów jest kluczowe dla doświadczenia użytkownika i wymogów prawnych w niektórych branżach.

## Krok 3: Utwórz element tabeli

A teraz zaczyna się najlepsza część — tworzenie samej tabeli!

```csharp
// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Tutaj używamy`RootElement` oznaczonej zawartości, aby dołączyć naszą tabelę. To w zasadzie dodanie tabeli jako węzła podrzędnego do struktury dokumentu.

## Krok 4: Dostosuj obramowania i nagłówki tabeli

Nie chcesz, żeby Twój stół wyglądał nijako, prawda? Dodajmy trochę stylu!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Definiujemy obramowania i dodajemy nagłówki, treść i stopki do tabeli. Zwróć uwagę na użycie`BorderInfo` aby nadać obramowaniu stołu ciemnoniebieski kolor.

## Krok 5: Dodaj wiersze i komórki do tabeli

Teraz wypełnijmy naszą tabelę wierszami i komórkami. Ta część procesu to miejsce, w którym definiujemy układ naszej tabeli.

### Krok 5.1: Utwórz wiersz nagłówka

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Tworzymy wiersz nagłówka z 4 kolumnami, a każda komórka nagłówka jest stylizowana kolorem tła`GreenYellow`. Ustawiamy również obramowanie i wyrównanie nagłówków.

### Krok 5.2: Dodaj rzędy korpusu

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Tutaj dynamicznie tworzymy 50 wierszy i 4 kolumny, wypełniając je tekstem i stylizując komórki. Kolor tła jest ustawiony na żółty, a tekst jest wyśrodkowany.

### Krok 5.3: Dodaj wiersz stopki

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Aby uzupełnić tabelę, dodajemy stopkę z wyśrodkowanym tekstem i`LightSeaGreen` tło.

## Krok 6: Sprawdź zgodność z PDF/UA

Po utworzeniu tabeli należy koniecznie upewnić się, że plik PDF jest zgodny ze standardem PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Sprawdź zgodność z PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Ten fragment kodu zapisuje plik PDF i sprawdza, czy spełnia on standardy zgodności PDF/UA. Jeśli dokument jest zgodny, jest dostępny dla użytkowników niepełnosprawnych.

## Wniosek

Gratulacje! Udało Ci się utworzyć w pełni dostosowaną tabelę w pliku PDF przy użyciu Aspose.PDF dla .NET. Od stylizacji tabeli po zapewnienie zgodności z PDF/UA, masz teraz solidne podstawy do generowania dynamicznych tabel w dokumentach PDF. Nie zapomnij zapoznać się z rozbudowanymi funkcjami Aspose.PDF, aby jeszcze bardziej ulepszyć swoje dokumenty!

## Najczęściej zadawane pytania

### Czy mogę dostosować czcionkę i styl tekstu tabeli?
Tak, Aspose.PDF pozwala na pełną personalizację czcionek, stylów tekstu i wyrównania za pomocą`TextState` klasa.

### Jak dynamicznie dodać więcej kolumn lub wierszy?
 Możesz dostosować liczbę kolumn lub wierszy, modyfikując`rowIndex` I`colIndex` w pętlach.

### Czy można scalić komórki w tabeli?
 Tak, możesz użyć`ColSpan` I`RowSpan` właściwości umożliwiające scalanie komórek w kolumnach lub wierszach.

### Na czym polega zgodność ze standardem PDF/UA?
Zgodność ze standardem PDF/UA gwarantuje, że dokument jest dostępny dla użytkowników niepełnosprawnych, zgodnie z międzynarodowymi standardami dostępności.

### Jak sprawdzić zgodność pliku Aspose.PDF z PDF/UA?
 Możesz użyć`Validate` metoda sprawdzająca zgodność dokumentu ze standardami PDF/UA.