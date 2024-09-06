---
title: Styl komórki tabeli
linktitle: Styl komórki tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak stylizować komórki tabeli za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący tworzenia i dostosowywania tabel.
type: docs
weight: 160
url: /pl/net/programming-with-tagged-pdf/style-table-cell/
---
Witamy w tym szczegółowym samouczku dotyczącym formatowania komórek tabeli za pomocą Aspose.PDF dla .NET. W tym przewodniku szczegółowo wyjaśnimy każdy krok dostarczonego kodu źródłowego C#, aby pomóc Ci zrozumieć, jak stylizować komórki tabeli. Upewnij się, że zainstalowałeś Aspose.PDF dla .NET i skonfigurowałeś środowisko programistyczne, zanim zaczniesz.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do używania Aspose.PDF dla .NET. Obejmuje to zainstalowanie biblioteki Aspose.PDF i skonfigurowanie projektu, aby się do niej odwoływał.

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

Utworzyliśmy nowy dokument i ustawiliśmy jego tytuł oraz język.

## Krok 3: Uzyskanie elementu struktury korzenia

W tym kroku otrzymamy element struktury głównej naszego dokumentu.

```csharp
//Uzyskaj element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy element struktury głównej, który będzie służył jako pojemnik na elementy tablicy.

## Krok 4: Tworzenie elementu struktury tablicy

Teraz utwórzmy nowy element struktury tabeli dla naszego dokumentu.

```csharp
// Utwórz element struktury tablicy
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Stworzyliśmy nowy element struktury tablicy i dodaliśmy go do elementu struktury głównej. Stworzyliśmy również elementy nagłówka, treści i stopki tabeli.

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

Stworzyliśmy wiersz nagłówka dla naszej tabeli i dodaliśmy komórki nagłówka z właściwościami formatowania, takimi jak kolor tła, obramowanie, marginesy i wyrównanie.

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

Dodaliśmy wiersze do treści tabeli, używając pętli do iterowania po każdej komórce tabeli. Ustawiamy właściwości formatowania dla każdej komórki, takie jak kolor tła, obramowania, marginesy, wyrównanie tekstu itp.

## Krok 7: Dodawanie stopki

Na koniec dodamy stopkę do naszej tabeli.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Stworzyliśmy stopkę dla naszej tabeli i dodaliśmy komórki stopki zawierające tekst.



## Krok 8: Zapisywanie oznaczonego dokumentu PDF

Teraz, gdy utworzyliśmy dokument ze stylizowaną tabelą, zapiszemy go jako oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");
```

Zapisaliśmy oznaczony dokument PDF w podanym katalogu.

## Krok 9: Walidacja zgodności z PDF/UA

Następnie zweryfikujemy zgodność naszego dokumentu z formatem PDF/UA.

```csharp
// Sprawdzenie zgodności PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Przesłaliśmy oznaczony dokument PDF i sprawdziliśmy jego zgodność ze standardem PDF/UA, generując raport XML.

### Przykładowy kod źródłowy dla komórki tabeli stylów przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Pobierz element struktury korzenia
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

// Sprawdzanie zgodności PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

tym samouczku nauczyliśmy się, jak stylizować komórki tabeli za pomocą Aspose.PDF dla .NET. Zobaczyliśmy, jak utworzyć dokument, dodać tabelę z nagłówkami, wierszami treści i stopką oraz dostosować style komórek. Na koniec zapisaliśmy oznaczony dokument PDF i sprawdziliśmy jego zgodność z PDF/UA. Teraz możesz używać Aspose.PDF dla .NET do tworzenia i stylizowania tabel w aplikacjach .NET.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego samouczka dotyczącego formatowania komórek tabeli za pomocą Aspose.PDF dla platformy .NET?

A: Ten samouczek ma na celu dostarczenie kompleksowego przewodnika na temat tego, jak stylizować komórki tabeli w dokumencie PDF przy użyciu biblioteki Aspose.PDF dla .NET. Obejmuje instrukcje krok po kroku i przykłady kodu źródłowego C#, aby pomóc Ci zrozumieć i zaimplementować formatowanie komórek tabeli.

#### P: Jakie wymagania muszę spełnić, aby móc skorzystać z tego samouczka?

A: Zanim zaczniesz, upewnij się, że zainstalowałeś Aspose.PDF dla .NET i skonfigurowałeś środowisko programistyczne. Obejmuje to skonfigurowanie projektu tak, aby odwoływał się do biblioteki Aspose.PDF.

#### P: Jak utworzyć nowy dokument PDF za pomocą Aspose.PDF dla platformy .NET?

A: Aby utworzyć nowy dokument PDF, należy utworzyć instancję`Document` obiekt z biblioteki Aspose.PDF. Dostarczony kod źródłowy C# pokazuje, jak utworzyć dokument i ustawić jego tytuł i język.

#### P: Jakie znaczenie ma element struktury głównej w dokumencie PDF?

A: Element struktury głównej służy jako pojemnik dla innych elementów struktury, pomagając organizować i kategoryzować zawartość dokumentu PDF. Odgrywa kluczową rolę w ustalaniu logicznej struktury dokumentu.

#### P: W jaki sposób mogę utworzyć element struktury tabeli i dostosować jego wygląd, korzystając z Aspose.PDF dla platformy .NET?

 A: Możesz utworzyć element struktury tabeli za pomocą`CreateTableElement()` metoda. Dostarczony kod źródłowy pokazuje, jak dostosować wygląd tabeli, w tym jej nagłówek, treść i stopkę, ustawiając właściwości, takie jak kolor tła, obramowania, marginesy i wyrównanie.

#### P: Czy mogę dodać wiele wierszy i kolumn do treści tabeli oraz dostosować ich formatowanie?

A: Tak, samouczek pokazuje, jak dodać wiele wierszy i kolumn do treści tabeli za pomocą pętli. Zawiera również przykłady dostosowywania formatowania komórek, takie jak kolor tła, obramowania, wyrównanie tekstu, styl czcionki i inne.

#### P: Jaki jest cel weryfikacji zgodności PDF/UA i w jaki sposób mogę przeprowadzić taką weryfikację?

 A: Walidacja zgodności PDF/UA zapewnia, że dokument PDF jest zgodny ze standardami dostępności, dzięki czemu jest bardziej dostępny dla użytkowników niepełnosprawnych. Samouczek pokazuje, jak zweryfikować zgodność PDF/UA za pomocą`Validate()` i wygeneruj raport XML.

#### P: W jaki sposób mogę zastosować te koncepcje we własnych aplikacjach .NET?

A: Możesz użyć podanych przykładów kodu źródłowego C# jako przewodnika do implementacji formatowania komórek tabeli w swoich własnych aplikacjach .NET. Dostosuj kod w razie potrzeby, aby spełnić swoje wymagania i zintegruj go ze swoimi projektami.

#### P: Czy istnieją jakieś zalecane najlepsze praktyki dotyczące stylizowania komórek tabeli w dokumentach PDF?

A: Stylizując komórki tabeli, weź pod uwagę potrzeby odbiorców, w tym wymagania dotyczące dostępności. Użyj kontrastujących kolorów, odpowiednich czcionek i wyraźnego wyrównania komórek, aby zwiększyć czytelność. Ponadto sprawdź zgodność z PDF/UA, aby zapewnić spełnienie standardów dostępności.

#### P: Jakie inne funkcje Aspose.PDF dla .NET mogę wykorzystać do manipulowania dokumentami PDF?

A: Aspose.PDF dla .NET oferuje szeroki zakres funkcji do manipulacji dokumentami PDF, w tym ekstrakcję tekstu, wstawianie obrazów, zarządzanie polami formularzy, podpisy cyfrowe i wiele innych. Zapoznaj się z oficjalną dokumentacją i zasobami, aby dowiedzieć się więcej o dodatkowych funkcjonalnościach.
