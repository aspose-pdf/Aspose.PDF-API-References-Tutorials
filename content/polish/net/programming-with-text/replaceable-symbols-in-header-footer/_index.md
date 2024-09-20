---
title: Wymienne symbole w nagłówku i stopce
linktitle: Wymienne symbole w nagłówku i stopce
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać wymiennych symboli w nagłówku i stopce dokumentu PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 320
url: /pl/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Wstęp

Podczas pracy z plikami PDF zdarzają się sytuacje, gdy trzeba dostosować nagłówki i stopki za pomocą dynamicznej zawartości, takiej jak numery stron, nazwy raportów lub wygenerowane daty. Na szczęście Aspose.PDF dla .NET upraszcza ten proces, umożliwiając tworzenie plików PDF z automatycznie aktualizowanymi symbolami w nagłówkach i stopkach, takimi jak numery stron lub szczegóły generowania raportów. Ten artykuł przeprowadzi Cię przez proces krok po kroku zastępowania symboli w nagłówkach i stopkach za pomocą Aspose.PDF dla .NET, w sposób, który jest nie tylko prosty, ale także niesamowicie wydajny.

## Wymagania wstępne

Zanim przejdziesz do instrukcji krok po kroku, upewnij się, że masz następujące rzeczy:

-  Aspose.PDF dla biblioteki .NET –[Pobierać](https://releases.aspose.com/pdf/net/) lub zdobądź[bezpłatny okres próbny](https://releases.aspose.com/).
- Visual Studio lub dowolne środowisko IDE C# zainstalowane w systemie.
- Podstawowa znajomość programowania w języku C# i .NET.
-  Ważny[licencja](https://purchase.aspose.com/temporary-license/) dla Aspose.PDF lub możesz skorzystać z wersji próbnej.

## Importuj pakiety

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw, które umożliwią funkcjonalność Aspose.PDF dla .NET. Poniżej przedstawiono niezbędny import:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Są one niezbędne do obsługi tworzenia plików PDF, edycji tekstu oraz zarządzania nagłówkami i stopkami.

Podzielmy przykładowy kod na łatwe do zrozumienia kroki.

## Krok 1: Skonfiguruj dokument i stronę

Najpierw musimy zainicjować dokument i dodać do niego stronę. To stanowi podstawę do dodawania nagłówków i stopek.

```csharp
// Skonfiguruj katalog dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Zainicjuj obiekt dokumentu
Document doc = new Document();

// Dodaj stronę do dokumentu
Page page = doc.Pages.Add();
```

 Tutaj konfigurujemy dokument PDF za pomocą`Document` klasa i dodanie strony z`doc.Pages.Add()`Ta strona będzie zawierać nagłówek, stopkę i inną treść.

## Krok 2: Skonfiguruj marginesy strony

Następnie zdefiniujemy marginesy strony, aby mieć pewność, że treść nie będzie sięgać samej krawędzi.

```csharp
// Konfigurowanie marginesów
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Tutaj zdefiniowaliśmy górny, dolny, lewy i prawy margines za pomocą`MarginInfo` klasę i zastosowałem ją do strony za pomocą`page.PageInfo.Margin`.

## Krok 3: Utwórz i skonfiguruj nagłówek

Teraz utwórzmy nagłówek i dodajmy go do strony. Nagłówek będzie zawierał tytuł i nazwę raportu.

```csharp
// Utwórz nagłówek
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Ustaw marginesy nagłówka
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Dodaj tytuł do nagłówka
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Dodaj nazwę raportu do nagłówka
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 Dodaliśmy dwa`TextFragment` obiekty do nagłówka: jeden dla tytułu raportu i drugi dla nazwy raportu. Tekst jest stylizowany za pomocą`TextState` właściwości takie jak czcionka, rozmiar i wyrównanie.

## Krok 4: Utwórz i skonfiguruj stopkę

Teraz czas na skonfigurowanie stopki, która będzie zawierać dynamiczną zawartość, taką jak numery stron i datę wygenerowania.

```csharp
// Utwórz stopkę
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Ustaw marginesy stopki
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Dodaj treść stopki
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

stopce uwzględniamy fragmenty dotyczące daty wygenerowania, nazwy raportu i dynamicznych numerów stron (`$p` I`$P` reprezentują odpowiednio bieżący numer strony i całkowitą liczbę stron).

## Krok 5: Utwórz tabelę w stopce

Możesz również dodać bardziej złożone elementy, takie jak tabele w stopce, aby lepiej zorganizować dane.

```csharp
// Utwórz tabelę dla stopki
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Utwórz wiersze i komórki dla tabeli
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Ustaw wyrównanie dla każdej komórki
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Dodaj zawartość do komórek tabeli
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Ten blok kodu tworzy w stopce tabelę złożoną z 3 kolumn, w której każda kolumna zawiera inne informacje, takie jak data wygenerowania, nazwa raportu i numery stron.

## Krok 6: Dodaj treść do strony

Oprócz nagłówków i stopek możesz dodać treść do treści strony PDF. Tutaj dodajemy tabelę z tekstem zastępczym.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Dodaj zawartość tabeli
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Ten kod dodaje prostą tabelę z trzema kolumnami do strony. Możesz ją zmodyfikować, aby dostosować ją do swoich konkretnych potrzeb.

## Krok 7: Zapisz plik PDF

Gdy wszystko jest już skonfigurowane, ostatnim krokiem jest zapisanie dokumentu PDF w wybranej lokalizacji.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Określ ścieżkę pliku i zapisz dokument za pomocą`doc.Save()`. To wszystko! Udało Ci się utworzyć plik PDF z niestandardowymi nagłówkami i stopkami.

## Wniosek

Zastępowanie symboli w nagłówkach i stopkach za pomocą Aspose.PDF dla .NET jest nie tylko proste, ale i skuteczne. Postępując zgodnie z powyższym przewodnikiem krok po kroku, możesz łatwo dostosować pliki PDF za pomocą dynamicznej zawartości, takiej jak numery stron, nazwy raportów i daty. Ta metoda jest bardzo elastyczna, umożliwiając wstawianie tabel, dostosowywanie formatowania i kontrolowanie układu w celu dopasowania do konkretnych wymagań.

## Najczęściej zadawane pytania

### Czy mogę dostosować czcionki nagłówków i stopek?  
Tak, możesz w pełni dostosowywać czcionki, rozmiary, kolory i style tekstu w nagłówkach i stopkach.

### Jak dodawać obrazy do nagłówków i stopek?  
 Możesz użyć`ImageStamp` aby wstawiać obrazy do nagłówków i stopek.

### Czy można dodawać hiperłącza w nagłówkach lub stopkach?  
 Tak, możesz użyć`TextFragment` z hiperłączem poprzez ustawienie`Hyperlink` nieruchomość.

### Czy mogę używać różnych nagłówków dla stron nieparzystych i parzystych?  
Tak, Aspose.PDF pozwala na określenie różnych nagłówków i stopek dla stron nieparzystych i parzystych.

### Jak zmienić położenie nagłówka i stopki?  
Możesz dostosować marginesy i właściwości wyrównania, aby kontrolować położenie nagłówków i stopek.