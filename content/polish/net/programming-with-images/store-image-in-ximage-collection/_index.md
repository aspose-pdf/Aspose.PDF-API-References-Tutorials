---
title: Przechowuj obraz w kolekcji XImage
linktitle: Przechowuj obraz w kolekcji XImage
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący przechowywania obrazu w kolekcji XImage przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 290
url: /pl/net/programming-with-images/store-image-in-ximage-collection/
---
W tym samouczku przeprowadzimy Cię przez proces przechowywania obrazu w kolekcji XImage przy użyciu Aspose.PDF dla .NET. Wykonaj poniższe kroki, aby łatwo wykonać tę operację.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowany i skonfigurowany program Visual Studio lub dowolne inne środowisko programistyczne.
- Podstawowa znajomość języka programowania C#.
- Zainstalowana biblioteka Aspose.PDF dla .NET. Można go pobrać z oficjalnej strony Aspose.

## Krok 1: Inicjalizacja dokumentu PDF

Aby rozpocząć, użyj następującego kodu, aby zainicjować nowy dokument PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//Zainicjuj dokument
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Krok 2: Dodanie obrazu do kolekcji XImage

Następnie dodamy obraz do kolekcji XImage dokumentu PDF. Użyj następującego kodu:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Pamiętaj, aby podać poprawną ścieżkę do pliku źródłowego obrazu.

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

Spowoduje to umieszczenie obrazu pod określonymi współrzędnymi na stronie.

## Krok 4: Zapisywanie dokumentu PDF

Na koniec zapiszemy zaktualizowany dokument PDF. Użyj następującego kodu:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Pamiętaj, aby podać żądaną ścieżkę i nazwę pliku końcowego dokumentu PDF.

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
// Użycie operatora ConcatenateMatrix (concatenate matrix): określa sposób umieszczenia obrazu
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Wniosek

Gratulacje! Pomyślnie zapisałeś obraz w kolekcji XImage przy użyciu Aspose.PDF dla .NET. Możesz teraz zastosować tę metodę do własnych projektów, aby manipulować i personalizować obrazy w plikach PDF.

### Często zadawane pytania

#### P: Jaki jest cel przechowywania obrazu w kolekcji XImage przy użyciu Aspose.PDF dla .NET?

Odp.: Przechowywanie obrazu w kolekcji XImage umożliwia efektywne zarządzanie obrazami i ich używanie w dokumencie PDF. Takie podejście umożliwia manipulowanie, dostosowywanie i personalizowanie obrazów przed umieszczeniem ich na określonych stronach.

#### P: Czym różni się przechowywanie obrazu w kolekcji XImage od bezpośredniego umieszczania obrazu na stronie PDF?

O: Przechowywanie obrazu w kolekcji XImage zapewnia bardziej zorganizowany sposób zarządzania obrazami, który można ponownie wykorzystać. Zamiast bezpośrednio umieszczać obraz na stronie, przechowujesz go w kolekcji i możesz w razie potrzeby odwołać się do niego po nazwie, co pozwala na łatwiejsze zarządzanie i modyfikację.

#### P: Czy mogę dodać wiele obrazów do kolekcji XImage w jednym dokumencie PDF?

Odp.: Tak, możesz dodać wiele obrazów do kolekcji XImage w tym samym dokumencie PDF. Każdemu obrazowi przypisana jest unikalna nazwa w kolekcji, której można używać do odwoływania się do obrazów i umieszczania ich na różnych stronach.

#### P: Jak określić położenie i rozmiar obrazu podczas umieszczania go na stronie PDF z kolekcji XImage?

Odp.: Aby określić położenie i rozmiar obrazu, musisz zdefiniować prostokąt i transformację macierzy. Prostokąt definiuje granice obrazu, a transformacja macierzy określa, w jaki sposób obraz powinien zostać umieszczony w tym prostokącie.

####  P: Jaki jest cel`GSave()` and `GRestore()` operators in the code for placing the image?

 O:`GSave()` I`GRestore()` operatory służą do zapisywania i przywracania stanu graficznego strony PDF. Dzięki temu operacje wykonywane na stronie, takie jak umieszczenie obrazu, nie mają wpływu na stan strony po umieszczeniu obrazu.

#### P: Czy mogę zastosować dodatkowe modyfikacje lub transformacje do obrazów przechowywanych w kolekcji XImage?

O: Tak, możesz zastosować różne modyfikacje i transformacje do obrazów przechowywanych w kolekcji XImage. Możesz obracać, skalować, przycinać i wykonywać inne transformacje, korzystając z odpowiednich operacji i technik dostarczonych przez Aspose.PDF dla .NET.

#### P: Jak mogę zintegrować tę metodę z moimi własnymi projektami, aby przechowywać i umieszczać obrazy w kolekcji XImage dokumentu PDF?

O: Aby zintegrować tę metodę, wykonaj opisane kroki i zmodyfikuj kod tak, aby spełniał wymagania projektu. Możesz używać kolekcji XImage do przechowywania obrazów i zarządzania nimi, a następnie umieszczać je na określonych stronach przy użyciu określonych współrzędnych i przekształceń.

#### P: Czy są jakieś uwagi lub ograniczenia podczas pracy z kolekcją XImage w Aspose.PDF dla .NET?

O: Chociaż kolekcja XImage zapewnia potężny sposób zarządzania obrazami i manipulowania nimi, ważne jest, aby wziąć pod uwagę takie czynniki, jak użycie pamięci i złożoność operacji wykonywanych na obrazach. Zaleca się ostrożne zarządzanie gromadzeniem i efektywne wykorzystanie zasobów.

#### P: Czy mogę ponownie używać obrazów przechowywanych w kolekcji XImage w wielu dokumentach PDF?

Odp.: Kolekcja XImage jest specyficzna dla każdego dokumentu PDF i nie jest przeznaczona do ponownego wykorzystania w wielu dokumentach. Jeśli chcesz ponownie wykorzystać obrazy w wielu dokumentach, musisz je przechowywać i zarządzać nimi oddzielnie dla każdego dokumentu.