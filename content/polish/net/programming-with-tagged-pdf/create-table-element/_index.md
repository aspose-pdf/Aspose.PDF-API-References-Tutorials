---
title: Utwórz element tabeli
linktitle: Utwórz element tabeli
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący tworzenia elementu tablicy za pomocą Aspose.PDF dla .NET. Z łatwością generuj dynamiczne pliki PDF z tabelami.
type: docs
weight: 80
url: /pl/net/programming-with-tagged-pdf/create-table-element/
---
tym przewodniku krok po kroku przeprowadzimy Cię przez proces tworzenia elementu tablicy przy użyciu Aspose.PDF dla .NET. Aspose.PDF to potężna biblioteka, która pozwala programowo manipulować dokumentami PDF. Tworzenie elementu tablicy jest częstym wymogiem podczas generowania dynamicznych plików PDF, a Aspose.PDF oferuje łatwy i skuteczny sposób na osiągnięcie tego.

Zagłębmy się w kod i dowiedzmy się, jak utworzyć element tablicy przy użyciu Aspose.PDF dla .NET.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Zainstalowana biblioteka Aspose.PDF dla .NET.
2. Podstawowa znajomość języka programowania C#.

## Krok 1: Konfigurowanie środowiska

Aby rozpocząć, otwórz środowisko programistyczne C# i utwórz nowy projekt. Upewnij się, że w swoim projekcie dodałeś odniesienie do biblioteki Aspose.PDF dla .NET.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu

 Pierwszym krokiem jest utworzenie nowego dokumentu PDF za pomocą`Document` klasa.

```csharp
// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Tutaj ustawiamy także tytuł i język otagowanej treści.

## Krok 3: Tworzenie elementu tablicy

Następnie musimy utworzyć element tablicy i dodać go do dokumentu. Zaczynamy od pobrania głównego elementu struktury, następnie tworzymy nowy element tabeli za pomocą`CreateTableElement` metoda.

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

// Kontrola zgodności z PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Przykładowy kod źródłowy narzędzia Utwórz element tabeli przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Uzyskaj element struktury głównej
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

// Sprawdzanie zgodności z PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Wniosek

Nauczyłeś się, jak utworzyć element tablicy przy użyciu Aspose.PDF dla .NET. Za pomocą tej metody można teraz generować dokumenty PDF z tabelami dynamicznymi. Zachęcamy do zapoznania się z większą liczbą funkcji Aspose.PDF, aby odkryć jego pełny potencjał.

### Często zadawane pytania

#### P: Co to jest element tablicy w dokumencie PDF i dlaczego miałbym go utworzyć przy użyciu Aspose.PDF dla .NET?

Odp.: Element tablicy w dokumencie PDF reprezentuje uporządkowany zbiór danych, często używany do tworzenia tabel lub siatek. Może być konieczne utworzenie elementu tablicy przy użyciu Aspose.PDF dla .NET podczas generowania dynamicznych plików PDF, które wymagają prezentacji danych strukturalnych, takich jak informacje tabelaryczne lub siatki.

#### P: W jaki sposób Aspose.PDF dla .NET upraszcza proces tworzenia elementu tablicy?

Odp.: Aspose.PDF dla .NET zapewnia kompleksowy zestaw klas i metod, które pozwalają programowo tworzyć, dostosowywać i zarządzać elementami tablicy (tabelami) w dokumencie PDF. Eliminuje to potrzebę ręcznej manipulacji plikami PDF i usprawnia tworzenie ustrukturyzowanych reprezentacji danych.

#### P: Jakie są kluczowe kroki związane z tworzeniem elementu tablicy przy użyciu Aspose.PDF dla .NET?

O: Kluczowe kroki obejmują skonfigurowanie środowiska, utworzenie dokumentu, uzyskanie głównego elementu struktury, utworzenie elementu tabeli, zdefiniowanie wierszy i komórek w tabeli oraz określenie formatowania i właściwości elementów. Podany przykład kodu demonstruje te kroki.

####  P: Jaką rolę odgrywa`taggedContent` object play in creating an array element?

 O:`taggedContent` obiekt, uzyskany z dokumentu`TaggedContent`umożliwia zdefiniowanie struktury oznaczonej treści w dokumencie PDF. Obejmuje to tworzenie i organizowanie elementów tablicy i ich elementów podrzędnych w sposób hierarchiczny.

#### P: W jaki sposób kod zapewnia dostępność i semantykę utworzonego elementu tablicy?

 Odp.: Kod ustawia atrybuty takie jak`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , I`ColSpan` w celu zwiększenia dostępności i semantyki elementu tablicy. Atrybuty te przyczyniają się do dobrze zorganizowanej, informacyjnej i atrakcyjnej wizualnie reprezentacji danych.

#### P: Jakie znaczenie ma zgodność z PDF/UA w kontekście tworzenia elementów tablicy?

 Odp.: Zgodność z formatem PDF/UA (uniwersalna dostępność) zapewnia, że wygenerowane dokumenty PDF są dostępne dla użytkowników niepełnosprawnych i spełniają określone standardy dostępności. Przykładowy kod sprawdza zgodność z PDF/UA za pomocą`Validate` która pomoże Ci stworzyć dokumenty, które będą włączające i dostępne.

#### P: Czy mogę bardziej dostosować formatowanie i wygląd elementów tablicy?

O: Tak, możesz dostosować formatowanie i wygląd elementów tablicy, dostosowując atrybuty, takie jak kolor tła, styl obramowania, rozmiar czcionki i wyrównanie. Aspose.PDF dla .NET zapewnia szeroką gamę właściwości pozwalających dostosować prezentację wizualną do Twoich wymagań.

#### P: Jak mogę rozszerzyć tę wiedzę, aby tworzyć bardziej złożone struktury tabel lub włączać elementy tablic do większych dokumentów PDF?

Odp.: Możesz poszerzyć tę wiedzę, eksplorując dodatkowe funkcje Aspose.PDF dla .NET, takie jak łączenie wielu elementów tablicy, tworzenie zagnieżdżonych tabel, dodawanie nagłówków i stopek oraz integrowanie elementów tablicy w większe układy PDF. Dokumentacja i przykłady biblioteki zawierają wskazówki dotyczące tych zaawansowanych scenariuszy.

#### P: Czy można importować dane ze źródeł zewnętrznych, takich jak bazy danych lub arkusze kalkulacyjne, w celu zapełnienia elementów tablicy?

O: Tak, możesz importować dane ze źródeł zewnętrznych, aby wypełnić elementy tablicy. Za pomocą technik pobierania i przekształcania danych w języku C# można pobierać dane z baz danych, arkuszy kalkulacyjnych lub innych źródeł, a następnie odpowiednio wypełniać elementy tablicy.

#### P: Jak mogę wykorzystać wiedzę zdobytą w tym samouczku, aby poprawić jakość i użyteczność dokumentów PDF tworzonych programowo?

Odp.: Wiedza zdobyta w tym samouczku umożliwia tworzenie uporządkowanych i atrakcyjnych wizualnie elementów tablicowych (tabel) w dokumentach PDF. Stosując te techniki, można poprawić czytelność, dostępność i wygodę użytkownika dynamicznie generowanych plików PDF, czyniąc je bardziej informacyjnymi i przyjaznymi dla użytkownika.