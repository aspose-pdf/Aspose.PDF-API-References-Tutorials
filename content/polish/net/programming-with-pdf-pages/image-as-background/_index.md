---
title: Ustaw obraz jako tło strony w pliku PDF
linktitle: Ustaw obraz jako tło strony w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku, jak ustawić obraz jako tło strony w pliku PDF przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 110
url: /pl/net/programming-with-pdf-pages/image-as-background/
---
tym samouczku przeprowadzimy Cię przez proces krok po kroku, aby ustawić obraz jako tło strony za pomocą Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy Ci kompleksowy przewodnik, który pomoże Ci zrozumieć i zaimplementować tę funkcję we własnych projektach. Na końcu tego samouczka będziesz wiedzieć, jak dodać obraz jako tło strony w dokumencie PDF za pomocą Aspose.PDF dla .NET.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której chcesz zapisać edytowany dokument PDF. Zastąp „TWOJE DOKUMENTY KATALOGU” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz nowy dokument
 Następnie możesz utworzyć nowy obiekt Dokument, używając`Document` klasa.

```csharp
Document doc = new Document();
```

## Krok 3: Dodaj nową stronę do dokumentu
 Teraz możesz dodać nową stronę do obiektu Dokument, używając`Add()` metoda`Pages` klasa.

```csharp
Page page = doc.Pages.Add();
```

## Krok 4: Utwórz obiekt Artefaktu tła
Następnie możesz utworzyć nowy obiekt BackgroundArtifact, aby ustawić obraz tła.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Krok 5: Dodaj tło do strony
Następnie możesz dodać obiekt BackgroundArtifact do kolekcji artefaktów strony, używając`Artifacts` własność`Page` klasa.

```csharp
page. Artifacts. Add(background);
```

## Krok 6: Zapisz dokument PDF
 Na koniec możesz zapisać dokument PDF do pliku, korzystając z`Save()` metoda`Document`klasa. Upewnij się, że podałeś poprawną ścieżkę i nazwę pliku.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Przykładowy kod źródłowy dla Obrazu jako tła przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz nowy obiekt Dokument
Document doc = new Document();
// Dodaj nową stronę do obiektu dokumentu
Page page = doc.Pages.Add();
// Utwórz obiekt Artefakt tła
BackgroundArtifact background = new BackgroundArtifact();
// Określ obraz dla obiektu backgroundartifact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Dodaj backgroundartifact do kolekcji artefaktów strony
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Zapisz dokument
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić obraz jako tło strony w dokumencie PDF za pomocą Aspose.PDF dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz łatwo dodać obraz tła do swoich dokumentów PDF. Aspose.PDF oferuje potężne i elastyczne API do pracy z plikami PDF, w tym dostosowywanie tła strony. Teraz możesz zastosować tę funkcję we własnych projektach, aby tworzyć dokumenty PDF z niestandardowymi obrazami tła

### FAQ dotyczące ustawiania obrazu jako tła strony w pliku PDF

#### P: W jaki sposób mogę ustawić obraz jako tło strony w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

A: Aby ustawić obraz jako tło strony w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET, wykonaj następujące czynności:

1. Ustaw katalog dokumentu, określając ścieżkę, w której chcesz zapisać edytowany dokument PDF.
2.  Utwórz nowy obiekt Dokument za pomocą`Document` klasa.
3.  Dodaj nową stronę do obiektu Dokument za pomocą`Add()` metoda`Pages` klasa.
4.  Utwórz nowy obiekt BackgroundArtifact, aby ustawić obraz tła. Możesz określić plik obrazu za pomocą`File.OpenRead()` metoda.
5.  Dodaj obiekt BackgroundArtifact do kolekcji artefaktów strony za pomocą`Artifacts` własność`Page` klasa.
6.  Zapisz dokument PDF do pliku za pomocą`Save()` metoda`Document` klasę i podaj prawidłową ścieżkę i nazwę pliku wyjściowego.

#### P: Czy mogę dodać różne obrazy tła do różnych stron dokumentu PDF?

A: Tak, możesz dodać wiele obrazów tła do różnych stron dokumentu PDF, powtarzając proces opisany w samouczku dla każdej strony. Po prostu utwórz nowy obiekt BackgroundArtifact z żądanym obrazem dla każdej strony i dodaj go do kolekcji artefaktów odpowiedniej strony.

#### P: Czy mogę zastosować skalowanie lub pozycjonowanie obrazu w tle strony?

 O: Tak, możesz zastosować skalowanie lub pozycjonowanie obrazu tła na stronie, manipulując`background.BackgroundImage` Właściwość obiektu BackgroundArtifact. Przed dodaniem BackgroundArtifact do strony możesz zmodyfikować właściwości obrazu, takie jak szerokość, wysokość i położenie, aby dostosować sposób wyświetlania obrazu jako tła.

#### P: Czy Aspose.PDF dla platformy .NET obsługuje dodawanie obrazów tła do istniejących dokumentów PDF z treścią?

A: Tak, Aspose.PDF dla .NET pozwala dodawać obrazy tła do istniejących dokumentów PDF z treścią. Możesz załadować istniejący dokument PDF, dodać obraz tła do żądanej strony, a następnie zapisać zaktualizowany dokument do nowego pliku lub nadpisać oryginalny plik.

#### P: Czy mogę używać obrazów w różnych formatach jako tła strony, np. PNG lub BMP?

A: Tak, możesz używać obrazów w różnych formatach jako tła strony, takich jak PNG lub BMP, oprócz formatu JPEG używanego w samouczku. Aspose.PDF dla .NET obsługuje szeroki zakres formatów obrazów i możesz używać dowolnego obsługiwanego formatu obrazu jako tła stron PDF.