---
title: Ukryj numery stron w spisie treści
linktitle: Ukryj numery stron w spisie treści
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak ukryć numery stron w spisie treści za pomocą Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 220
url: /pl/net/programming-with-document/hidepagenumbersintoc/
---
W tym artykule omówimy implementację funkcji Ukryj numery stron w spisie treści w Aspose.PDF dla .NET przy użyciu C#. Zaczniemy od krótkiego wprowadzenia do Aspose.PDF dla .NET, a następnie zagłębimy się w przewodnik krok po kroku dotyczący wdrożenia tej funkcji. 

## Wprowadzenie do Aspose.PDF dla .NET

Aspose.PDF dla .NET to potężny komponent do manipulacji plikami PDF, który umożliwia programistom programowe tworzenie, edytowanie i manipulowanie plikami PDF. Zapewnia szeroką gamę funkcji i funkcjonalności, które ułatwiają pracę z dokumentami PDF. Aspose.PDF dla .NET obsługuje zarówno 32-bitowe, jak i 64-bitowe systemy operacyjne i może być używany z platformami .NET Framework, .NET Core i Xamarin. 

## Co to jest funkcja Ukryj numery stron w spisie treści?

Spis treści (TOC) to istotna część dokumentu PDF, która zapewnia użytkownikom szybki przegląd zawartości. Czasami użytkownicy mogą chcieć ukryć numery stron w spisie treści, aby uczynić go bardziej przyjaznym dla użytkownika. Aspose.PDF dla .NET zapewnia wbudowaną funkcję ukrywania numerów stron w spisie treści. Tej funkcji można używać do tworzenia bardziej przyjaznych dla użytkownika dokumentów PDF. 

## Warunki wstępne

Aby skorzystać z tego samouczka, będziesz potrzebować:

- Visual Studio 2010 lub nowszy
- Aspose.PDF dla .NET zainstalowany w twoim systemie
- Podstawowa znajomość języka programowania C#

## Przewodnik krok po kroku dotyczący wdrożenia funkcji Ukryj numery stron w spisie treści

Wykonaj poniższe kroki, aby zaimplementować funkcję Ukryj numery stron w spisie treści przy użyciu Aspose.PDF dla .NET:

## Krok 1: Utwórz nową aplikację konsolową C# w Visual Studio

Otwórz program Visual Studio i utwórz nową aplikację konsolową C#.

## Krok 2: Dodaj odniesienie do Aspose.PDF dla .NET

Kliknij prawym przyciskiem myszy folder Odniesienia w projekcie i wybierz opcję Dodaj odniesienie. Przejdź do lokalizacji, w której jest zainstalowany Aspose.PDF dla .NET w twoim systemie i dodaj do niej odniesienie.

## Krok 1: Utwórz nowy dokument PDF

Utwórz nowy dokument PDF, używając następującego kodu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Krok 2: Utwórz stronę spisu treści

Utwórz nową stronę spisu treści i dodaj ją do dokumentu PDF, używając następującego kodu:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Krok 3: Dodaj sekcję listy do kolekcji sekcji dokumentu PDF

Dodaj sekcję listy do kolekcji sekcji dokumentu PDF, używając następującego kodu:

```csharp
tocPage.TocInfo = tocInfo;
```

## Krok 4: Zdefiniuj format listy czterech poziomów

Zdefiniuj format listy czterech poziomów, ustawiając lewe marginesy i ustawienia formatu tekstu na każdym poziomie, używając następującego kodu:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Krok 5: Dodaj cztery nagłówki w sekcji

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Przykładowy kod źródłowy do ukrywania numerów stron w spisie treści przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Dodaj sekcję listy do kolekcji sekcji dokumentu PDF
tocPage.TocInfo = tocInfo;
//Zdefiniuj format listy czterech poziomów, ustawiając lewe marginesy i
//ustawienia formatu tekstu na każdym poziomie

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Dodaj cztery nagłówki w sekcji
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Wniosek

W tym samouczku omówiliśmy, jak pracować z metadanymi XMP w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Metadane XMP dostarczają cennych informacji o dokumencie PDF, w tym jego tytułu, autora, daty utworzenia i innych. Aspose.PDF dla .NET umożliwia programistom dostęp do metadanych i manipulowanie nimi, zapewniając elastyczne i wydajne API do pracy z dokumentami PDF.

### Często zadawane pytania

#### P: Czym są metadane XMP w dokumencie PDF?

O: Metadane XMP (Extensible Metadata Platform) w dokumencie PDF to standardowy format przechowywania informacji o metadanych dokumentu. Zawiera szczegółowe informacje, takie jak tytuł dokumentu, autor, data utworzenia, słowa kluczowe i inne. Metadane XMP zapewniają ustrukturyzowany i ustandaryzowany sposób przechowywania i udostępniania informacji o dokumencie PDF.

#### P: Czy mogę modyfikować metadane XMP dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz programowo modyfikować metadane XMP dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz uzyskać dostęp do`Info` własność`Document` obiekt, który daje dostęp do właściwości metadanych XMP. Następnie możesz zaktualizować wartości tych właściwości, aby zmodyfikować metadane XMP dokumentu PDF.

#### P: Czy mogę wyodrębnić niestandardowe właściwości metadanych XMP z dokumentu PDF przy użyciu Aspose.PDF dla .NET?

 O: Tak, możesz wyodrębnić niestandardowe właściwości metadanych XMP z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Możesz skorzystać z`Metadata` własność`Document`obiekt, który zapewnia dostęp do wszystkich właściwości metadanych XMP dokumentu PDF. Następnie można wyodrębnić właściwości niestandardowe i użyć ich wartości w razie potrzeby.