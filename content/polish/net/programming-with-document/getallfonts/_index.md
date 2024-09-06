---
title: Pobierz wszystkie czcionki w pliku PDF
linktitle: Pobierz wszystkie czcionki w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak używać Aspose.PDF dla .NET, aby programowo pobrać wszystkie czcionki użyte w pliku PDF, korzystając z tego przewodnika krok po kroku i przykładowego kodu.
type: docs
weight: 160
url: /pl/net/programming-with-document/getallfonts/
---
Aspose.PDF dla .NET to potężna biblioteka, która umożliwia programistom programową pracę z plikiem PDF. Jedną z funkcji, które oferuje, jest możliwość pobrania wszystkich czcionek użytych w pliku PDF. Może to być przydatne, jeśli trzeba programowo analizować lub manipulować czcionkami w pliku PDF.

W tym samouczku omówimy, jak używać Aspose.PDF dla .NET, aby uzyskać wszystkie czcionki używane w dokumencie PDF. Przedstawimy przewodnik krok po kroku, jak to zrobić, wraz z przykładowym kodem źródłowym.

## Krok 1: Utwórz nową aplikację konsolową C#
Aby rozpocząć, utwórz nową aplikację konsoli C# w Visual Studio. Możesz nadać jej dowolną nazwę. Po utworzeniu projektu musisz dodać odwołanie do biblioteki Aspose.PDF dla .NET.

## Krok 2: Importuj przestrzeń nazw Aspose.PDF
Dodaj następujący wiersz kodu na górze pliku C#, aby zaimportować przestrzeń nazw Aspose.PDF:

```csharp
using Aspose.Pdf;
```

## Krok 3: Załaduj dokument PDF
Załaduj dokument PDF, z którego chcesz pobrać czcionki:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Zdobądź wszystkie czcionki
Pobierz wszystkie czcionki użyte w dokumencie PDF:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Krok 5: Wydrukuj wszystkie czcionki
Wydrukuj wszystkie czcionki użyte w dokumencie PDF:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Przykładowy kod źródłowy dla funkcji Pobierz wszystkie czcionki przy użyciu Aspose.PDF dla .NET
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Wniosek
tym samouczku omówiliśmy, jak uzyskać wszystkie czcionki używane w dokumencie PDF za pomocą Aspose.PDF dla .NET. Uzyskanie wszystkich czcionek używanych w dokumencie PDF może być przydatne, jeśli trzeba programowo analizować lub manipulować czcionkami w dokumencie PDF. Aspose.PDF dla .NET zapewnia proste i łatwe w użyciu API do pracy z dokumentami PDF, w tym uzyskiwanie wszystkich czcionek używanych w dokumencie PDF.

### Najczęściej zadawane pytania

#### P: Dlaczego muszę pobrać wszystkie czcionki użyte w dokumencie PDF?

A: Możliwość pobrania wszystkich czcionek użytych w dokumencie PDF może być przydatna, jeśli zachodzi potrzeba programowej analizy lub manipulowania czcionkami w różnych celach, na przykład w celu zamiany lub dostosowania czcionek.

#### P: W jaki sposób mogę pobrać wszystkie czcionki użyte w dokumencie PDF, korzystając z Aspose.PDF dla platformy .NET?

 A: Możesz uzyskać wszystkie czcionki użyte w dokumencie PDF, korzystając z Aspose.PDF dla .NET, wywołując`GetAllFonts` metoda`FontUtilities` Klasa. Ta metoda zwraca tablicę`Aspose.Pdf.Text.Font` obiekty, które reprezentują czcionki używane w dokumencie PDF.

#### P: Czy mogę filtrować czcionki na podstawie określonych kryteriów?

A: Tak, możesz filtrować czcionki na podstawie określonych kryteriów, używając Aspose.PDF dla .NET. Po uzyskaniu wszystkich czcionek możesz programowo analizować czcionki i stosować logikę filtrowania w razie potrzeby.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z różnymi formatami czcionek?

A: Tak, Aspose.PDF dla .NET jest kompatybilny z różnymi formatami czcionek, w tym TrueType, OpenType i Type 1. Może współpracować z różnymi formatami czcionek i obsługiwać je podczas manipulacji dokumentem PDF.