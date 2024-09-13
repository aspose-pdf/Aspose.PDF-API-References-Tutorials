---
title: Niestandardowe tabulatory w pliku PDF
linktitle: Niestandardowe tabulatory w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak tworzyć niestandardowe tabulatory w plikach PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 120
url: /pl/net/programming-with-text/custom-tab-stops/
---

Ten samouczek przeprowadzi Cię przez proces tworzenia niestandardowych tabulatorów w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
pliku kodu, w którym chcesz utworzyć niestandardowe tabulatory, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Utwórz nową instancję dokumentu
 Utwórz nową instancję`Document` obiekt dodając następujący wiersz kodu:

```csharp
Document _pdfdocument = new Document();
```

## Krok 5: Dodaj stronę do dokumentu
 Dodaj nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja. W podanym kodzie nowa strona jest przypisana do zmiennej`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Krok 6: Utwórz niestandardowe tabulatory
 Utwórz`TabStops` obiekt i dodaj do niego niestandardowe tabulatory. Ustaw typ wyrównania i typ linii odniesienia dla każdego tabulatora.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Krok 7: Utwórz fragmenty tekstu z tabulatorami
 Tworzyć`TextFragment` obiektów i przekaż im niestandardowe tabulatory. Użyj znaków specjalnych`#$TAB` do wskazania tabulatorów w tekście.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Krok 8: Zapisz dokument PDF
 Zapisz dokument PDF za pomocą`Save` metoda`Document` obiekt.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Przykładowy kod źródłowy dla niestandardowych tabulatorów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Wniosek
Udało Ci się utworzyć dokument PDF z niestandardowymi tabulatorami przy użyciu Aspose.PDF dla .NET. Wynikowy plik PDF można teraz znaleźć w określonej ścieżce pliku wyjściowego.

### Najczęściej zadawane pytania

#### P: Na czym skupia się ten samouczek?

A: Ten samouczek koncentruje się na przeprowadzeniu Cię przez proces tworzenia niestandardowych tabulatorów w pliku PDF przy użyciu biblioteki Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki, aby to osiągnąć.

#### P: Jakie przestrzenie nazw powinienem zaimportować na potrzeby tego samouczka?

A: W pliku kodu, w którym chcesz utworzyć niestandardowe tabulatory, zaimportuj następujące przestrzenie nazw na początku pliku:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### P: Jak określić katalog dokumentów?

 A: W kodzie znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak utworzyć nową instancję dokumentu?

 A: W kroku 4 utworzysz nową instancję`Document` obiekt używając dostarczonego kodu.

#### P: Jak dodać stronę do dokumentu?

 A: W kroku 5 dodasz nową stronę do dokumentu za pomocą`Add` metoda`Pages` kolekcja.

#### P: Jak utworzyć niestandardowe tabulatory?

 A: W kroku 6 utworzysz`TabStops` obiekt i dodać do niego niestandardowe tabulatory. Ustawisz również wyrównanie i typy linii odniesienia dla każdego tabulatora.

#### P: Jak tworzyć fragmenty tekstu z tabulatorami?

 A: W kroku 7 utworzysz`TextFragment` obiekty i przekaż im niestandardowe tabulatory. Użyjesz znaków specjalnych`#$TAB` do wskazania tabulatorów w tekście.

#### P: Jak zapisać dokument PDF?

 A: W kroku 8 zapiszesz dokument PDF za pomocą`Save` metoda`Document` obiekt.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak utworzyć dokument PDF z niestandardowymi tabulatorami przy użyciu Aspose.PDF dla .NET. Może to być przydatne do organizowania i wyrównywania tekstu w sposób uporządkowany.