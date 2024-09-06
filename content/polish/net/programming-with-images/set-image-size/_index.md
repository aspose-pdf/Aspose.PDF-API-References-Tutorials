---
title: Ustaw rozmiar obrazu w pliku PDF
linktitle: Ustaw rozmiar obrazu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku, jak ustawić rozmiar obrazu w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 270
url: /pl/net/programming-with-images/set-image-size/
---
W tym samouczku pokażemy Ci, jak ustawić rozmiar obrazu w pliku PDF za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowany i skonfigurowany program Visual Studio lub inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana. Możesz ją pobrać z oficjalnej strony Aspose.

## Krok 1: Tworzenie dokumentu PDF

Aby rozpocząć, użyj następującego kodu w celu utworzenia nowego dokumentu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Utwórz obiekt dokumentu
Document doc = new Document();

// Dodaj stronę do zbioru stron pliku PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 2: Dodano zdjęcie

Następnie dodamy obraz do strony dokumentu PDF. Użyj następującego kodu:

```csharp
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Ustaw szerokość i wysokość obrazu w punktach
img. FixWidth = 100;
img. FixHeight = 100;

//Ustaw typ obrazu na nieznany (Nieznany)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Ścieżka do pliku źródłowego obrazu
img.File = dataDir + "aspose-logo.jpg";

// Dodaj obraz do kolekcji akapitów strony
page.Paragraphs.Add(img);
```

Pamiętaj o podaniu prawidłowej ścieżki do pliku źródłowego obrazu.

## Krok 3: Ustawianie właściwości strony

Na koniec ustawimy właściwości strony, w tym jej szerokość i wysokość. Użyj następującego kodu:

```csharp
// Ustaw właściwości strony
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Przykładowy kod źródłowy dla Ustaw rozmiar obrazu za pomocą Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz obiekt dokumentu
Document doc = new Document();
// dodaj stronę do zbioru stron pliku PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Utwórz instancję obrazu
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Ustaw szerokość i wysokość obrazu w punktach
img.FixWidth = 100;
img.FixHeight = 100;
// Ustaw typ obrazu jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Ścieżka do pliku źródłowego
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Ustaw właściwości strony
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// zapisz wynikowy plik PDF
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Wniosek

Gratulacje! Udało Ci się ustawić rozmiar obrazu w dokumencie PDF za pomocą Aspose.PDF dla .NET. Teraz możesz zastosować tę metodę do własnych projektów, aby dostosować rozmiar obrazów w plikach PDF.

### FAQ dotyczące ustawiania rozmiaru obrazu w pliku PDF

#### P: Jaki jest cel ustawiania rozmiaru obrazu w dokumencie PDF za pomocą Aspose.PDF dla platformy .NET?

A: Celem ustawienia rozmiaru obrazu w dokumencie PDF jest kontrolowanie wymiarów obrazu podczas dodawania go do pliku PDF. Pozwala to dostosować wygląd i układ obrazów w plikach PDF.

#### P: Jak działa proces ustawiania rozmiaru obrazu w dokumencie PDF?

 A: Proces ten obejmuje tworzenie`Aspose.Pdf.Image` wystąpienie, określając jego szerokość i wysokość za pomocą`FixWidth` I`FixHeight` właściwości, a następnie dodanie obrazu do dokumentu PDF. Dodatkowo możesz ustawić wymiary samej strony, aby pomieścić obraz.

#### P: Czy mogę ustawić rozmiar obrazu jako określony procent wymiarów strony?

A: Dostarczony kod ustawia absolutną szerokość i wysokość obrazu w punktach. Jeśli chcesz ustawić rozmiar obrazu na podstawie procentu wymiarów strony, musisz odpowiednio obliczyć wymiary i odpowiednio dostosować kod.

####  P: Jakie jest znaczenie`FileType` property when adding an image to the PDF document?

 A: Ten`FileType`właściwość określa typ obrazu dodawanego do dokumentu PDF. W podanym kodzie wartość`Unknown` oznacza, że typ obrazu jest nieznany i Aspose.PDF spróbuje ustalić typ obrazu na podstawie rozszerzenia pliku.

#### P: Czy mogę dodać wiele obrazów do jednej strony, używając tej metody?

 O: Tak, możesz dodać wiele obrazów do jednej strony, tworząc wiele`Aspose.Pdf.Image` wystąpienia i dodawanie ich do kolekcji akapitów strony. Upewnij się, że dostosowujesz pozycjonowanie i układ obrazów w razie potrzeby.

#### P: W jaki sposób mogę kontrolować rozmieszczenie i wyrównanie dodawanego obrazu na stronie?

 A: Umiejscowienie i wyrównanie dodanego obrazu można kontrolować, dostosowując współrzędne i układ obrazu za pomocą właściwości, takich jak:`img.Left`, `img.Top`i właściwości formatowania akapitu.

####  P: Jaki jest cel ustawiania właściwości strony za pomocą`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Ustawienie właściwości strony pozwala zdefiniować wymiary samej strony. Zapewnia to, że wymiary strony mieszczą dodany obraz i wszelkie inne treści, które możesz mieć na stronie.

#### P: Czy mogę ustawić różne rozmiary dla różnych obrazów w tym samym dokumencie PDF?

 O: Tak, możesz ustawić różne rozmiary dla różnych obrazów, tworząc oddzielne`Aspose.Pdf.Image` wystąpienia i dostosowywanie`FixWidth`, `FixHeight`i właściwości rozmieszczenia dla każdego obrazu.

#### P: W jaki sposób mogę zintegrować tę metodę z własnymi projektami dotyczącymi ustawiania rozmiarów obrazów w plikach PDF?

A: Aby zintegrować tę metodę ze swoimi projektami, wykonaj opisane kroki i zmodyfikuj kod w razie potrzeby. Możesz użyć tej metody, aby dodać obrazy o określonych rozmiarach do dokumentów PDF w oparciu o wymagania aplikacji.