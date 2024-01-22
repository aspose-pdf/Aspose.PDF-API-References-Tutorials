---
title: Element tabeli stylu
linktitle: Element tabeli stylu
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak sformatować element tabeli za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku dotyczący dostosowywania stylów i właściwości.
type: docs
weight: 170
url: /pl/net/programming-with-tagged-pdf/style-table-element/
---
tym szczegółowym samouczku przeprowadzimy Cię krok po kroku przez dostarczony kod źródłowy C#, aby sformatować element tablicy przy użyciu Aspose.PDF dla .NET. Postępuj zgodnie z poniższymi instrukcjami, aby dowiedzieć się, jak dostosować style i właściwości elementu tablicy.

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
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Stworzyliśmy nowy dokument oraz ustawiliśmy tytuł i język dokumentu.

## Krok 3: Uzyskanie elementu struktury korzenia

W tym kroku otrzymamy element struktury głównej naszego dokumentu.

```csharp
//Zdobądź element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy element struktury korzenia, który będzie służył jako kontener dla elementu tablicy.

## Krok 4: Tworzenie elementu struktury tablicowej

Stwórzmy teraz nowy element struktury tabeli dla naszego dokumentu.

```csharp
// Utwórz element struktury tablicowej
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Stworzyliśmy nowy element struktury tablicowej i dodaliśmy go do elementu struktury głównej.

## Krok 5: Dostosowywanie stylów i właściwości elementów szyku

W tym kroku dostosujemy style i właściwości elementu tablicy.

```csharp
// Dostosuj style i właściwości elementu tablicy
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Dostosuj styl powtarzających się linii
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

Aby dostosować element tabeli, użyliśmy różnych właściwości, takich jak kolor tła, obramowania, wyrównanie, domyślny styl komórki, marginesy, szerokość kolumny itp.

## Krok 6: Dodaj nagłówki, treść i stopkę tabeli

Teraz dodajmy nagłówki, treść i stopkę tabeli do elementu tabeli.
```csharp
// Dodaj nagłówki tabeli
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Liczba wierszy i kolumn w tabeli
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Utwórz wiersz nagłówka tabeli
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Dodaj wiersze treści tabeli
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Dodaj linię podstawy tabeli
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Do tabeli dodaliśmy nagłówki, wiersze treści i wiersz stopki, korzystając z odpowiednich elementów.

## Krok 7: Zapisywanie oznaczonego dokumentu PDF

Teraz, gdy utworzyliśmy dokument ze stylizowanym elementem tabeli, zapiszemy go jako oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");
```

Zapisaliśmy oznaczony dokument PDF w określonym katalogu.

## Krok 8: Sprawdzanie zgodności z PDF/UA

Następnie sprawdzimy zgodność naszego dokumentu z PDF/UA.

```csharp
// Kontrola zgodności z PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Przesłaliśmy oznaczony tagiem dokument PDF i sprawdziliśmy jego zgodność z PDF/UA, generując raport XML.

### Przykładowy kod źródłowy elementu tabeli stylów przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Uzyskaj element struktury głównej
StructureElement rootElement = taggedContent.RootElement;

// Utwórz element struktury tabeli
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
document.Save(dataDir + "StyleTableElement.pdf");

// Sprawdzanie zgodności z PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyliśmy się, jak sformatować element tablicy za pomocą Aspose.PDF dla .NET. Dostosowaliśmy style i właściwości elementu tabeli, dodaliśmy nagłówki, wiersze treści i stopkę, zapisaliśmy oznaczony tagami dokument PDF i sprawdziliśmy jego zgodność z PDF/UA.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka dotyczącego formatowania elementu tablicy przy użyciu Aspose.PDF dla .NET?

Odp.: Celem tego samouczka jest poprowadzenie Cię przez proces formatowania elementu tablicy w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Zawiera instrukcje krok po kroku i przykłady kodu źródłowego języka C#, które ułatwiają dostosowywanie stylów i właściwości elementu tablicy.

#### P: Jakie są wymagania wstępne dotyczące korzystania z tego samouczka?

O: Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do korzystania z Aspose.PDF dla .NET. Obejmuje to zainstalowanie biblioteki Aspose.PDF i skonfigurowanie projektu tak, aby się do niej odwoływał.

#### P: Jak mogę utworzyć nowy dokument PDF i ustawić jego tytuł i język za pomocą Aspose.PDF dla .NET?

 Odp.: Aby utworzyć nowy dokument PDF, musisz utworzyć plik`Document` obiekt z biblioteki Aspose.PDF. Kod źródłowy języka C# podany w samouczku demonstruje, jak utworzyć dokument i ustawić jego tytuł i właściwości językowe.

#### P: Jakie jest znaczenie elementu struktury głównej w dokumencie PDF?

Odp.: Główny element struktury działa jak pojemnik na inne elementy struktury, pomagając organizować i kategoryzować zawartość dokumentu PDF. Odgrywa kluczową rolę w ustaleniu logicznej struktury dokumentu.

#### P: Jak utworzyć i dostosować element struktury tablicowej przy użyciu Aspose.PDF dla .NET?

 Odp.: Możesz utworzyć element struktury tablicowej za pomocą`CreateTableElement()` metoda. Kod źródłowy samouczka zawiera przykłady dostosowywania różnych właściwości elementu tabeli, takich jak kolor tła, obramowania, wyrównanie, szerokość kolumny i inne.

#### P: Czy mogę dostosować style i właściwości komórek tabeli w elemencie tablicy?

O: Tak, w tym samouczku opisano, jak dostosować style i właściwości całego elementu tabeli, w tym nagłówków, wierszy treści i stopki. Nie dotyczy to jednak konkretnie dostosowywania poszczególnych komórek tabeli.

#### P: Jak mogę dodać nagłówki, wiersze treści i stopkę do elementu tabeli?

Odp.: W samouczku wyjaśniono, jak tworzyć i dodawać nagłówki, wiersze treści i stopkę do elementu tabeli przy użyciu odpowiednich metod dostarczonych przez Aspose.PDF dla .NET.

#### P: Jaka jest zgodność z formatem PDF/UA i jak mogę ją sprawdzić w przypadku mojego oznaczonego dokumentu PDF?

 Odp.: Zgodność z formatem PDF/UA gwarantuje, że dokument PDF jest zgodny ze standardami dostępności, dzięki czemu jest bardziej dostępny dla użytkowników niepełnosprawnych. W samouczku pokazano, jak sprawdzić zgodność z PDF/UA za pomocą pliku`Validate()` metodę i wygenerować raport zgodności XML.

#### P: Jak mogę włączyć te koncepcje do moich własnych aplikacji .NET?

Odp.: Możesz użyć dostarczonych przykładów kodu źródłowego C# jako przewodnika po implementowaniu formatowania elementów tablicy we własnych aplikacjach .NET. Zmodyfikuj i dostosuj kod do swoich wymagań i zintegruj go ze swoimi projektami.

#### P: Czy są jakieś zalecane najlepsze praktyki dotyczące formatowania elementów tablicy w dokumentach PDF?

Odp.: Podczas formatowania elementów tablicy (tabel) należy wziąć pod uwagę czytelność i dostępność treści. Stosuj jasne i czytelne czcionki, odpowiednią kolorystykę i zachowaj spójny układ. Sprawdź zgodność z PDF/UA, aby upewnić się, że spełnione są standardy dostępności.

#### P: Jakie inne funkcje Aspose.PDF dla .NET mogę wykorzystać w celu dostosowania dokumentu PDF?

Odp.: Aspose.PDF dla .NET oferuje szereg funkcji dostosowywania dokumentów PDF, w tym manipulację tekstem, wstawianie obrazów, zarządzanie polami formularzy, podpisy cyfrowe, adnotacje i inne. Zapoznaj się z oficjalną dokumentacją i zasobami, aby poznać dodatkowe funkcje.