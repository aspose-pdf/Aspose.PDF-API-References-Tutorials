---
title: Usuń nieużywane strumienie z pliku PDF
linktitle: Usuń nieużywane strumienie z pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak usunąć nieużywane strumienie z plików PDF za pomocą Aspose.PDF dla .NET. Nasz przewodnik krok po kroku.
type: docs
weight: 270
url: /pl/net/programming-with-document/removeunusedstreams/
---
W tym przykładzie omówimy, jak usunąć nieużywane strumienie z plików PDF przy użyciu Aspose.PDF dla .NET. Udostępnimy przewodnik krok po kroku, jak to zrobić, w tym pełny kod źródłowy z objaśnieniami.

## Krok 1: Ścieżka do katalogu dokumentów

Pierwsza linia kodu określa ścieżkę do katalogu, w którym znajduje się dokument PDF. Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką katalogu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

Następna linia kodu otwiera dokument PDF przy użyciu biblioteki Aspose.PDF dla .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 3: Ustaw opcję Usuń nieużywane strumienie

Następnym krokiem jest ustawienie opcji RemoveUnusedStreams na true. Spowoduje to usunięcie wszelkich nieużywanych strumieni z dokumentu PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Krok 4: Zoptymalizuj dokument PDF za pomocą Opcji optymalizacji

Teraz, gdy ustawiliśmy opcje optymalizacji, możemy zoptymalizować dokument PDF za pomocą następującego wiersza kodu.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 5: Zapisz zaktualizowany dokument

Na koniec możemy zapisać zaktualizowany dokument korzystając z metody Save klasy Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla Usuń nieużywane strumienie przy użyciu Aspose.PDF dla .NET

Poniżej znajduje się przykładowy kod źródłowy do usuwania nieużywanych strumieni przy użyciu Aspose.PDF dla .NET.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ustaw opcję UsuńUsedStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
// Zoptymalizuj dokument PDF za pomocą Opcji optymalizacji
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
```

## Wniosek

 Optymalizacja dokumentów PDF poprzez usuwanie nieużywanych strumieni jest niezbędna do zwiększenia wydajności i zmniejszenia rozmiaru pliku. Aspose.PDF dla .NET upraszcza ten proces, zapewniając wygodną metodę usuwania nieużywanych strumieni za pomocą`OptimizationOptions`. Przewodnik krok po kroku i dostarczony kod źródłowy C# ułatwiają programistom wdrażanie tej funkcji w aplikacjach .NET. Postępując zgodnie z tymi instrukcjami, programiści mogą skutecznie optymalizować swoje pliki PDF i usprawniać ogólne przetwarzanie plików PDF w swoich projektach .NET.

### Często zadawane pytania dotyczące usuwania nieużywanych strumieni z pliku PDF

#### P: Czym są nieużywane strumienie w dokumencie PDF?

Odp.: Nieużywane strumienie w dokumencie PDF to części pliku, do których nie ma odniesienia ani które nie są używane w treści dokumentu. Strumienie te mogą zawierać obrazy, czcionki lub inne zasoby, które nie są już potrzebne, ale nadal istnieją w pliku PDF.

#### P: Jaki wpływ na dokumenty PDF ma usunięcie nieużywanych strumieni?

Odp.: Usunięcie nieużywanych strumieni z dokumentu PDF zmniejsza rozmiar pliku, co skutkuje szybszym ładowaniem i lepszą wydajnością. Pomaga w optymalizacji pliku PDF w celu zapewnienia lepszego doświadczenia użytkownika i wydajnego przechowywania.

#### P: Czy programiści mogą określić, które strumienie mają zostać usunięte przy użyciu Aspose.PDF dla .NET?

 O: Tak, programiści mogą kontrolować usuwanie nieużywanych strumieni, ustawiając opcję`RemoveUnusedStreams` opcja w`OptimizationOptions`. Daje im to elastyczność w wyborze strumieni do usunięcia w zależności od ich konkretnych potrzeb.