---
title: Zezwalaj na ponowne wykorzystanie zawartości strony
linktitle: Zezwalaj na ponowne wykorzystanie zawartości strony
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak zoptymalizować pliki PDF, włączając funkcję „Zezwalaj na ponowne użycie zawartości strony” przy użyciu Aspose.PDF dla .NET. Zmniejsz rozmiar pliku i zwiększ wydajność.
type: docs
weight: 50
url: /pl/net/programming-with-document/allowresusepagecontent/
---
tym samouczku wyjaśnimy, jak włączyć funkcję „Zezwalaj na ponowne użycie zawartości strony” przy użyciu Aspose.PDF dla .NET. Ta funkcja optymalizuje dokument PDF poprzez ponowne wykorzystanie zawartości strony, zmniejszenie rozmiaru pliku i poprawę wydajności. Postępuj zgodnie z poniższym przewodnikiem krok po kroku:

## Krok 1: Załaduj dokument PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 2: Ustaw opcjęAllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Krok 3: Zoptymalizuj dokument PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 4: Zapisz zaktualizowany dokument

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Krok 5: Sprawdź zmniejszenie rozmiaru pliku

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Gratulacje! Pomyślnie zezwoliłeś na ponowne wykorzystanie zawartości strony w dokumencie PDF.

### Przykładowy kod źródłowy umożliwiający ponowne wykorzystanie zawartości strony przy użyciu Aspose.PDF dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otwórz dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Ustaw opcjęAllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Zoptymalizuj dokument PDF za pomocą Opcji optymalizacji
pdfDocument.OptimizeResources(optimizeOptions);

// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Teraz możesz skutecznie optymalizować swoje dokumenty PDF, umożliwiając ponowne wykorzystanie zawartości strony.

## Wniosek

tym samouczku wyjaśniliśmy, jak włączyć funkcję „Zezwalaj na ponowne wykorzystanie zawartości strony” przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z dostarczonym przewodnikiem krok po kroku i wykorzystując kod źródłowy C#, możesz skutecznie zoptymalizować dokumenty PDF, umożliwiając ponowne wykorzystanie zawartości strony. Ta optymalizacja skutkuje mniejszymi plikami PDF, co może prowadzić do szybszego ładowania i lepszej wydajności podczas obsługi dużych dokumentów PDF. Aspose.PDF dla .NET zapewnia solidne i przyjazne dla użytkownika rozwiązanie do optymalizacji plików PDF, umożliwiające łatwe tworzenie wydajnych i wysokiej jakości plików PDF.

### Często zadawane pytania

#### P: Jaki jest cel włączenia funkcji „Zezwalaj na ponowne wykorzystanie zawartości strony” w dokumencie PDF?

O: Włączenie funkcji „Zezwalaj na ponowne wykorzystanie zawartości strony” w dokumencie PDF optymalizuje plik poprzez ponowne wykorzystanie zawartości strony, co zmniejsza rozmiar pliku i poprawia ogólną wydajność. Ta optymalizacja skutkuje mniejszymi plikami PDF bez utraty jakości treści.

#### P: Jak działa funkcja „Zezwalaj na ponowne wykorzystanie zawartości strony”?

O: Gdy włączona jest funkcja „Zezwalaj na ponowne wykorzystanie zawartości strony”, identyczne obiekty strony w dokumencie PDF są udostępniane i ponownie wykorzystywane, a nie duplikowane przy każdym wystąpieniu. To udostępnianie zawartości strony znacznie zmniejsza ogólny rozmiar pliku.

#### P: Czy mogę cofnąć optymalizację i przywrócić oryginalny dokument?

O: Nie, po przeprowadzeniu optymalizacji za pomocą opcji „Zezwalaj na ponowne użycie zawartości strony” i zapisaniu dokumentu PDF zmiany są trwałe. Zaleca się wykonanie kopii zapasowej oryginalnego dokumentu przed wykonaniem jakiejkolwiek optymalizacji.

#### P: Czy włączenie tej funkcji wpłynie na wygląd lub zawartość dokumentu PDF?

O: Włączenie funkcji „Zezwalaj na ponowne wykorzystanie zawartości strony” nie ma wpływu na wygląd ani zawartość dokumentu PDF. Optymalizuje jedynie wewnętrzną strukturę pliku, aby zmniejszyć redundancję i zwiększyć wydajność.

#### P: Czy Aspose.PDF dla .NET jest niezawodnym rozwiązaniem do optymalizacji i manipulacji plikami PDF?

O: Tak, Aspose.PDF dla .NET to niezawodna i bogata w funkcje biblioteka do optymalizacji i manipulacji plikami PDF. Oferuje rozbudowane opcje optymalizacji plików PDF, w tym zmniejszanie rozmiaru pliku, usuwanie nieużywanych zasobów i zwiększanie ogólnej wydajności.