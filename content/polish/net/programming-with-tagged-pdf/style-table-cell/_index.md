---
title: Komórka tabeli stylu
linktitle: Komórka tabeli stylu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak stylizować komórki tabeli za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący tworzenia i dostosowywania tabel.
type: docs
weight: 160
url: /pl/net/programming-with-tagged-pdf/style-table-cell/
---
Witamy w tym szczegółowym samouczku na temat formatowania komórek tabeli przy użyciu Aspose.PDF dla .NET. W tym przewodniku szczegółowo wyjaśnimy każdy krok dostarczonego kodu źródłowego C#, aby pomóc Ci zrozumieć, jak stylizować komórki tabeli. Zanim zaczniesz, upewnij się, że zainstalowałeś Aspose.PDF dla .NET i skonfiguruj środowisko programistyczne.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do korzystania z Aspose.PDF dla .NET. Obejmuje to instalację biblioteki Aspose.PDF i skonfigurowanie projektu tak, aby się do niej odwoływał.

## Krok 2: Tworzenie dokumentu

W tym kroku utworzymy nowy obiekt dokumentu Aspose.PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Stworzyliśmy nowy dokument oraz ustawiliśmy tytuł i język dokumentu.

## Krok 3: Uzyskanie elementu struktury korzenia

W tym kroku otrzymamy element struktury głównej naszego dokumentu.

```csharp
//Zdobądź element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy element struktury głównej, który będzie służył jako kontener dla elementów tablicy.

## Krok 4: Tworzenie elementu struktury tablicowej

Stwórzmy teraz nowy element struktury tabeli dla naszego dokumentu.

```csharp
// Utwórz element struktury tablicowej
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Stworzyliśmy nowy element struktury tablicowej i dodaliśmy go do elementu struktury głównej. Stworzyliśmy także elementy nagłówka, treści i stopki tabeli.

## Krok 5: Dodawanie nagłówków tabeli

W tym kroku dodamy nagłówki tabeli do naszej tabeli.

```csharp
// Liczba wierszy i kolumn w tabeli
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Utwórz wiersz nagłówka tabeli
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Stworzyliśmy wiersz nagłówka dla naszej tabeli i dodaliśmy komórki nagłówka z właściwościami formatowania, takimi jak kolor tła, obramowania, marginesy i wyrównanie.

## Krok 6: Dodawanie wierszy treści tabeli

Teraz dodajmy wiersze treści tabeli do naszej tabeli.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Dodaliśmy wiersze do treści tabeli, używając pętli do iteracji po każdej komórce tabeli. Dla każdej komórki ustawiamy właściwości formatowania, takie jak kolor tła, obramowania, marginesy, wyrównanie tekstu itp.

## Krok 7: Dodanie stopki

Na koniec dodamy do naszej tabeli stopkę tabeli.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Stworzyliśmy stopkę dla naszej tabeli i dodaliśmy komórki stopki z tekstem.



## Krok 8: Zapisywanie oznaczonego dokumentu PDF

Teraz, gdy utworzyliśmy dokument ze stylizowaną tabelą, zapiszemy go jako oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");
```

Zapisaliśmy oznaczony dokument PDF w określonym katalogu.

## Krok 9: Sprawdzanie zgodności z PDF/UA

Następnie sprawdzimy zgodność naszego dokumentu z PDF/UA.

```csharp
// Kontrola zgodności z PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Przesłaliśmy oznaczony tagiem dokument PDF i sprawdziliśmy jego zgodność z PDF/UA, generując raport XML.

### Przykładowy kod źródłowy komórki tabeli stylów przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Uzyskaj element struktury głównej
StructureElement rootElement = taggedContent.RootElement;

// Utwórz element struktury tabeli
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");

// Sprawdzanie zgodności z PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

tym samouczku nauczyliśmy się stylizować komórki tabeli za pomocą Aspose.PDF dla .NET. Widzieliśmy, jak utworzyć dokument, dodać tabelę z nagłówkami, wierszami treści i stopką oraz dostosować style komórek. Na koniec zapisaliśmy oznaczony tagiem dokument PDF i sprawdziliśmy jego zgodność z PDF/UA. Możesz teraz używać Aspose.PDF dla .NET do tworzenia i stylizowania tabel w aplikacjach .NET.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka dotyczącego formatowania komórek tabeli przy użyciu Aspose.PDF dla .NET?

Odp.: Ten samouczek ma na celu zapewnienie kompleksowego przewodnika na temat stylizowania komórek tabeli w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Zawiera instrukcje krok po kroku i przykłady kodu źródłowego C#, które pomogą Ci zrozumieć i wdrożyć formatowanie komórek tabeli.

#### P: Jakie są wymagania wstępne dotyczące korzystania z tego samouczka?

O: Zanim zaczniesz, upewnij się, że zainstalowałeś Aspose.PDF dla .NET i skonfigurowałeś środowisko programistyczne. Obejmuje to skonfigurowanie projektu tak, aby odwoływał się do biblioteki Aspose.PDF.

#### P: Jak utworzyć nowy dokument PDF przy użyciu Aspose.PDF dla .NET?

O: Aby utworzyć nowy dokument PDF, musisz utworzyć instancję pliku`Document` obiekt z biblioteki Aspose.PDF. Dostarczony kod źródłowy języka C# demonstruje, jak utworzyć dokument oraz ustawić jego tytuł i język.

#### P: Jakie jest znaczenie elementu struktury głównej w dokumencie PDF?

Odp.: Główny element struktury służy jako pojemnik na inne elementy struktury, pomagając organizować i kategoryzować zawartość dokumentu PDF. Odgrywa kluczową rolę w ustaleniu logicznej struktury dokumentu.

#### P: Jak mogę utworzyć element struktury tabeli i dostosować jego wygląd za pomocą Aspose.PDF dla .NET?

 Odp.: Możesz utworzyć element struktury tabeli za pomocą`CreateTableElement()` metoda. Dostarczony kod źródłowy pokazuje, jak dostosować wygląd tabeli, w tym jej nagłówek, treść i stopkę, poprzez ustawienie właściwości, takich jak kolor tła, obramowania, marginesy i wyrównanie.

#### P: Czy mogę dodać wiele wierszy i kolumn do treści tabeli i dostosować ich formatowanie?

O: Tak, w samouczku pokazano, jak dodać wiele wierszy i kolumn do treści tabeli za pomocą pętli. Zawiera także przykłady dostosowywania formatowania komórek, np. koloru tła, obramowań, wyrównania tekstu, stylu czcionki i innych.

#### P: Jaki jest cel sprawdzania zgodności z PDF/UA i jak mogę przeprowadzić tę weryfikację?

 O: Sprawdzenie zgodności z PDF/UA gwarantuje, że dokument PDF jest zgodny ze standardami dostępności, dzięki czemu jest bardziej dostępny dla użytkowników niepełnosprawnych. Samouczek pokazuje, jak sprawdzić zgodność z PDF/UA za pomocą pliku`Validate()` metodę i wygenerować raport XML.

#### P: Jak mogę zastosować te koncepcje do moich własnych aplikacji .NET?

Odp.: Możesz użyć podanych przykładów kodu źródłowego C# jako przewodnika po implementowaniu formatowania komórek tabeli we własnych aplikacjach .NET. Dostosuj kod zgodnie z potrzebami i zintegruj go ze swoimi projektami.

#### P: Czy są jakieś zalecane najlepsze praktyki dotyczące stylizacji komórek tabeli w dokumentach PDF?

O: Stylizując komórki tabeli, weź pod uwagę potrzeby odbiorców, w tym wymagania dotyczące dostępności. Aby zwiększyć czytelność, użyj kontrastujących kolorów, odpowiednich czcionek i wyraźnego wyrównania komórek. Dodatkowo sprawdź zgodność z PDF/UA, aby upewnić się, że spełnione są standardy dostępności.

#### P: Jakie inne funkcje Aspose.PDF dla .NET mogę wykorzystać do manipulacji dokumentami PDF?

Odp.: Aspose.PDF dla .NET oferuje szeroką gamę funkcji do manipulacji dokumentami PDF, w tym wyodrębnianie tekstu, wstawianie obrazów, zarządzanie polami formularzy, podpisy cyfrowe i inne. Zapoznaj się z oficjalną dokumentacją i zasobami, aby poznać dodatkowe funkcje.
