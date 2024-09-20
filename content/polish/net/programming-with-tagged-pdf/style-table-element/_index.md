---
title: Element tabeli stylów
linktitle: Element tabeli stylów
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak utworzyć i stylizować element tabeli w programie Aspose.PDF dla platformy .NET, korzystając z instrukcji krok po kroku, niestandardowego stylu i zgodności ze standardem PDF/UA.
type: docs
weight: 170
url: /pl/net/programming-with-tagged-pdf/style-table-element/
---
## Wstęp

W tym artykule zagłębimy się w sposób tworzenia i stylizowania elementu tabeli przy użyciu Aspose.PDF dla .NET. Dowiesz się, jak strukturować tabelę, stosować niestandardowe style i sprawdzać zgodność dokumentu z PDF/UA. Pod koniec tego samouczka będziesz w stanie z łatwością tworzyć profesjonalnie wyglądające tabele w swoich plikach PDF!

## Wymagania wstępne

Zanim rozpoczniesz samouczek, upewnij się, że posiadasz następujące elementy:

1. Na Twoim komputerze zainstalowany jest program Visual Studio lub podobne środowisko IDE.
2. .NET Framework lub .NET Core SDK do uruchomienia aplikacji.
3.  Aspose.PDF dla biblioteki .NET pobrany i przywoływany w Twoim projekcie. Możesz pobrać najnowszą wersję z[Tutaj](https://releases.aspose.com/pdf/net/).
4.  Ważna licencja Aspose lub[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby odblokować pełną funkcjonalność biblioteki.

## Importuj pakiety

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Te przestrzenie nazw obejmują podstawowe operacje PDF, tagowaną zawartość, tabele i formatowanie tekstu.

Teraz omówmy proces tworzenia i stylizowania tabeli w Aspose.PDF. Przejdziemy przez każdą sekcję szczegółowo, abyś mógł śledzić.

## Krok 1: Utwórz nowy dokument PDF i skonfiguruj oznaczoną zawartość

W pierwszym kroku utworzymy pusty dokument PDF i skonfigurujemy jego oznaczoną zawartość.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument PDF
Document document = new Document();

// Konfiguracja oznaczonej zawartości
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Zaczynamy od stworzenia nowego`Document` obiekt, reprezentujący nasz PDF.`TaggedContent`obiekt służy do zarządzania strukturą dokumentu, zapewniając zgodność ze standardami dostępności. Ustawiamy tytuł i język dokumentu w celu prawidłowego tagowania.

## Krok 2: Zdefiniuj element główny

Następnie utworzymy element struktury głównej, który będzie pełnił funkcję kontenera dla całej zawartości naszego pliku PDF.

```csharp
// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;
```

 Ten`RootElement` służy jako podstawowy kontener dla wszystkich ustrukturyzowanych elementów, w tym naszej tabeli. Pomaga utrzymać hierarchię strukturalną dokumentu, co jest ważne zarówno dla organizacji, jak i dostępności.

## Krok 3: Utwórz i nadaj styl elementowi tabeli

 Teraz, gdy element główny jest już skonfigurowany, utworzymy`TableElement` i zastosuj style, takie jak kolor tła, obramowanie i wyrównanie.

```csharp
// Utwórz element struktury tabeli
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Stylizuj tabelę
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Tworzymy`TableElement` , która definiuje strukturę naszej tabeli.`BackgroundColor`, `Border` , I`Alignment` Właściwości pozwalają nam dostosować wygląd tabeli.`Broken` Właściwość ta zapewnia, że jeśli tabela zostanie podzielona między strony, nastąpi podział pionowy.

## Krok 4: Ustaw wymiary tabeli i style komórek

W tym kroku zdefiniujemy liczbę kolumn, wypełnienie komórek i inne ważne właściwości tabeli.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Określamy szerokości kolumn, aby zapewnić równomierne rozmieszczenie każdej kolumny w tabeli.`DefaultCellBorder`, `DefaultCellPadding` , I`DefaultCellTextState` zdefiniuj domyślne style komórek, obejmujące obramowanie, wypełnienie, kolor tekstu i rozmiar czcionki.

## Krok 5: Dodaj powtarzające się wiersze i style niestandardowe

Możemy również definiować style dla powtarzających się wierszy i innych określonych elementów tabeli, takich jak nagłówki i stopki.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 Ten`RepeatingRowsCount` zapewnia, że pierwsze trzy wiersze powtarzają się, jeśli tabela obejmuje wiele stron. Ustawiamy`RepeatingRowsStyle` aby zastosować niestandardowy kolor tła do tych wierszy.

## Krok 6: Dodaj elementy nagłówka, korpusu i stopy tabeli

Teraz utwórzmy sekcje nagłówka, treści i stopki tabeli i wypełnijmy je treścią.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Utwórz wiersz nagłówka
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Wypełnij treść tabeli
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Tabela jest podzielona na trzy części: głowa, ciało i stopa. Najpierw tworzymy wiersz nagłówka za pomocą`TableTHElement` dodajemy nagłówki kolumn. Następnie wypełniamy treść tabeli`TableTDElement`, wypełniając każdą komórkę etykietą zawierającą jej pozycję.

## Krok 7: Zapisz dokument

Na koniec zapisujemy dokument PDF w podanym katalogu.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");
```

Ten krok kończy proces tworzenia dokumentu poprzez zapisanie pliku PDF ze stylizowaną tabelą.

## Krok 8: Sprawdź zgodność z PDF/UA

Po zapisaniu dokumentu należy upewnić się, że jest on zgodny ze standardami PDF/UA (Uniwersalna Dostępność).

```csharp
// Sprawdź zgodność PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Tutaj ponownie ładujemy dokument i weryfikujemy go pod kątem standardów PDF/UA. Zgodność zapewnia, że Twój plik PDF spełnia wymagania dotyczące dostępności, dzięki czemu jest odpowiedni dla szerokiego grona użytkowników.

## Wniosek

Dzięki Aspose.PDF dla .NET tworzenie i stylizowanie tabel w dokumentach PDF jest proste i intuicyjne. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz tworzyć tabele ze stylami dostosowanymi do potrzeb i upewnić się, że Twoje pliki PDF spełniają standardy dostępności. Niezależnie od tego, czy generujesz raporty, czy tworzysz ustrukturyzowane dokumenty, tabele są potężnym narzędziem do przejrzystej prezentacji danych.

## Najczęściej zadawane pytania

### Czy mogę dodawać obrazy do komórek tabeli?
 Tak, możesz wstawiać obrazy do komórek tabeli za pomocą`Image` element.

### Jak dynamicznie dostosować szerokość kolumn?
 Możesz ustawić`ColumnAdjustment` nieruchomość do`AutoFitToWindow` aby automatycznie dostosowywać szerokość kolumn na podstawie zawartości.

### Czy zgodność ze standardem PDF/UA jest obowiązkowa dla wszystkich dokumentów?
Choć nie jest to obowiązkowe, zaleca się to w przypadku dokumentów wymagających wysokich standardów dostępności.

### Czy mogę zastosować różne style do konkretnych wierszy?
 Tak, możesz dostosować poszczególne wiersze lub komórki, dostosowując ich`TextState` Lub`BackgroundColor`.

### Jakie są korzyści ze stosowania treści oznaczonych tagami?
Oznaczona treść poprawia dostępność dokumentu i pomaga zapewnić zgodność ze standardami takimi jak PDF/UA.