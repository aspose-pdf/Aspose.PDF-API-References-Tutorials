---
title: Styl komórki tabeli
linktitle: Styl komórki tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak stylizować komórki tabeli w pliku PDF za pomocą Aspose.PDF dla .NET dzięki temu szczegółowemu samouczkowi. Postępuj zgodnie z instrukcjami, aby tworzyć i formatować piękne tabele PDF.
type: docs
weight: 160
url: /pl/net/programming-with-tagged-pdf/style-table-cell/
---
## Wstęp

Tworzenie profesjonalnie wyglądających tabel PDF może być trudne, ale dzięki Aspose.PDF dla .NET jest to zaskakująco proste! Niezależnie od tego, czy stylizujesz nagłówki, stopki czy konkretne komórki tabeli, ta potężna biblioteka zapewnia wszystkie narzędzia potrzebne do tworzenia pięknie sformatowanych dokumentów PDF. W tym samouczku pokażemy, jak stylizować komórki tabeli w dokumencie PDF za pomocą Aspose.PDF dla .NET. Nie martw się — podzielimy wszystko na łatwe do wykonania kroki.

## Wymagania wstępne

Zanim zaczniesz pisać kod, upewnij się, że spełniasz następujące wymagania wstępne:

1. Aspose.PDF dla .NET: Pobierz i zainstaluj najnowszą wersję Aspose.PDF ze strony[Tutaj](https://releases.aspose.com/pdf/net/).
2. IDE (np. Visual Studio): skonfiguruj środowisko programistyczne .NET.
3. Podstawowa znajomość programowania w języku C#: Wymagana jest pewna znajomość języka C#.
4.  Licencja Aspose.PDF: Uzyskaj tymczasową lub pełną licencję, aby odblokować pełne funkcje biblioteki. Możesz otrzymać bezpłatną wersję próbną[Tutaj](https://purchase.aspose.com/temporary-license/).

## Importuj pakiety

Przed rozpoczęciem upewnij się, że zaimportowałeś niezbędne przestrzenie nazw. Będziesz potrzebować następujących elementów w swoim projekcie:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Teraz, gdy wszystko jest już skonfigurowane, możemy przejść do przewodnika krok po kroku!

Stworzymy tabelę w dokumencie PDF i nadamy jej styl komórkom. Każdy krok będzie szczegółowo wyjaśniał proces.

## Krok 1: Utwórz nowy dokument PDF

 Pierwszym krokiem jest utworzenie nowego dokumentu PDF. W Aspose.PDF możesz zainicjować nowy`Document` obiekt, który reprezentuje Twój plik PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Tutaj inicjujemy dokument PDF i ustawiamy jego tytuł i język. To nadaje dokumentowi odpowiednią strukturę, która jest niezbędna do zgodności z PDF/UA.

## Krok 2: Skonfiguruj strukturę tabeli

Tabele w plikach PDF są definiowane w elementach struktury. Utwórzmy tabelę i zdefiniujmy wiersze i kolumny tabeli.

```csharp
// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;

// Utwórz element struktury tabeli
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Zdefiniowaliśmy teraz nagłówek tabeli (`TableTHeadElement`), ciało (`TableTBodyElement`), i stopa (`TableTFootElement`) sekcje. Możesz myśleć o nich jako o szkielecie swojej tabeli.

## Krok 3: Stylizuj komórki nagłówka

Stylizowanie komórek nagłówka sprawia, że się wyróżniają. Tutaj stosujemy kolory tła, obramowania i wyrównanie tekstu.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

W tym kroku przechodzimy przez każdą komórkę nagłówka, nadając jej zielono-żółte tło, szarą ramkę i tekst wyrównany do prawej. Możesz dostosować te właściwości, aby dopasować je do pożądanego projektu.

## Krok 4: Wypełnij i sformatuj treść tabeli

Treść tabeli zawiera rzeczywiste dane. Oto, jak możesz stylizować każdą komórkę za pomocą określonych marginesów, obramowań i ustawień tekstu.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 W tym kroku wypełniamy ciało tabeli czterema wierszami i stylizujemy każdą komórkę żółtym tłem i wyśrodkowanym, pogrubionym niebieskim tekstem. Używamy również`MarginInfo`Klasa definiująca wypełnienie wokół tekstu.

## Krok 5: Styl stopki

Aby nadać tabeli kompletną strukturę, dodajemy i stylizujemy komórki stopki, tak jak zrobiliśmy to w przypadku nagłówka.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

Sekcja stopki ma podobny styl do nagłówka, co ułatwia czytelnikom śledzenie struktury tabeli.

## Krok 6: Zapisz i zatwierdź dokument PDF

Na koniec zapisujemy dokument PDF i sprawdzamy czy jest zgodny ze standardem PDF/UA.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");

// Sprawdzanie zgodności PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Zapisujemy plik PDF i używamy`Validate` metoda ta zapewnia spełnienie standardów dostępności (zgodność z PDF/UA).

## Wniosek

Stylizowanie tabel w pliku PDF przy użyciu Aspose.PDF dla .NET jest zarówno wydajne, jak i elastyczne. Za pomocą kilku linijek kodu możesz tworzyć niestandardowe projekty tabel, które wyróżnią Twoje dokumenty PDF. Od dostosowywania obramowań i tła komórek po zapewnienie zgodności z dostępnością, Aspose.PDF ułatwia tworzenie dopracowanych plików PDF.

## Najczęściej zadawane pytania

### Czy mogę stosować różne style do poszczególnych komórek tabeli?  
Tak, możesz stylizować poszczególne komórki, dostosowując`TableTDElement` Właściwości.

### Jak mogę scalić komórki tabeli?  
 Możesz użyć`ColSpan` I`RowSpan` Właściwości umożliwiające scalenie komórek w tabeli.

### Czy można utworzyć tabelę zgodną ze standardem PDF/UA?  
 Tak, jak pokazano w tym przewodniku, możesz zapewnić zgodność PDF/UA, weryfikując dokument za pomocą`Validate` metoda.

### Czy mogę używać różnych czcionek w komórkach tabeli?  
 Oczywiście! Możesz określić różne czcionki za pomocą`TextState` obiekt dla każdej komórki.

### Jak pobrać plik Aspose.PDF dla platformy .NET?  
 Można go pobrać ze strony[strona wydań](https://releases.aspose.com/pdf/net/).