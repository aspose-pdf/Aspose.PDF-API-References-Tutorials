---
title: Element tabeli stylów
linktitle: Element tabeli stylów
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak formatować element tabeli za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku, jak dostosować style i właściwości.
type: docs
weight: 170
url: /pl/net/programming-with-tagged-pdf/style-table-element/
---
tym szczegółowym samouczku przeprowadzimy Cię krok po kroku przez podany kod źródłowy C#, aby sformatować element tablicy za pomocą Aspose.PDF dla .NET. Postępuj zgodnie z poniższymi instrukcjami, aby dowiedzieć się, jak dostosować style i właściwości elementu tablicy.

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
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Utworzyliśmy nowy dokument i ustawiliśmy jego tytuł oraz język.

## Krok 3: Uzyskanie elementu struktury korzenia

W tym kroku otrzymamy element struktury głównej naszego dokumentu.

```csharp
//Uzyskaj element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;
```

Otrzymaliśmy element struktury głównej, który będzie służył jako pojemnik dla elementów tablicy.

## Krok 4: Tworzenie elementu struktury tablicy

Teraz utwórzmy nowy element struktury tabeli dla naszego dokumentu.

```csharp
// Utwórz element struktury tablicy
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Utworzyliśmy nowy element struktury tablicy i dodaliśmy go do elementu struktury głównej.

## Krok 5: Dostosowywanie stylów i właściwości elementów tablicy

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

Użyliśmy różnych właściwości, aby dostosować element tabeli, takie jak kolor tła, obramowanie, wyrównanie, domyślny styl komórki, marginesy, szerokość kolumny itp.

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

// Dodaj linię bazową tabeli
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Dodaliśmy nagłówki, wiersze treści i wiersz stopki do tabeli, używając odpowiednich elementów.

## Krok 7: Zapisywanie oznaczonego dokumentu PDF

Teraz, gdy utworzyliśmy dokument ze stylizowanym elementem tabeli, zapiszemy go jako oznaczony dokument PDF.

```csharp
// Zapisz oznaczony dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");
```

Zapisaliśmy oznaczony dokument PDF w podanym katalogu.

## Krok 8: Walidacja zgodności PDF/UA

Następnie zweryfikujemy zgodność naszego dokumentu z formatem PDF/UA.

```csharp
// Sprawdzenie zgodności PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Przesłaliśmy oznaczony dokument PDF i sprawdziliśmy jego zgodność ze standardem PDF/UA, generując raport XML.

### Przykładowy kod źródłowy dla elementu tabeli stylów przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Pobierz element struktury korzenia
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

// Sprawdzanie zgodności PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

W tym samouczku nauczyliśmy się, jak sformatować element tablicy za pomocą Aspose.PDF dla .NET. Dostosowaliśmy style i właściwości elementu tabeli, dodaliśmy nagłówki, wiersze treści i stopkę, zapisaliśmy oznaczony dokument PDF i sprawdziliśmy jego zgodność z PDF/UA.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego samouczka dotyczącego formatowania elementów tablicy za pomocą Aspose.PDF dla platformy .NET?

A: Celem tego samouczka jest przeprowadzenie Cię przez proces formatowania elementu tablicy w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Zawiera instrukcje krok po kroku i przykłady kodu źródłowego C#, które pomogą Ci dostosować style i właściwości elementu tablicy.

#### P: Jakie wymagania muszę spełnić, aby móc skorzystać z tego samouczka?

A: Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne do używania Aspose.PDF dla .NET. Wiąże się to z zainstalowaniem biblioteki Aspose.PDF i skonfigurowaniem projektu tak, aby się do niej odwoływał.

#### P: W jaki sposób mogę utworzyć nowy dokument PDF i ustawić jego tytuł oraz język za pomocą Aspose.PDF dla platformy .NET?

 A: Aby utworzyć nowy dokument PDF, należy utworzyć`Document` obiekt z biblioteki Aspose.PDF. Dostarczony w samouczku kod źródłowy C# pokazuje, jak utworzyć dokument i ustawić jego tytuł oraz właściwości języka.

#### P: Jakie znaczenie ma element struktury głównej w dokumencie PDF?

A: Element struktury głównej działa jako pojemnik dla innych elementów struktury, pomagając w organizacji i kategoryzowaniu zawartości dokumentu PDF. Odgrywa kluczową rolę w ustalaniu logicznej struktury dokumentu.

#### P: Jak utworzyć i dostosować element struktury tablicy za pomocą Aspose.PDF dla platformy .NET?

 A: Możesz utworzyć element struktury tablicy za pomocą`CreateTableElement()` metoda. Kod źródłowy samouczka zawiera przykłady dostosowywania różnych właściwości elementu tabeli, takich jak kolor tła, obramowanie, wyrównanie, szerokość kolumny i inne.

#### P: Czy mogę dostosować style i właściwości komórek tabeli w elemencie tablicy?

A: Tak, samouczek obejmuje sposób dostosowywania stylów i właściwości całego elementu tabeli, w tym nagłówków, wierszy treści i stopki. Jednak nie dotyczy on konkretnie dostosowywania poszczególnych komórek tabeli.

#### P: Jak mogę dodać nagłówki, wiersze treści i stopkę do elementu tabeli?

A: W tym samouczku wyjaśniono, jak tworzyć i dodawać nagłówki, wiersze treści i stopkę do elementu tabeli, korzystając z odpowiednich metod udostępnionych przez Aspose.PDF dla platformy .NET.

#### P: Na czym polega zgodność PDF/UA i jak mogę ją sprawdzić w przypadku mojego oznaczonego dokumentu PDF?

 A: Zgodność z PDF/UA zapewnia zgodność dokumentu PDF ze standardami dostępności, dzięki czemu jest on bardziej dostępny dla użytkowników niepełnosprawnych. Samouczek pokazuje, jak sprawdzić zgodność PDF/UA za pomocą`Validate()` metodę i wygeneruj raport zgodności XML.

#### P: W jaki sposób mogę włączyć te koncepcje do moich własnych aplikacji .NET?

A: Możesz użyć podanych przykładów kodu źródłowego C# jako przewodnika do implementacji formatowania elementów tablicy we własnych aplikacjach .NET. Modyfikuj i dostosuj kod, aby odpowiadał Twoim wymaganiom i zintegruj go ze swoimi projektami.

#### P: Czy istnieją jakieś zalecane najlepsze praktyki formatowania elementów tablic w dokumentach PDF?

A: Podczas formatowania elementów tablicy (tabel) należy wziąć pod uwagę czytelność i dostępność treści. Używaj wyraźnych i czytelnych czcionek, odpowiednich kolorów i zachowaj spójny układ. Sprawdź zgodność PDF/UA, aby zapewnić spełnienie standardów dostępności.

#### P: Jakie inne funkcje Aspose.PDF dla .NET mogę wykorzystać do personalizacji dokumentów PDF?

A: Aspose.PDF dla .NET oferuje szereg funkcji do dostosowywania dokumentów PDF, w tym manipulację tekstem, wstawianie obrazów, zarządzanie polami formularzy, podpisy cyfrowe, adnotacje i wiele innych. Zapoznaj się z oficjalną dokumentacją i zasobami, aby poznać dodatkowe funkcjonalności.