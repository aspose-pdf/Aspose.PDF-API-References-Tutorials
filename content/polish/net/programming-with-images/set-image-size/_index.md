---
title: Ustaw rozmiar obrazu w pliku PDF
linktitle: Ustaw rozmiar obrazu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku, jak ustawić rozmiar obrazu w pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 270
url: /pl/net/programming-with-images/set-image-size/
---
W tym samouczku przeprowadzimy Cię przez proces ustawiania rozmiaru obrazu w pliku PDF przy użyciu Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowany i skonfigurowany program Visual Studio lub dowolne inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Można go pobrać z oficjalnej strony Aspose.

## Krok 1: Utworzenie dokumentu PDF

Aby rozpocząć, użyj poniższego kodu i utwórz nowy dokument PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Utwórz instancję obiektu dokumentu
Document doc = new Document();

// Dodaj stronę do kolekcji stron pliku PDF
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

// Ustaw typ obrazu na nieznany (Nieznany)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Ścieżka do pliku źródłowego obrazu
img.File = dataDir + "aspose-logo.jpg";

// Dodaj obraz do kolekcji akapitów strony
page.Paragraphs.Add(img);
```

Pamiętaj, aby podać poprawną ścieżkę do pliku źródłowego obrazu.

## Krok 3: Ustawianie właściwości strony

Na koniec ustawimy właściwości strony, w tym jej szerokość i wysokość. Użyj następującego kodu:

```csharp
// Ustaw właściwości strony
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Przykładowy kod źródłowy dla Ustaw rozmiar obrazu przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utwórz instancję obiektu dokumentu
Document doc = new Document();
// dodaj stronę do kolekcji stron pliku PDF
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

Gratulacje! Pomyślnie ustawiłeś rozmiar obrazu w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Możesz teraz zastosować tę metodę do własnych projektów, aby dostosować rozmiar obrazów w plikach PDF.

### Często zadawane pytania dotyczące ustawiania rozmiaru obrazu w pliku PDF

#### P: Jaki jest cel ustawiania rozmiaru obrazu w dokumencie PDF przy użyciu Aspose.PDF dla .NET?

O: Celem ustawienia rozmiaru obrazu w dokumencie PDF jest kontrolowanie wymiarów obrazu po dodaniu do pliku PDF. Umożliwia to dostosowanie wyglądu i układu obrazów w plikach PDF.

#### P: Jak działa proces ustawiania rozmiaru obrazu w dokumencie PDF?

 Odp.: Proces obejmuje utworzenie pliku`Aspose.Pdf.Image` instancję, określając jej szerokość i wysokość za pomocą metody`FixWidth` I`FixHeight` właściwości, a następnie dodanie obrazu do dokumentu PDF. Dodatkowo możesz ustawić wymiary samej strony, aby zmieścić obraz.

#### P: Czy mogę ustawić rozmiar obrazu na określony procent wymiarów strony?

Odp.: Dostarczony kod określa bezwzględną szerokość i wysokość obrazu w punktach. Jeśli chcesz ustawić rozmiar obrazu na podstawie procentu wymiarów strony, musisz odpowiednio obliczyć wymiary i odpowiednio dostosować kod.

####  P: Jakie jest znaczenie`FileType` property when adding an image to the PDF document?

 O:`FileType`Właściwość określa typ obrazu dodawanego do dokumentu PDF. W podanym kodzie wartość`Unknown` wskazuje, że typ obrazu jest nieznany, a Aspose.PDF spróbuje określić typ obrazu na podstawie rozszerzenia pliku.

#### P: Czy przy użyciu tej metody mogę dodać wiele obrazów do jednej strony?

 Odp.: Tak, możesz dodać wiele obrazów do jednej strony, tworząc wiele obrazów`Aspose.Pdf.Image` wystąpienia i dodanie ich do zbioru akapitów strony. W razie potrzeby dostosuj położenie i układ obrazów.

#### P: Jak mogę kontrolować położenie i wyrównanie dodanego obrazu na stronie?

 O: Położenie i wyrównanie dodanego obrazu można kontrolować, dostosowując współrzędne i układ obrazu za pomocą właściwości takich jak`img.Left`, `img.Top`i właściwości formatowania akapitu.

####  P: Jaki jest cel ustawiania właściwości strony za pomocą`page.PageInfo.Width` and `page.PageInfo.Height`?

O: Ustawienie właściwości strony umożliwia zdefiniowanie wymiarów samej strony. Gwarantuje to, że wymiary strony pomieszczą dodany obraz i całą inną zawartość, którą możesz umieścić na stronie.

#### P: Czy mogę ustawić różne rozmiary dla różnych obrazów w tym samym dokumencie PDF?

 Odp.: Tak, możesz ustawić różne rozmiary dla różnych obrazów, tworząc osobne`Aspose.Pdf.Image` instancji i dostosowywanie`FixWidth`, `FixHeight`i właściwości rozmieszczenia każdego obrazu.

#### P: Jak mogę zintegrować tę metodę z moimi własnymi projektami, aby ustawić rozmiary obrazów w plikach PDF?

O: Aby zintegrować tę metodę ze swoimi projektami, wykonaj opisane kroki i zmodyfikuj kod zgodnie z potrzebami. Możesz użyć tej metody, aby dodać obrazy o określonych rozmiarach do dokumentów PDF w zależności od wymagań aplikacji.