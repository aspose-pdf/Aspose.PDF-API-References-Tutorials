---
title: Ustaw obraz jako tło strony w pliku PDF
linktitle: Ustaw obraz jako tło strony w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku, jak ustawić obraz jako tło strony w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 110
url: /pl/net/programming-with-pdf-pages/image-as-background/
---
tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania obrazu jako tła strony przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka będziesz wiedział, jak dodać obraz jako tło strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w Twoim środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany dokument PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz nowy dokument
 Następnie możesz utworzyć nowy obiekt dokumentu za pomocą`Document` klasa.

```csharp
Document doc = new Document();
```

## Krok 3: Dodaj nową stronę do dokumentu
 Teraz możesz dodać nową stronę do obiektu Dokument za pomocą`Add()` metoda`Pages` klasa.

```csharp
Page page = doc.Pages.Add();
```

## Krok 4: Utwórz obiekt Artefakt tła
Następnie możesz utworzyć nowy obiekt BackgroundArtifact, aby ustawić obraz tła.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Krok 5: Dodaj tło do strony
Następnie możesz dodać obiekt BackgroundArtifact do kolekcji artefaktów strony, używając metody`Artifacts` własność`Page` klasa.

```csharp
page. Artifacts. Add(background);
```

## Krok 6: Zapisz dokument PDF
 Na koniec możesz zapisać dokument PDF w pliku za pomocą`Save()` metoda`Document`klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Przykładowy kod źródłowy obrazu jako tła przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt Dokument
Document doc = new Document();
// Dodaj nową stronę do obiektu dokumentu
Page page = doc.Pages.Add();
// Utwórz obiekt artefaktu tła
BackgroundArtifact background = new BackgroundArtifact();
// Określ obraz obiektu artefaktu tła
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Dodaj artefakt tła do kolekcji artefaktów strony
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Zapisz dokument
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić obraz jako tło strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo dodać obraz tła do swoich dokumentów PDF. Aspose.PDF oferuje potężne i elastyczne API do pracy z plikami PDF, w tym dostosowywanie tła strony. Możesz teraz zastosować tę funkcję we własnych projektach, aby tworzyć dokumenty PDF z niestandardowymi obrazami tła

### Często zadawane pytania dotyczące ustawiania obrazu jako tła strony w pliku PDF

#### P: Jak mogę ustawić obraz jako tło strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

Odp.: Aby ustawić obraz jako tło strony w dokumencie PDF przy użyciu Aspose.PDF dla .NET, możesz wykonać następujące kroki:

1. Ustaw katalog dokumentów, określając ścieżkę, w której chcesz zapisać edytowany dokument PDF.
2.  Utwórz nowy obiekt dokumentu za pomocą metody`Document` klasa.
3.  Dodaj nową stronę do obiektu Dokument za pomocą metody`Add()` metoda`Pages` klasa.
4.  Utwórz nowy obiekt BackgroundArtifact, aby ustawić obraz tła. Możesz określić plik obrazu za pomocą`File.OpenRead()` metoda.
5.  Dodaj obiekt BackgroundArtifact do kolekcji artefaktów strony za pomocą metody`Artifacts` własność`Page` klasa.
6.  Zapisz dokument PDF w pliku za pomocą`Save()` metoda`Document` class i określ poprawną ścieżkę i nazwę pliku wyjściowego.

#### P: Czy mogę dodać wiele obrazów tła do różnych stron dokumentu PDF?

O: Tak, możesz dodać wiele obrazów tła do różnych stron dokumentu PDF, powtarzając proces opisany w samouczku dla każdej strony. Po prostu utwórz nowy obiekt BackgroundArtifact z żądanym obrazem dla każdej strony i dodaj go do kolekcji artefaktów odpowiedniej strony.

#### P: Czy mogę zastosować skalowanie lub pozycjonowanie obrazu do obrazu tła na stronie?

 O: Tak, możesz zastosować skalowanie lub pozycjonowanie obrazu tła na stronie, manipulując`background.BackgroundImage` właściwość obiektu BackgroundArtifact. Przed dodaniem elementu BackgroundArtifact do strony można zmodyfikować właściwości obrazu, takie jak szerokość, wysokość i położenie, aby dostosować sposób wyświetlania obrazu jako tła.

#### P: Czy Aspose.PDF dla .NET obsługuje dodawanie obrazów tła do istniejących dokumentów PDF z zawartością?

Odp.: Tak, Aspose.PDF dla .NET umożliwia dodawanie obrazów tła do istniejących dokumentów PDF z zawartością. Możesz załadować istniejący dokument PDF, dodać obraz tła do żądanej strony, a następnie zapisać zaktualizowany dokument w nowym pliku lub zastąpić oryginalny plik.

#### P: Czy mogę używać obrazów w różnych formatach jako tła strony, np. PNG lub BMP?

O: Tak, oprócz formatu JPEG używanego w samouczku jako tła strony możesz używać obrazów w różnych formatach, takich jak PNG lub BMP. Aspose.PDF dla .NET obsługuje szeroką gamę formatów obrazów i możesz użyć dowolnego obsługiwanego formatu obrazu jako tła dla stron PDF.