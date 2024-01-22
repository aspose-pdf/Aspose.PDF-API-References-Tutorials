---
title: Dziedzicz powiększenie pliku PDF
linktitle: Dziedzicz powiększenie pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Łatwe dziedziczenie powiększenia zakładek w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 90
url: /pl/net/programming-with-bookmarks/inherit-zoom/
---
Dziedziczenie powiększenia w pliku PDF umożliwia określenie domyślnego poziomu powiększenia zakładek. Dzięki Aspose.PDF dla .NET możesz łatwo odziedziczyć powiększenie, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, z którego chcesz odziedziczyć powiększenie. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otwórz dokument PDF

Teraz otworzymy dokument PDF, w którym chcemy odziedziczyć powiększenie, używając następującego kodu:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Pobierz kolekcję zakładek

 W tym kroku uzyskamy zbiór zakładek lub punktów orientacyjnych dokumentu za pomocą`Outlines` własność`doc` obiekt. Oto odpowiedni kod:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Krok 5: Ustaw poziom powiększenia

 Teraz ustawimy poziom powiększenia, tworząc plik`XYZExplicitDestination` obiekt o określonych współrzędnych x, yiz. Tutaj używamy współrzędnych (100, 100, 0) z powiększeniem 2. Oto odpowiedni kod:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Krok 6: Dodaj poziom powiększenia do zakładek

 W tym kroku dodajemy`XYZExplicitDestination` obiekt jako akcja na zakładkach pliku`item` kolekcja. Oto odpowiedni kod:

```csharp
item. Action = new GoToAction(dest);
```

## Krok 7: Dodaj zaktualizowane zakładki do dokumentu

 Na koniec dodajemy zaktualizowane zakładki do kolekcji zakładek dokumentu za pomocą metody`Add` metoda`doc.Outlines` obiekt. Oto odpowiedni kod:

```csharp
doc. Outlines. Add(item);
```

## Krok 8: Zapisz zaktualizowany plik

 Teraz zapiszmy zaktualizowany plik PDF za pomocą rozszerzenia`Save` metoda`doc` obiekt. Oto odpowiedni kod:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla Inherit Zoom przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document doc = new Document(dataDir + "input.pdf");
// Pobierz kolekcję konturów/zakładek w pliku PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Ustaw poziom powiększenia na 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Dodaj XYZExplicitDestination jako akcję do zarysowania kolekcji plików PDF
item.Action = new GoToAction(dest);
// Dodaj element do kolekcji konturów pliku PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Zapisz dane wyjściowe
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku dotyczący dziedziczenia powiększenia za pomocą Aspose.PDF dla .NET. Możesz użyć tego kodu, aby określić domyślny poziom powiększenia zakładek w dokumentach PDF.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji manipulacji zakładkami.

### Często zadawane pytania dotyczące dziedziczenia powiększenia w pliku PDF

#### P: Co to jest dziedziczenie powiększenia w pliku PDF?

Odp.: Dziedziczenie powiększenia odnosi się do możliwości określenia domyślnego poziomu powiększenia zakładek w dokumencie PDF. Pozwala to na spójną i przyjazną dla użytkownika nawigację podczas interakcji z zakładkami.

#### P: Dlaczego miałbym chcieć dziedziczyć poziomy powiększenia zakładek?

O: Dziedziczenie poziomów powiększenia zapewnia użytkownikom spójny wygląd podczas przeglądania zakładek w dokumencie PDF. Może to być szczególnie przydatne, gdy chcesz zapewnić określony widok dla różnych sekcji dokumentu.

#### P: Jak zaimportować niezbędne biblioteki do mojego projektu C#?

O: Aby zaimportować wymagane biblioteki do projektu C#, dołącz następujące dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Dyrektywy te umożliwiają dostęp do klas i metod potrzebnych do pracy z dokumentami PDF i zakładkami.

#### P: Jak określić ścieżkę do folderu dokumentów?

 Odp.: W dostarczonym kodzie źródłowym zamień`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do folderu zawierającego plik PDF, dla którego chcesz odziedziczyć poziomy powiększenia.

#### P: Jak otworzyć dokument PDF, aby odziedziczyć poziomy powiększenia?

Odp.: Aby otworzyć dokument PDF w celu dziedziczenia poziomów powiększenia, użyj następującego kodu:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Zastępować`"input.pdf"` z rzeczywistą nazwą pliku.

#### P: Jak ustawić poziom powiększenia zakładek?

 Odp.: Aby ustawić poziom powiększenia, utwórz plik`XYZExplicitDestination` obiekt o żądanych współrzędnych i współczynniku powiększenia. Oto przykład:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Ustawia to poziom powiększenia na 2 przy współrzędnych (100, 100).

#### P: Jak dodać poziom powiększenia do zakładek?

 O: Dodaj`XYZExplicitDestination` obiekt jako akcja w kolekcji zakładek:

```csharp
item.Action = new GoToAction(dest);
```

 Gdzie`item` jest`OutlineItemCollection` reprezentujący zakładkę.

#### P: Jak zapisać zaktualizowany plik PDF?

 Odp.: Zapisz zaktualizowany plik PDF za pomocą rozszerzenia`Save` metoda`doc` obiekt:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### P: Czy mogę dostosować poziomy powiększenia dla różnych zakładek?

 Odp.: Tak, możesz dostosować poziomy powiększenia dla różnych zakładek, tworząc ich wiele`XYZExplicitDestination` obiekty o różnych współrzędnych i współczynnikach powiększenia.

#### P: Czy istnieje ograniczenie liczby zakładek, do których mogę zastosować dziedziczenie powiększenia?

Odpowiedź: Zwykle nie ma ścisłego ograniczenia liczby zakładek, do których można zastosować dziedziczenie powiększenia. Jednak bardzo duże dokumenty z nadmierną liczbą zakładek mogą wymagać sprawnego zarządzania pamięcią.

#### P: Jak mogę potwierdzić, że zastosowano dziedziczenie powiększenia?

O: Otwórz wygenerowany plik PDF, aby sprawdzić, czy zakładki przejęły określone poziomy powiększenia.