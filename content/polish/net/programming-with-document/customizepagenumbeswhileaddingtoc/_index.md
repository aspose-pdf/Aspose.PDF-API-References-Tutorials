---
title: Dostosuj numery stron podczas dodawania spisu treści
linktitle: Dostosuj numery stron podczas dodawania spisu treści
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak dostosować numery stron podczas dodawania spisu treści (TOC) przy użyciu Aspose.PDF dla .NET, korzystając z tego przewodnika krok po kroku i przykładowego kodu.
type: docs
weight: 100
url: /pl/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
W tym samouczku przyjrzymy się, jak dostosować numery stron podczas dodawania spisu treści (TOC) przy użyciu Aspose.PDF dla .NET. Zapewnimy wskazówki krok po kroku wraz z przykładem kodu, które pomogą Ci to osiągnąć.

## Krok 1: Ładowanie istniejącego pliku PDF

Najpierw musimy załadować istniejący plik PDF. W tym samouczku użyjemy pliku „42824.pdf” znajdującego się w katalogu „TWOJ KATALOG DOKUMENTÓW”. Zastąp tę ścieżkę katalogu rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Krok 2: Dodanie strony spisu treści

 Następnie musimy dodać nową stronę na początku dokumentu, która będzie służyć jako strona spisu treści. Możemy to osiągnąć za pomocą`Insert()` metoda`Pages` zbiór`Document` obiekt.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Krok 3: Tworzenie obiektu TOC

 Aby utworzyć obiekt TOC, musimy najpierw utworzyć obiekt`TocInfo` obiekt i ustawić jego właściwości. W tym samouczku ustawimy tytuł spisu treści na „Spis treści”, a przedrostek numeru strony na „P”.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Krok 4: Tworzenie wpisów TOC

Aby utworzyć wpisy w spisie treści, musimy przejść przez wszystkie strony dokumentu, z wyjątkiem strony spisu treści, i utworzyć obiekt nagłówka dla każdej strony. Następnie możemy dodać obiekt nagłówka do strony spisu treści i określić jego stronę docelową.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Utwórz obiekt nagłówka
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Określ stronę docelową dla obiektu nagłówka
    heading2.DestinationPage = doc.Pages[i + 1];
    // Strona docelowa
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Współrzędna miejsca docelowego
    segment2.Text = "Page " + i.ToString();
    // Dodaj nagłówek do strony zawierającej spis treści
    tocPage.Paragraphs.Add(heading2);
}
```

## Krok 5: Zapisanie zaktualizowanego dokumentu

Na koniec musimy zapisać zaktualizowany dokument w nowym pliku. Możemy to osiągnąć za pomocą`Save()` metoda`Document` obiekt.

```csharp
doc.Save(outFile);
```

### Przykładowy kod źródłowy do dostosowywania numeracji stron podczas dodawania spisu treści przy użyciu Aspose.PDF dla .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Załaduj istniejące pliki PDF
Document doc = new Document(inFile);
// Uzyskaj dostęp do pierwszej strony pliku PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Utwórz obiekt reprezentujący informacje o spisie treści
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Ustaw tytuł spisu treści
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Utwórz obiekt nagłówka
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Określ stronę docelową dla obiektu nagłówka
	heading2.DestinationPage = doc.Pages[i + 1];
	// Strona docelowa
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Współrzędna miejsca docelowego
	segment2.Text = "Page " + i.ToString();
	// Dodaj nagłówek do strony zawierającej spis treści
	tocPage.Paragraphs.Add(heading2);
}

// Zapisz zaktualizowany dokument
doc.Save(outFile);
```

## Wniosek

W tym samouczku przedstawiliśmy szczegółowe wskazówki dotyczące dostosowywania numerów stron podczas dodawania spisu treści przy użyciu Aspose.PDF dla .NET. Udostępniliśmy także przykładowy kod, którego możesz użyć jako odniesienia podczas implementowania tej funkcji w swoim

### Często zadawane pytania

#### P: Co to jest spis treści (TOC) w dokumencie PDF?

O: Spis treści (TOC) w dokumencie PDF to pomoc w nawigacji, która zapewnia uporządkowaną listę sekcji lub rozdziałów dokumentu wraz z odpowiadającymi im numerami stron. Umożliwia czytelnikom szybkie nawigowanie do określonych sekcji dokumentu.

#### P: Dlaczego miałbym chcieć dostosować numery stron w spisie treści?

Odp.: Dostosowywanie numerów stron w spisie treści może być przydatne, jeśli chcesz użyć określonego formatu numeracji stron lub dołączyć dodatkowe informacje wraz z numerami stron. Pozwala stworzyć bardziej spersonalizowany i informacyjny spis treści.

#### P: Czy mogę umieścić w spisie treści hiperłącza prowadzące do określonych sekcji lub stron dokumentu PDF?

Odp.: Tak, Aspose.PDF dla .NET umożliwia tworzenie hiperłączy w spisie treści, które prowadzą do określonych sekcji lub stron dokumentu PDF. Zwiększa to interaktywność i nawigację w dokumencie PDF.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny ze standardami PDF/A?

O: Tak, Aspose.PDF dla .NET obsługuje standardy PDF/A, w tym PDF/A-1, PDF/A-2 i PDF/A-3. Umożliwia tworzenie dokumentów PDF spełniających wymogi dotyczące archiwizacji i długoterminowego przechowywania.

#### P: Czy mogę dodać więcej formatowania do wpisów spisu treści, np. style czcionek lub kolory?

Odp.: Tak, możesz dodać dodatkowe formatowanie do wpisów spisu treści, takie jak style czcionek, kolory i rozmiary czcionek, używając Aspose.PDF dla .NET. Dzięki temu możesz dostosować wygląd spisu treści do swoich wymagań.
