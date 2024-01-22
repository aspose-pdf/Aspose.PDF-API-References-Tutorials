---
title: Dodaj spis treści do pliku PDF
linktitle: Dodaj spis treści do pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dodać spis treści do pliku PDF przy użyciu Aspose.PDF dla .NET. Przewodnik krok po kroku z przykładowym kodem źródłowym. Usprawnij nawigację po dokumentach!
type: docs
weight: 40
url: /pl/net/programming-with-document/addtoc/
---
W tym samouczku przyjrzymy się, jak używać funkcji Dodaj spis treści (spis treści) do pliku PDF w Aspose.PDF dla .NET, aby dodać spis treści do dokumentów PDF. Zapewnimy przewodnik krok po kroku i wyjaśnimy kod źródłowy C# wymagany do osiągnięcia tego celu. Pod koniec tego samouczka będziesz w stanie wygenerować dokument PDF ze spisem treści przy użyciu Aspose.PDF dla .NET.


## Krok 1: Załaduj istniejący plik PDF

 Aby rozpocząć, musimy załadować istniejący plik PDF. Zastępować`"YOUR DOCUMENT DIRECTORY"` w następującym kodzie z rzeczywistą ścieżką do pliku PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Krok 2: Utwórz nową stronę ze spisem treści

Stworzymy nową stronę, na której będzie przechowywany spis treści. Poniższy kod wstawia nową stronę w indeksie 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Krok 3: Zdefiniuj informacje dotyczące spisu treści

Następnie musimy zdefiniować informacje dotyczące spisu treści. Ustalimy tytuł i inne właściwości spisu treści. Dodaj następujący kod:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Krok 4: Utwórz elementy spisu treści

Teraz utworzymy elementy spisu treści. W tym samouczku utworzymy cztery elementy spisu treści odpowiadające różnym stronom. Zmodyfikuj następujący kod zgodnie ze swoimi wymaganiami:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Krok 5: Zapisz zaktualizowany dokument

 Na koniec musimy zapisać zmodyfikowany dokument wraz ze spisem treści. Zastępować`"YOUR DOCUMENT DIRECTORY"` w poniższym kodzie z żądaną ścieżką pliku wyjściowego:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dodawania spisu treści do dokumentów PDF przy użyciu Aspose.PDF dla .NET

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Załaduj istniejące pliki PDF
Document doc = new Document(dataDir + "AddTOC.pdf");

// Uzyskaj dostęp do pierwszej strony pliku PDF
Page tocPage = doc.Pages.Insert(1);

// Utwórz obiekt reprezentujący informacje o spisie treści
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Ustaw tytuł spisu treści
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Utwórz obiekty typu string, które będą używane jako elementy spisu treści
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Utwórz obiekt nagłówka
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Określ stronę docelową dla obiektu nagłówka
	heading2.DestinationPage = doc.Pages[i + 2];

	// Strona docelowa
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Współrzędna miejsca docelowego
	segment2.Text = titles[i];

	// Dodaj nagłówek do strony zawierającej spis treści
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Zapisz zaktualizowany dokument
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Wniosek

W tym samouczku omówiliśmy, jak dodać spis treści (TOC) do dokumentów PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z przewodnikiem krok po kroku i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo wygenerować dokument PDF ze spisem treści. Spis treści zwiększa użyteczność dokumentu, umożliwiając użytkownikom efektywniejsze nawigowanie do określonych sekcji lub stron. Aspose.PDF dla .NET zapewnia solidne i przyjazne dla użytkownika rozwiązanie do pracy z plikami PDF w aplikacjach .NET, umożliwiając łatwe tworzenie dynamicznych i interaktywnych dokumentów PDF.

### Często zadawane pytania dotyczące dodawania spisu treści do pliku PDF

#### P: Co to jest Aspose.PDF dla .NET?

Odp.: Aspose.PDF dla .NET to potężna biblioteka, która pozwala programistom efektywnie pracować z plikami PDF w aplikacjach .NET. Zapewnia szeroką gamę funkcji do programowego tworzenia, manipulowania i zarządzania dokumentami PDF.

#### P: Jaki jest cel dodawania spisu treści (TOC) do dokumentu PDF?

O: Spis treści (TOC) zapewnia użytkownikom pomoc w nawigacji, umożliwiając im szybkie przechodzenie do określonych sekcji lub stron dokumentu PDF. Poprawia użyteczność dokumentu i wygodę użytkownika.

#### P: Jak dodać spis treści do dokumentu PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Aby dodać spis treści do dokumentu PDF przy użyciu Aspose.PDF dla .NET, musisz utworzyć nową stronę do przechowywania spisu treści, zdefiniować informacje o spisie treści, a następnie utworzyć elementy spisu treści odpowiadające określonym stronom lub sekcje w dokumencie.

#### P: Czy mogę dostosować wygląd spisu treści?

O: Tak, możesz dostosować wygląd spisu treści, ustawiając różne właściwości elementów spisu treści, takie jak rozmiar i styl czcionki oraz wyrównanie. Aspose.PDF dla .NET zapewnia elastyczność w projektowaniu spisu treści, aby pasował do pożądanego wyglądu i stylu.

#### P: Czy Aspose.PDF dla .NET nadaje się do dodawania zaawansowanych funkcji do dokumentów PDF?

O: Oczywiście, Aspose.PDF dla .NET to bogata w funkcje biblioteka, która umożliwia dodawanie zaawansowanych funkcjonalności do dokumentów PDF, w tym elementów interaktywnych, pól formularzy, podpisów cyfrowych i innych.