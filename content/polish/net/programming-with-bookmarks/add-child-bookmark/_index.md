---
title: Dodaj zakładkę podrzędną w pliku PDF
linktitle: Dodaj zakładkę podrzędną w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością dodawaj zakładki podrzędne do pliku PDF, aby przeglądać je lepiej zorganizowane dzięki Aspose.PDF dla .NET.
type: docs
weight: 20
url: /pl/net/programming-with-bookmarks/add-child-bookmark/
---
Dodawanie zakładek podrzędnych do pliku PDF pozwala na bardziej uporządkowaną organizację i nawigację. Dzięki Aspose.PDF dla .NET możesz łatwo dodać podzakładkę, postępując zgodnie z następującym kodem źródłowym:

## Krok 1: Zaimportuj wymagane biblioteki

Zanim zaczniesz, musisz zaimportować niezbędne biblioteki dla swojego projektu C#. Oto niezbędna dyrektywa importowa:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Ustaw ścieżkę do folderu dokumentów

 W tym kroku musisz określić ścieżkę do folderu zawierającego plik PDF, do którego chcesz dodać podzakładkę. Zastępować`"YOUR DOCUMENT DIRECTORY"` następującym kodzie z rzeczywistą ścieżką do folderu dokumentów:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otwórz dokument PDF

Teraz otworzymy dokument PDF, do którego chcemy dodać podzakładkę za pomocą następującego kodu:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Krok 4: Utwórz nadrzędny obiekt zakładki

 W tym kroku utworzymy obiekt nadrzędny zakładki za pomocą`OutlineItemCollection` class i ustaw jej właściwości, takie jak tytuł, atrybut kursywy i atrybut pogrubienia. Oto odpowiedni kod:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Krok 5: Utwórz obiekt podrzędny zakładki

 tym kroku ponownie utworzymy obiekt podzakładki za pomocą`OutlineItemCollection` class i ustaw jej właściwości. Oto odpowiedni kod:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Krok 6: Dodaj zakładkę podrzędną do zakładki nadrzędnej

 Na koniec dodajemy utworzoną podzakładkę do kolekcji podzakładek zakładki nadrzędnej, używając metody`Add` metoda obiektu nadrzędnego. Oto odpowiedni kod:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Krok 7: Dodaj zakładkę nadrzędną do kolekcji zakładek dokumentu

 Na koniec dodajemy zakładkę nadrzędną do kolekcji zakładek dokumentu za pomocą metody`Add` metoda`Outlines` nieruchomość. Oto odpowiedni kod:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Przykładowy kod źródłowy dla Dodaj zakładkę podrzędną przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Utwórz nadrzędny obiekt zakładki
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Utwórz obiekt podrzędny zakładki
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Dodaj zakładkę podrzędną do kolekcji zakładek nadrzędnych
pdfOutline.Add(pdfChildOutline);
// Dodaj zakładkę nadrzędną do kolekcji konspektów dokumentu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Zapisz dane wyjściowe
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Teraz masz przewodnik krok po kroku, jak dodać podzakładkę w Aspose.PDF dla .NET. Możesz użyć tego kodu do organizowania i strukturyzowania zakładek w dokumentach PDF.

Koniecznie zapoznaj się z oficjalną dokumentacją Aspose.PDF, aby uzyskać więcej informacji na temat zaawansowanych funkcji manipulacji zakładkami.

### Często zadawane pytania dotyczące dodawania zakładki podrzędnej w pliku PDF

#### P: Czym są zakładki podrzędne w pliku PDF?

Odp.: Zakładki podrzędne, zwane także zakładkami podrzędnymi, to elementy nawigacyjne w dokumencie PDF, które mają hierarchiczną strukturę w ramach zakładki nadrzędnej. Umożliwiają utworzenie bardziej zorganizowanego i szczegółowego spisu treści dokumentu.

#### P: Jak zaimportować niezbędne biblioteki do mojego projektu C#?

Odp.: Aby zaimportować wymagane biblioteki do projektu C#, możesz użyć następującej dyrektywy importu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Biblioteki te zapewniają niezbędne klasy i funkcje do pracy z dokumentami PDF oraz funkcje interaktywne.

#### P: Jak określić ścieżkę do folderu dokumentów?

 Odp.: W dostarczonym kodzie źródłowym należy go zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do folderu zawierającego plik PDF, z którym chcesz pracować. Dzięki temu kod poprawnie zlokalizuje docelowy plik PDF.

#### P: Czy mogę utworzyć wiele poziomów zakładek podrzędnych?

O: Tak, możesz utworzyć wiele poziomów zakładek podrzędnych, rozszerzając proces opisany w samouczku. Tworząc zakładki nadrzędne z zakładkami podrzędnymi i dalej je zagnieżdżając, możesz stworzyć hierarchiczną strukturę zakładek dla złożonych dokumentów PDF.

####  P: Jaki jest cel`OutlineItemCollection` class?

 O:`OutlineItemCollection` class w Aspose.PDF dla .NET służy do tworzenia i zarządzania konturami, które są w zasadzie zakładkami w dokumencie PDF. Ta klasa umożliwia ustawienie właściwości, takich jak tytuł, styl czcionki i akcje dotyczące zakładek.

#### P: Jak dodać zakładkę podrzędną do zakładki nadrzędnej?

 O: Aby dodać zakładkę podrzędną do zakładki nadrzędnej, utwórz nową`OutlineItemCollection` obiekt dla podzakładki i ustaw jego właściwości. Następnie korzystasz z`Add` metoda zakładki nadrzędnej`OutlineItemCollection` aby dodać podzakładkę do kolekcji rodzica.

#### P: Czy mogę dostosować wygląd zakładek podrzędnych?

O: Tak, podobnie jak w przypadku zakładek nadrzędnych, możesz dostosować wygląd zakładek podrzędnych, ustawiając właściwości, takie jak tytuł, styl czcionki i inne atrybuty. Dzięki temu możesz tworzyć wizualnie wyróżniające się i informacyjne zakładki.

#### P: Czy Aspose.PDF dla .NET jest kompatybilny z innymi językami programowania?

Odp.: Aspose.PDF dla .NET jest specjalnie zaprojektowany dla środowisk C# i .NET. Jednak Aspose oferuje podobne biblioteki dla innych języków programowania, takich jak Java i Android, każda dostosowana do odpowiednich platform.

#### P: W jaki sposób zakładki podrzędne usprawniają nawigację w plikach PDF?

Odp.: Zakładki podrzędne usprawniają nawigację w plikach PDF, zapewniając bardziej uporządkowany i uporządkowany spis treści. Użytkownicy mogą szybko uzyskać dostęp do określonych sekcji dokumentu poprzez hierarchiczną strukturę zakładek.