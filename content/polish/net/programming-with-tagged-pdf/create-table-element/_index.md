---
title: Utwórz element tabeli
linktitle: Utwórz element tabeli
second_title: Aspose.PDF dla .NET API Reference
description: Przewodnik krok po kroku, jak utworzyć element tablicy za pomocą Aspose.PDF dla platformy .NET. Łatwe generowanie dynamicznych plików PDF z tabelami.
type: docs
weight: 80
url: /pl/net/programming-with-tagged-pdf/create-table-element/
---
tym przewodniku krok po kroku przeprowadzimy Cię przez proces tworzenia elementu tablicy przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która umożliwia programowe manipulowanie dokumentami PDF. Tworzenie elementu tablicy jest powszechnym wymogiem podczas generowania dynamicznych plików PDF, a Aspose.PDF oferuje łatwy i wydajny sposób na osiągnięcie tego celu.

Przyjrzyjmy się bliżej kodowi i dowiedzmy się, jak utworzyć element tablicy za pomocą Aspose.PDF dla platformy .NET.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

1. Zainstalowano bibliotekę Aspose.PDF dla .NET.
2. Podstawowa znajomość języka programowania C#.

## Krok 1: Konfigurowanie środowiska

Aby rozpocząć, otwórz środowisko programistyczne C# i utwórz nowy projekt. Upewnij się, że dodałeś odwołanie do biblioteki Aspose.PDF dla .NET w swoim projekcie.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu

 Pierwszym krokiem jest utworzenie nowego dokumentu PDF przy użyciu`Document` klasa.

```csharp
// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Tutaj ustawiamy również tytuł i język dla oznaczonej treści.

## Krok 3: Tworzenie elementu tablicy

Następnie musimy utworzyć element tablicy i dodać go do dokumentu. Zaczynamy od pobrania elementu struktury głównej, a następnie tworzymy nowy element tabeli za pomocą`CreateTableElement` metoda.

```csharp
// Pobierz element struktury głównej
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Zapisz oznaczony dokument PDF
document.Save(dataDir + "CreateTableElement.pdf");

// Sprawdzenie zgodności PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Przykładowy kod źródłowy dla funkcji Create Table Element using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Pobierz element struktury korzenia
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Zapisz oznaczony dokument PDF
document.Save(dataDir + "CreateTableElement.pdf");

// Sprawdzanie zgodności PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

Nauczyłeś się, jak utworzyć element tablicy za pomocą Aspose.PDF dla .NET. Teraz możesz generować dokumenty PDF z dynamicznymi tabelami za pomocą tej metody. Możesz swobodnie odkrywać więcej funkcji Aspose.PDF, aby odkryć jego pełny potencjał.

### Najczęściej zadawane pytania

#### P: Czym jest element tablicy w dokumencie PDF i dlaczego muszę go utworzyć za pomocą Aspose.PDF dla platformy .NET?

A: Element tablicy w dokumencie PDF reprezentuje ustrukturyzowaną kolekcję danych, często używaną do tworzenia tabel lub siatek. Może być konieczne utworzenie elementu tablicy przy użyciu Aspose.PDF dla .NET podczas generowania dynamicznych plików PDF, które wymagają ustrukturyzowanej prezentacji danych, takiej jak informacje tabelaryczne lub siatki.

#### P: W jaki sposób Aspose.PDF dla .NET upraszcza proces tworzenia elementów tablicy?

A: Aspose.PDF dla .NET zapewnia kompleksowy zestaw klas i metod, które umożliwiają programowe tworzenie, dostosowywanie i zarządzanie elementami tablic (tabelami) w dokumencie PDF. Eliminuje to potrzebę ręcznej manipulacji PDF i usprawnia tworzenie reprezentacji danych strukturalnych.

#### P: Jakie są najważniejsze kroki w procesie tworzenia elementu tablicy za pomocą Aspose.PDF dla platformy .NET?

A: Kluczowe kroki obejmują skonfigurowanie środowiska, utworzenie dokumentu, uzyskanie elementu struktury głównej, utworzenie elementu tabeli, zdefiniowanie wierszy i komórek w tabeli oraz określenie formatowania i właściwości dla elementów. Dostarczony przykład kodu demonstruje te kroki.

####  P: Jaką rolę pełni`taggedContent` object play in creating an array element?

 A: Ten`taggedContent` obiekt, uzyskany z dokumentu`TaggedContent`Właściwość, pozwala zdefiniować strukturę oznaczonej zawartości w dokumencie PDF. Obejmuje to tworzenie i organizowanie elementów tablicy i ich elementów podrzędnych w sposób hierarchiczny.

#### P: W jaki sposób kod zapewnia dostępność i semantykę utworzonego elementu tablicy?

 A: Kod ustawia atrybuty takie jak:`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , I`ColSpan` aby zwiększyć dostępność i semantykę elementu tablicy. Te atrybuty przyczyniają się do dobrze ustrukturyzowanej, informacyjnej i atrakcyjnej wizualnie reprezentacji danych.

#### P: Jakie znaczenie ma zgodność ze standardem PDF/UA w kontekście tworzenia elementów tablic?

 A: Zgodność z PDF/UA (Universal Accessibility) zapewnia, że wygenerowane dokumenty PDF są dostępne dla użytkowników niepełnosprawnych i spełniają określone standardy dostępności. Przykład kodu sprawdza zgodność z PDF/UA za pomocą`Validate` metoda pomagająca tworzyć dokumenty, które są inkluzywne i dostępne.

#### P: Czy mogę dodatkowo dostosować formatowanie i wygląd elementów tablicy?

A: Tak, możesz dostosować formatowanie i wygląd elementów tablicy, dostosowując atrybuty, takie jak kolor tła, styl obramowania, rozmiar czcionki i wyrównanie. Aspose.PDF dla .NET zapewnia szeroki zakres właściwości, aby dostosować prezentację wizualną do Twoich wymagań.

#### P: W jaki sposób mogę rozszerzyć tę wiedzę, aby tworzyć bardziej złożone struktury tabel lub włączać elementy tablic do większych dokumentów PDF?

A: Możesz poszerzyć tę wiedzę, poznając dodatkowe funkcje Aspose.PDF dla .NET, takie jak scalanie wielu elementów tablic, tworzenie zagnieżdżonych tabel, dodawanie nagłówków i stopek oraz integrowanie elementów tablic w większych układach PDF. Dokumentacja biblioteki i przykłady zawierają wskazówki dotyczące tych zaawansowanych scenariuszy.

#### P: Czy można importować dane z zewnętrznych źródeł, takich jak bazy danych lub arkusze kalkulacyjne, aby wypełnić nimi elementy tablicy?

A: Tak, możesz importować dane z zewnętrznych źródeł, aby wypełnić elementy tablicy. Możesz użyć technik pobierania i transformacji danych w C#, aby pobrać dane z baz danych, arkuszy kalkulacyjnych lub innych źródeł, a następnie odpowiednio wypełnić elementy tablicy.

#### P: W jaki sposób mogę wykorzystać wiedzę zdobytą w tym samouczku, aby poprawić jakość i użyteczność dokumentów PDF tworzonych programowo?

A: Wiedza zdobyta w tym samouczku pozwala tworzyć ustrukturyzowane i wizualnie atrakcyjne elementy tablicowe (tabele) w dokumentach PDF. Włączając te techniki, możesz poprawić czytelność, dostępność i doświadczenie użytkownika dynamicznie generowanych plików PDF, czyniąc je bardziej informacyjnymi i przyjaznymi dla użytkownika.