---
title: Styl wiersza tabeli
linktitle: Styl wiersza tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak stylizować wiersze tabeli w pliku PDF za pomocą Aspose.PDF dla platformy .NET, korzystając z przewodnika krok po kroku, który pomoże Ci z łatwością ulepszyć formatowanie dokumentu.
type: docs
weight: 180
url: /pl/net/programming-with-tagged-pdf/style-table-row/
---
## Wstęp

Jeśli chodzi o tworzenie dobrze ustrukturyzowanych i pięknie sformatowanych dokumentów PDF, Aspose.PDF dla .NET jest rozwiązaniem, do którego należy się udać. Niezależnie od tego, czy automatyzujesz raporty, faktury, czy tworzysz dynamiczne tabele, formatowanie tabel za pomocą różnych stylów jest kluczem do uzyskania dopracowanego dokumentu. W tym samouczku zagłębimy się w stylizowanie wiersza tabeli za pomocą Aspose.PDF dla .NET. I nie martw się, poprowadzę Cię krok po kroku, tak jak dobrą rozmowę przy kawie!

## Wymagania wstępne

Zanim przejdziemy do konkretów, upewnijmy się, że masz wszystko pod kontrolą. Będziesz potrzebować:

1. Aspose.PDF dla biblioteki .NET  
    Jeśli jeszcze go nie masz, możesz go pobrać z[Tutaj](https://releases.aspose.com/pdf/net/) . Możesz również otrzymać[bezpłatny okres próbny](https://releases.aspose.com/) aby zacząć.
2. Środowisko programistyczne  
   Skonfiguruj Visual Studio lub dowolne wybrane przez siebie środowisko IDE C#. Będziesz również potrzebować zainstalowanego .NET, ale zakładam, że już jesteś z nim zaznajomiony.
3. Podstawowa wiedza z zakresu C# i .NET  
   Dobra znajomość języka C# sprawi, że ten samouczek będzie dziecinnie prosty. Ale nie martw się, wyjaśnię każdy krok szczegółowo!

## Importuj pakiety

Zanim zaczniemy pracę z Aspose.PDF, musimy zaimportować niezbędne przestrzenie nazw. W swoim projekcie C# upewnij się, że uwzględniłeś następujące elementy:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Są one niezbędne do utworzenia i nadania stylu tabeli, a także oczywiście do zapewnienia zgodności z przepisami pracy z oznaczoną treścią.

Teraz omówimy zadanie krok po kroku, dzięki czemu będziesz mógł stylizować wiersze tabeli jak profesjonalista!

## Krok 1: Utwórz nowy dokument PDF

Po pierwsze: utwórzmy zupełnie nowy dokument PDF. Ten dokument będzie zawierał wszystkie wiersze tabeli ze stylami.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
```

 Tutaj po prostu inicjujemy nowy`Document` obiekt, który będzie reprezentował nasz plik PDF. Upewnij się, że ustawiłeś ścieżkę katalogu, w którym będziesz zapisywać pliki wyjściowe.

## Krok 2: Praca z oznaczoną treścią

Aby ustrukturyzować plik PDF pod kątem dostępności, będziemy pracować z oznaczoną treścią. Pomaga to w tworzeniu ustrukturyzowanych elementów, takich jak tabele, zapewniając ich zgodność ze standardami dostępności, takimi jak PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Tutaj ustawiamy tytuł i język dla oznaczonej zawartości pliku PDF. To tak, jakbyśmy dali plikowi PDF nazwę i powiedzieli mu, w jakim języku powinien mówić!

## Krok 3: Zdefiniuj strukturę tabeli

Następnie zdefiniujmy strukturę tabeli, którą zamierzamy utworzyć. Każda tabela potrzebuje nagłówka, treści i stopki – zupełnie jak dobrze zorganizowany wpis na blogu!

```csharp
// Pobierz element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;

// Utwórz element struktury tabeli
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Tworzymy tutaj tabelę z nagłówkiem (`THead`), ciało (`TBody`) i stopka (`TFoot`). Te elementy będą trzymać nasze wiersze.

## Krok 4: Dodaj wiersz nagłówka tabeli

Tabele bez nagłówków są jak książki bez tytułów. Najpierw utwórzmy wiersz nagłówka, aby zapewnić kontekst dla danych.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Tutaj przechodzimy przez pętlę i dodajemy trzy komórki nagłówka (`TableTHElement`), nadając każdemu opisowy tekst. Proste, prawda?

## Krok 5: Dodaj rzędy stylizowanego korpusu

Teraz nadchodzi zabawna część – stylizowanie wierszy! Stwórzmy siedem wierszy z niestandardowymi stylami. Ustawimy kolory tła, obramowania, wypełnienie i wyrównanie tekstu.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Kolor tła: Użyliśmy jasnego, złocistożółtego odcienia, aby uzyskać profesjonalny, a jednocześnie ciepły efekt.
- Obramowanie: Każdy wiersz ma ciemnoszarą zewnętrzną obwódkę i niebieskie obramowanie komórek, co zapewnia ostry wygląd.
- Wysokość i wypełnienie: Wysokość wierszy jest ustawiona, a wypełnienie jest dodawane w celu uzyskania schludnego wyglądu.
- Podziały stron: Aby tabela była bardziej czytelna, co drugi wiersz zaczyna się na nowej stronie.

## Krok 6: Dodaj wiersz stopki

Podobnie jak nagłówek, stopka kotwiczy tabelę. Utwórzmy ją.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Po prostu przechodzimy przez trzy komórki stopki i dodajemy trochę tekstu. Alternatywny tekst dla stopki to „Foot Row”, aby uczynić ją dostępną.

## Krok 7: Zapisz dokument PDF

Teraz, gdy stół jest już gotowy, czas zapisać swoje dzieło!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

tak oto Twój plik PDF zostanie zapisany ze wszystkimi pięknymi wierszami tabeli, które przed chwilą wystylizowaliśmy.

## Krok 8: Sprawdź zgodność z PDF/UA

Aby mieć pewność, że nasz plik PDF jest zgodny ze standardami dostępności, zweryfikujemy go pod kątem zgodności z PDF/UA.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Dzięki temu Twój plik PDF spełnia standard PDF/UA, dzięki czemu jest dostępny dla każdego. Dostępność to nazwa gry!

## Wniosek

I masz to! Za pomocą zaledwie kilku linijek kodu utworzyłeś w pełni wystylizowaną tabelę w pliku PDF przy użyciu Aspose.PDF dla .NET. Od nagłówków do stopek, wystylizowaliśmy każdy wiersz, dodaliśmy elementy ułatwień dostępu, a nawet sprawdziliśmy zgodność dokumentu. Niezależnie od tego, czy pracujesz nad raportami korporacyjnymi, prezentacjami, czy po prostu bawisz się plikami PDF, ten przewodnik obejmuje wszystko. Teraz idź dalej i zacznij stylizować swoje tabele jak profesjonalista!

## Najczęściej zadawane pytania

### Czy mogę również zmienić styl czcionki tabeli?  
 Tak! Możesz modyfikować styl czcionki za pomocą`TextState` obiekt dla każdej komórki, co pozwala na pełną personalizację.

### Jak dodać więcej kolumn do tabeli?  
 Wystarczy dostosować`colCount`zmienną i dodaj więcej komórek w pętlach dla nagłówków, treści i stopek.

### Co się stanie, jeśli nie ustawię wysokości wiersza?  
Jeśli nie ustawisz wysokości wiersza, tabela automatycznie dostosuje się do jej zawartości.

### Czy mogę użyć tego do dynamicznej liczby wierszy?  
Oczywiście! Możesz pobrać dane z bazy danych lub dowolnego innego źródła i dynamicznie dostosować liczbę wierszy i kolumn.

### Czy korzystanie z Aspose.PDF dla platformy .NET jest bezpłatne?  
 Aspose.PDF dla .NET jest produktem licencjonowanym, ale możesz go wypróbować za pomocą[bezpłatny okres próbny](https://releases.aspose.com/) lub zdobądź[licencja tymczasowa](https://purchase.aspose.com/temporary-license/).