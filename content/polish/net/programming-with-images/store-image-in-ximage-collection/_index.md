---
title: Przechowuj obraz w kolekcji XImage
linktitle: Przechowuj obraz w kolekcji XImage
second_title: Aspose.PDF dla .NET API Reference
description: Instrukcja krok po kroku dotycząca przechowywania obrazu w kolekcji XImage przy użyciu Aspose.PDF dla platformy .NET.
type: docs
weight: 290
url: /pl/net/programming-with-images/store-image-in-ximage-collection/
---
W tym samouczku pokażemy Ci, jak przechowywać obraz w kolekcji XImage za pomocą Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowany i skonfigurowany program Visual Studio lub inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.PDF dla .NET zainstalowana. Możesz ją pobrać z oficjalnej strony Aspose.

## Krok 1: Inicjalizacja dokumentu PDF

Aby rozpocząć, użyj następującego kodu w celu zainicjowania nowego dokumentu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//Zainicjuj dokument
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Krok 2: Dodawanie obrazu do kolekcji XImage

Następnie dodamy obraz do kolekcji XImage dokumentu PDF. Użyj następującego kodu:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Pamiętaj o podaniu prawidłowej ścieżki do pliku źródłowego obrazu.

## Krok 3: Umieszczenie obrazu na stronie

Teraz umieśćmy obraz na stronie dokumentu PDF. Użyj następującego kodu:

```csharp
page. Contents. Add(new GSave());

// Ustaw współrzędne
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// Używając operatora ConcatenateMatrix: zdefiniuj sposób umieszczenia obrazu
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Obraz zostanie umieszczony w określonym miejscu na stronie.

## Krok 4: Zapisywanie dokumentu PDF

Na koniec zapiszemy zaktualizowany dokument PDF. Użyj następującego kodu:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Pamiętaj o podaniu żądanej ścieżki i nazwy pliku dla końcowego dokumentu PDF.

### Przykładowy kod źródłowy dla Store Image In XImage Collection przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zainicjuj dokument
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Ustaw współrzędne
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// Korzystanie z operatora ConcatenateMatrix (łączenie macierzy): definiuje sposób umieszczenia obrazu
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Wniosek

Gratulacje! Udało Ci się zapisać obraz w kolekcji XImage przy użyciu Aspose.PDF dla .NET. Teraz możesz zastosować tę metodę do własnych projektów, aby manipulować obrazami w plikach PDF i personalizować je.

### Najczęściej zadawane pytania

#### P: Jaki jest cel przechowywania obrazu w kolekcji XImage przy użyciu Aspose.PDF dla platformy .NET?

A: Przechowywanie obrazu w kolekcji XImage umożliwia efektywne zarządzanie obrazami i korzystanie z nich w dokumencie PDF. Takie podejście umożliwia manipulowanie obrazami, dostosowywanie ich i personalizowanie przed umieszczeniem ich na określonych stronach.

#### P: Czym przechowywanie obrazu w kolekcji XImage różni się od bezpośredniego umieszczania obrazu na stronie PDF?

A: Przechowywanie obrazu w kolekcji XImage zapewnia bardziej uporządkowany i wielokrotnego użytku sposób zarządzania obrazami. Zamiast bezpośrednio umieszczać obraz na stronie, przechowujesz go w kolekcji i możesz odwoływać się do niego po nazwie, gdy jest to potrzebne, co pozwala na łatwiejsze zarządzanie i modyfikację.

#### P: Czy mogę dodać wiele obrazów do kolekcji XImage w jednym dokumencie PDF?

A: Tak, możesz dodać wiele obrazów do kolekcji XImage w tym samym dokumencie PDF. Każdemu obrazowi przypisana jest unikalna nazwa w kolekcji, która może być używana do odwoływania się do obrazów i umieszczania ich na różnych stronach.

#### P: Jak mogę określić położenie i rozmiar obrazu podczas umieszczania go na stronie PDF z kolekcji XImage?

A: Aby określić pozycję i rozmiar obrazu, musisz zdefiniować prostokąt i transformację macierzową. Prostokąt definiuje granice obrazu, a transformacja macierzowa określa, jak obraz powinien zostać umieszczony w tym prostokącie.

####  P: Jaki jest cel`GSave()` and `GRestore()` operators in the code for placing the image?

 A: Ten`GSave()` I`GRestore()` operatorzy służą do zapisywania i przywracania stanu grafiki strony PDF. Zapewnia to, że operacje wykonywane na stronie, takie jak umieszczanie obrazu, nie mają wpływu na stan strony po umieszczeniu obrazu.

#### P: Czy mogę dokonać dodatkowych modyfikacji lub przekształceń obrazów zapisanych w kolekcji XImage?

A: Tak, możesz stosować różne modyfikacje i transformacje do obrazów przechowywanych w kolekcji XImage. Możesz obracać, skalować, przycinać i wykonywać inne transformacje, korzystając z odpowiednich operacji i technik udostępnianych przez Aspose.PDF dla .NET.

#### P: W jaki sposób mogę zintegrować tę metodę z własnymi projektami, aby przechowywać i umieszczać obrazy w kolekcji XImage dokumentu PDF?

A: Aby zintegrować tę metodę, wykonaj opisane kroki i zmodyfikuj kod, aby spełnić wymagania projektu. Możesz użyć kolekcji XImage do przechowywania i zarządzania obrazami, a następnie umieścić je na określonych stronach, używając określonych współrzędnych i transformacji.

#### P: Czy istnieją jakieś kwestie lub ograniczenia związane z pracą ze zbiorem XImage w Aspose.PDF dla platformy .NET?

A: Podczas gdy kolekcja XImage zapewnia potężny sposób zarządzania obrazami i manipulowania nimi, ważne jest, aby wziąć pod uwagę takie czynniki, jak wykorzystanie pamięci i złożoność operacji wykonywanych na obrazach. Zalecane jest ostrożne zarządzanie kolekcją i efektywne wykorzystanie zasobów.

#### P: Czy mogę ponownie wykorzystywać obrazy zapisane w kolekcji XImage w wielu dokumentach PDF?

A: Kolekcja XImage jest specyficzna dla każdego dokumentu PDF i nie jest przeznaczona do ponownego wykorzystania w wielu dokumentach. Jeśli musisz ponownie wykorzystać obrazy w wielu dokumentach, musisz przechowywać je i zarządzać nimi osobno dla każdego dokumentu.