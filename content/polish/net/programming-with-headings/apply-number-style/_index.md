---
title: Zastosuj styl numeracji w pliku PDF
linktitle: Zastosuj styl numeracji w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak stosować różne style numeracji (cyfry rzymskie, alfabetyczne) w nagłówkach w pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-headings/apply-number-style/
---
## Wstęp

Czy kiedykolwiek zdarzyło Ci się dodać pięknie ponumerowane listy do dokumentów PDF? Niezależnie od tego, czy formatujesz dokumenty prawne, raporty czy prezentacje, właściwe style numeracji są niezbędne do uporządkowania informacji. Dzięki Aspose.PDF dla .NET możesz stosować różne style numeracji do nagłówków plików PDF, tworząc dobrze ustrukturyzowane i profesjonalne dokumenty. 

## Wymagania wstępne

Zanim zagłębisz się w kodowanie, omówmy, czego będziesz potrzebować:

1. Aspose.PDF dla .NET: Pobierz najnowszą wersję Aspose.PDF ze strony[Tutaj](https://releases.aspose.com/pdf/net/).
2. Środowisko programistyczne: Upewnij się, że masz program Visual Studio lub inne środowisko programistyczne zgodne z platformą .NET.
3. .NET Framework: Upewnij się, że masz zainstalowany .NET Framework 4.0 lub nowszy.
4.  Licencja: Możesz użyć tymczasowej licencji z[Tutaj](https://purchase.aspose.com/temporary-license/) lub odkryj[bezpłatny okres próbny](https://releases.aspose.com/) opcje.

## Importuj pakiety

Aby rozpocząć, upewnij się, że w projekcie zaimportowano następujące przestrzenie nazw:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 1: Konfigurowanie dokumentu

Zacznijmy od utworzenia nowego dokumentu PDF i skonfigurowania jego ustawień strony. Ustawimy rozmiar strony i marginesy, aby kontrolować układ naszej treści.

Wyjaśnienie: W tym kroku skonfigurujemy podstawową strukturę pliku PDF, która obejmuje zdefiniowanie rozmiaru strony, wysokości i marginesów w celu zachowania spójnego formatowania.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Ustaw wymiary i marginesy strony
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Dzięki temu dokument będzie miał standardowy rozmiar strony, odpowiadający stronie 8,5 x 11 cali, i marginesy wynoszące 72 punkty (lub 1 cal) z każdej strony.

## Krok 2: Dodawanie strony do pliku PDF

Następnie dodamy nową stronę do dokumentu PDF, na której później zastosujemy style numeracji.

Wyjaśnienie: Każdy plik PDF wymaga stron! Ten krok dodaje pustą stronę do pliku PDF i ustawia jej marginesy tak, aby odpowiadały ustawieniom na poziomie dokumentu.

```csharp
// Dodaj nową stronę do dokumentu PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Krok 3: Utwórz pływające pole

FloatingBox pozwala na umieszczenie zawartości (takiej jak tekst lub nagłówki) wewnątrz pola, które zachowuje się niezależnie od przepływu strony. Jest to przydatne, gdy chcesz mieć pełną kontrolę nad układem swojej zawartości.

Wyjaśnienie: Tutaj konfigurujemy obiekt FloatingBox, który będzie zawierał nagłówki, do których zostaną zastosowane style liczbowe.

```csharp
// Utwórz FloatingBox dla treści strukturalnej
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Krok 4: Dodaj pierwszy nagłówek z cyframi rzymskimi

Teraz nadchodzi ekscytująca część! Dodajmy pierwszy nagłówek z numeracją cyfr rzymskich małymi literami.

Wyjaśnienie: Stosujemy styl NumberingStyle.NumeralsRomanLowercase do nagłówka, który będzie wyświetlał numerację w postaci cyfr rzymskich (i, ii, iii itd.).

```csharp
// Utwórz pierwszy nagłówek za pomocą cyfr rzymskich
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Krok 5: Dodaj drugi nagłówek składający się z cyfr rzymskich

W celach demonstracyjnych dodajmy drugi nagłówek składający się z cyfr rzymskich, ale tym razem zacznijmy od 13.

Wyjaśnienie: Właściwość StartNumber umożliwia rozpoczęcie numerowania od niestandardowego numeru — w tym przypadku zaczynamy od 13.

```csharp
// Utwórz drugi nagłówek zaczynający się od cyfry rzymskiej 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Krok 6: Dodaj nagłówek z numeracją alfabetyczną

Dla urozmaicenia dodajmy trzeci nagłówek, ale tym razem użyjemy numeracji alfabetycznej małymi literami (a, b, c, itd.).

Wyjaśnienie: Zmiana NumberingStyle na LettersLowercase umożliwia zastosowanie numeracji alfabetycznej do naszych nagłówków.

```csharp
// Utwórz nagłówek z numeracją alfabetyczną
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Krok 7: Zapisywanie pliku PDF

Na koniec, po zastosowaniu wszystkich nagłówków i stylów numeracji, zapiszmy plik PDF w wybranym katalogu.

Wyjaśnienie: Ten krok powoduje zapisanie pliku PDF zawierającego wszystkie sformatowane nagłówki z zastosowanymi stylami numeracji.

```csharp
// Zapisz dokument PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Wniosek

I masz to! Udało Ci się zastosować style numeracji — cyfry rzymskie i alfabetyczne — do nagłówków w pliku PDF przy użyciu Aspose.PDF dla .NET. Elastyczność zapewniana przez Aspose.PDF do kontrolowania układu strony, stylów numeracji i pozycjonowania treści daje Ci potężny zestaw narzędzi do tworzenia dobrze zorganizowanych, profesjonalnych dokumentów PDF.

## Najczęściej zadawane pytania

### Czy mogę zastosować różne style numeracji w tym samym dokumencie PDF?  
Tak, Aspose.PDF dla platformy .NET pozwala na łączenie różnych stylów numeracji, takich jak cyfry rzymskie, cyfry arabskie i numeracja alfabetyczna w obrębie tego samego dokumentu.

### Jak mogę dostosować numer początkowy nagłówków?  
 Możesz ustawić numer początkowy dla dowolnego nagłówka za pomocą`StartNumber` nieruchomość.

### Czy istnieje sposób na zresetowanie kolejności numeracji?  
Tak, możesz zresetować numerację, dostosowując`StartNumber` właściwość dla każdego nagłówka.

### Czy oprócz numerowania mogę zastosować pogrubienie lub kursywę w nagłówkach?  
 Oczywiście! Możesz dostosować style nagłówków, modyfikując właściwości, takie jak czcionka, rozmiar, pogrubienie i kursywa, używając`TextState` obiekt.

### Jak uzyskać tymczasową licencję na Aspose.PDF?  
 Możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/) aby przetestować Aspose.PDF bez ograniczeń.