---
title: Wyodrębnij akapity w pliku PDF
linktitle: Wyodrębnij akapity w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić akapity z pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 160
url: /pl/net/programming-with-text/extract-paragraphs/
---
Ten samouczek przeprowadzi Cię przez proces wyodrębniania akapitów w pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Visual Studio lub inny kompilator C# zainstalowany na Twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać ją z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby ją zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla platformy .NET.

## Krok 2: Importuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić akapity, dodaj na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź linię, która mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i zastąpić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do pliku wejściowego PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 5: Wyodrębnij akapity
 Utwórz instancję`ParagraphAbsorber` klasa i użyj jej`Visit` metoda wyodrębniania akapitów z dokumentu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Krok 6: Przejrzyj akapity
Przejdź przez wyodrębnione akapity, aby uzyskać dostęp do zawartości tekstu. Użyj zagnieżdżonych pętli, aby przejść przez sekcje i wiersze w każdym akapicie.

```csharp
foreach(PageMarkup markup in absorber.PageMarkups)
{
     int i = 1;
     foreach(MarkupSection section in markup.Sections)
     {
         int j = 1;
         foreach(MarkupParagraph paragraph in section.Paragraphs)
         {
             StringBuilder paragraphText = new StringBuilder();
             foreach(List<TextFragment> line in paragraph.Lines)
             {
                 foreach(TextFragment fragment in line)
                 {
                     paragraphText.Append(fragment.Text);
                 }
                 paragraphText. Append("\r\n");
             }
             paragraphText. Append("\r\n");
             Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
             Console.WriteLine(paragraphText.ToString());
             j++;
         }
         i++;
     }
}
```

### Przykładowy kod źródłowy dla funkcji Extract Paragraphs using Aspose.PDF for .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz istniejący plik PDF
Document doc = new Document(dataDir + "input.pdf");
// Utwórz instancję ParagraphAbsorber
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
foreach (PageMarkup markup in absorber.PageMarkups)
{
	int i = 1;
	foreach (MarkupSection section in markup.Sections)
	{
		int j = 1;
		foreach (MarkupParagraph paragraph in section.Paragraphs)
		{
			StringBuilder paragraphText = new StringBuilder();
			foreach (List<TextFragment> line in paragraph.Lines)
			{
				foreach (TextFragment fragment in line)
				{
					paragraphText.Append(fragment.Text);
				}
				paragraphText.Append("\r\n");
			}
			paragraphText.Append("\r\n");
			Console.WriteLine("Paragraph {0} of section {1} on page {2}:", j, i, markup.Number);
			Console.WriteLine(paragraphText.ToString());
			j++;
		}
		i++;
	}
}
```

## Wniosek
Udało Ci się wyodrębnić akapity z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębnione akapity zostały wyświetlone w oknie konsoli.

### Najczęściej zadawane pytania

#### P: Jaki jest cel tego poradnika?

A: Ten samouczek ma na celu przeprowadzenie Cię przez proces wyodrębniania akapitów z pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy C# zawiera praktyczne kroki umożliwiające wykonanie tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

A: W pliku kodu, z którego zamierzasz wyodrębnić akapity, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### P: Jak określić katalog dokumentów?

 A: Zlokalizuj linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 A: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do pliku wejściowego PDF.

#### P: Jak wyodrębnić akapity z dokumentu?

 A: Krok 5 obejmuje utworzenie instancji`ParagraphAbsorber` klasa i jej używanie`Visit` metoda wyodrębniania akapitów z dokumentu PDF.

#### P: W jaki sposób mogę przeglądać wyodrębnione akapity?

A: Krok 6 prowadzi Cię przez pętle przez wyodrębnione akapity. Zagnieżdżone pętle są używane do przechodzenia przez sekcje i wiersze w każdym akapicie, ostatecznie uzyskując dostęp do zawartości tekstu i wyświetlając ją.

#### P: Jakie są najważniejsze wnioski z tego samouczka?

A: Postępując zgodnie z tym samouczkiem, nauczyłeś się, jak wyodrębnić akapity z dokumentu PDF za pomocą Aspose.PDF dla .NET. Wyodrębnione akapity zostały wyświetlone w oknie konsoli, zapewniając Ci cenny wgląd w strukturę zawartości dokumentu.