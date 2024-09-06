---
title: Usuń nieużywane strumienie w pliku PDF
linktitle: Usuń nieużywane strumienie w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak usuwać nieużywane strumienie w plikach PDF za pomocą Aspose.PDF dla .NET. Nasz przewodnik krok po kroku.
type: docs
weight: 270
url: /pl/net/programming-with-document/removeunusedstreams/
---
W tym przykładzie omówimy, jak usunąć nieużywane strumienie w plikach PDF za pomocą Aspose.PDF dla .NET. Przedstawimy przewodnik krok po kroku, jak to zrobić, w tym pełny kod źródłowy z wyjaśnieniami.

## Krok 1: Ścieżka do katalogu dokumentów

Pierwszy wiersz kodu ustawia ścieżkę do katalogu, w którym znajduje się Twój dokument PDF. Upewnij się, że zastąpiłeś „YOUR DOCUMENT DIRECTORY” rzeczywistą ścieżką katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

Kolejny wiersz kodu otwiera dokument PDF przy użyciu biblioteki Aspose.PDF dla .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 3: Ustaw opcję RemoveUnusedStreams

Następnym krokiem jest ustawienie opcji RemoveUnusedStreams na true. Spowoduje to usunięcie wszystkich nieużywanych strumieni z dokumentu PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Krok 4: Zoptymalizuj dokument PDF za pomocą OptimizationOptions

Teraz, gdy ustawiliśmy opcje optymalizacji, możemy zoptymalizować dokument PDF za pomocą poniższej linii kodu.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 5: Zapisz zaktualizowany dokument

Na koniec możemy zapisać zaktualizowany dokument korzystając z metody Save klasy Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Usuń nieużywane strumienie za pomocą Aspose.PDF dla .NET

Poniżej znajduje się przykładowy kod źródłowy służący do usuwania nieużywanych strumieni za pomocą Aspose.PDF dla platformy .NET.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ustaw opcję RemoveUsedStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
// Zoptymalizuj dokument PDF za pomocą OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
```

## Wniosek

 Optymalizacja dokumentów PDF poprzez usuwanie nieużywanych strumieni jest niezbędna do zwiększenia wydajności i zmniejszenia rozmiaru pliku. Aspose.PDF dla .NET upraszcza ten proces, zapewniając wygodną metodę usuwania nieużywanych strumieni za pomocą`OptimizationOptions`. Przewodnik krok po kroku i dostarczony kod źródłowy C# ułatwiają programistom implementację tej funkcji w aplikacjach .NET. Postępując zgodnie z tymi instrukcjami, programiści mogą skutecznie optymalizować swoje pliki PDF i usprawniać ogólne przetwarzanie PDF w swoich projektach .NET.

### FAQ dotyczące usuwania nieużywanych strumieni w pliku PDF

#### P: Czym są nieużywane strumienie w dokumencie PDF?

A: Nieużywane strumienie w dokumencie PDF to części pliku, do których nie odwołuje się ani nie są używane w treści dokumentu. Strumienie te mogą obejmować obrazy, czcionki lub inne zasoby, które nie są już potrzebne, ale nadal istnieją w pliku PDF.

#### P: Jak usuwanie nieużywanych strumieni wpływa korzystnie na dokumenty PDF?

A: Usunięcie nieużywanych strumieni z dokumentu PDF zmniejsza rozmiar pliku, co skutkuje szybszym czasem ładowania i lepszą wydajnością. Pomaga zoptymalizować plik PDF, aby zapewnić lepsze wrażenia użytkownika i wydajne przechowywanie.

#### P: Czy programiści mogą wskazać, które strumienie należy usunąć za pomocą Aspose.PDF dla .NET?

 O: Tak, programiści mogą kontrolować usuwanie nieużywanych strumieni, ustawiając`RemoveUnusedStreams` opcja w`OptimizationOptions`. Daje im to elastyczność wyboru, które strumienie usunąć w oparciu o ich konkretne potrzeby.