---
title: Wyodrębnij akapity z pliku PDF
linktitle: Wyodrębnij akapity z pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić akapity z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 160
url: /pl/net/programming-with-text/extract-paragraphs/
---
Ten samouczek poprowadzi Cię przez proces wyodrębniania akapitów z pliku PDF przy użyciu Aspose.PDF dla .NET. Dostarczony kod źródłowy języka C# demonstruje niezbędne kroki.

## Wymagania
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Visual Studio lub dowolny inny kompilator C# zainstalowany na twoim komputerze.
- Aspose.PDF dla biblioteki .NET. Możesz pobrać go z oficjalnej strony Aspose lub użyć menedżera pakietów, takiego jak NuGet, aby go zainstalować.

## Krok 1: Skonfiguruj projekt
1. Utwórz nowy projekt C# w preferowanym środowisku programistycznym.
2. Dodaj odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Zaimportuj wymagane przestrzenie nazw
W pliku kodu, z którego chcesz wyodrębnić akapity, dodaj następujące dyrektywy using na górze pliku:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

## Krok 3: Ustaw katalog dokumentów
 W kodzie znajdź wiersz, który mówi`string dataDir = "YOUR DOCUMENT DIRECTORY";` i wymienić`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do katalogu, w którym przechowywane są Twoje dokumenty.

## Krok 4: Otwórz dokument PDF
 Otwórz istniejący dokument PDF za pomocą`Document`konstruktora i przekazując ścieżkę do wejściowego pliku PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 5: Wyodrębnij akapity
 Utwórz instancję`ParagraphAbsorber` klasę i użyj jej`Visit` metoda wyodrębniania akapitów z dokumentu.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
```

## Krok 6: Iteruj po akapitach
Przejdź w pętli wyodrębnione akapity, aby uzyskać dostęp do zawartości tekstu. Użyj zagnieżdżonych pętli, aby przechodzić przez sekcje i linie w każdym akapicie.

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

### Przykładowy kod źródłowy dla wyodrębnienia akapitów przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Otwórz istniejący plik PDF
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
Pomyślnie wyodrębniłeś akapity z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębnione akapity zostały wyświetlone w oknie konsoli.

### Często zadawane pytania

#### P: Jaki jest cel tego samouczka?

Odp.: Ten samouczek ma na celu poprowadzić Cię przez proces wyodrębniania akapitów z pliku PDF przy użyciu Aspose.PDF dla .NET. Towarzyszący kod źródłowy języka C# zawiera praktyczne kroki umożliwiające osiągnięcie tego zadania.

#### P: Jakie przestrzenie nazw powinienem zaimportować?

O: W pliku kodu, z którego chcesz wyodrębnić akapity, umieść na początku pliku następujące dyrektywy using:

```csharp
using Aspose.Pdf;
using System;
using System.Text;
```

#### P: Jak określić katalog dokumentów?

 O: Znajdź linię`string dataDir = "YOUR DOCUMENT DIRECTORY";` w kodzie i zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

#### P: Jak otworzyć istniejący dokument PDF?

 Odp.: W kroku 4 otworzysz istniejący dokument PDF za pomocą`Document` konstruktora i podając ścieżkę do wejściowego pliku PDF.

#### P: Jak wyodrębnić akapity z dokumentu?

 O: Krok 5 polega na utworzeniu instancji pliku`ParagraphAbsorber` klasę i używanie jej`Visit` metoda wyodrębniania akapitów z dokumentu PDF.

#### P: Jak iterować po wyodrębnionych akapitach?

O: Krok 6 poprowadzi Cię przez przeglądanie wyodrębnionych akapitów. Zagnieżdżone pętle służą do przechodzenia przez sekcje i linie każdego akapitu, ostatecznie uzyskując dostęp i wyświetlając zawartość tekstu.

#### P: Jaki jest najważniejszy wniosek z tego samouczka?

Odp.: Wykonując ten samouczek, nauczyłeś się wyodrębniać akapity z dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyodrębnione akapity zostały wyświetlone w oknie konsoli, zapewniając cenny wgląd w strukturę treści dokumentu.