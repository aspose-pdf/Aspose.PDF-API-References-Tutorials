---
title: Dodaj obraz w pliku PDF
linktitle: Dodaj obraz w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Z łatwością dodawaj obraz do pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-images/add-image/
---
Ten przewodnik poprowadzi Cię krok po kroku, jak dodać obraz do pliku PDF przy użyciu Aspose.PDF dla .NET. Upewnij się, że masz już skonfigurowane środowisko i wykonaj poniższe czynności:

## Krok 1: Zdefiniuj katalog dokumentów

 Zanim zaczniesz, upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie ścieżką do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

 tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktor i podaj ścieżkę do dokumentu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Krok 3: Ustaw współrzędne obrazu

 Ustaw współrzędne obrazu, który chcesz dodać. Zmienne`lowerLeftX`, `lowerLeftY`, `upperRightX` I`upperRightY` reprezentują współrzędne odpowiednio lewego dolnego i prawego górnego rogu obrazu.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Krok 4: Uzyskaj stronę, na której powinien zostać dodany obraz

Aby dodać obraz do określonej strony dokumentu PDF, musimy najpierw pobrać tę stronę. W tym przykładzie dodajemy obraz na drugą stronę (indeks 1) dokumentu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Krok 5: Załaduj obraz ze strumienia

 Załadujemy teraz obraz, który chcemy dodać do dokumentu PDF. W tym przykładzie założono, że masz plik obrazu o nazwie`aspose-logo.jpg` w tym samym katalogu co Twój dokument. Jeśli to konieczne, zmień nazwę pliku.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Krok 6: Dodaj obraz do zasobów strony

Aby użyć obrazu w dokumencie PDF, musimy dodać go do kolekcji obrazów zasobów strony.

```csharp
page.Resources.Images.Add(imageStream);
```

## Krok 7: Zapisz aktualny stan grafiki

 Przed narysowaniem obrazu musimy zapisać aktualny stan grafiki za pomocą pliku`GSave` operator. Zapewnia to możliwość późniejszego wycofania zmian w stanie grafiki.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Krok 8: Utwórz obiekty Rectangle i Matrix

 Utworzymy teraz plik`Rectangle` obiekt i a`Matrix`obiekt. Prostokąt reprezentuje położenie i rozmiar obrazu, natomiast matryca określa, w jaki sposób obraz powinien zostać umieszczony.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Krok 9: Połącz macierz w celu umieszczenia obrazu

 Aby określić sposób umieszczenia obrazu w prostokącie, używamy metody`ConcatenateMatrix` operator. Operator ten definiuje macierz transformacji, która odwzorowuje przestrzeń współrzędnych obrazu na przestrzeń współrzędnych strony.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Krok 10: Narysuj obraz

 W tym kroku narysujemy obraz na stronie za pomocą`Do` operator. The`Do` operator pobiera nazwę obrazu z zasobów i rysuje ją na stronie.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Krok 11: Przywróć stan grafiki

 Po narysowaniu obrazu musimy przywrócić poprzedni stan graficzny za pomocą`GRestore` operator.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Krok 12: Zapisz zaktualizowany dokument

 Na koniec zapiszemy zaktualizowany dokument w nowym pliku. Zaktualizuj`dataDir` zmienną z żądanym katalogiem wyjściowym i nazwą pliku.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla Dodaj obraz przy użyciu Aspose.PDF dla .NET 
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otwórz dokument
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Ustaw współrzędne
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//Uzyskaj stronę, na której należy dodać obraz
Page page = pdfDocument.Pages[1];
// Załaduj obraz do strumienia
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Dodaj obraz do kolekcji obrazów w zasobach strony
page.Resources.Images.Add(imageStream);
// Korzystanie z operatora GSave: operator ten zapisuje aktualny stan grafiki
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Twórz obiekty Rectangle i Matrix
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Użycie operatora ConcatenateMatrix (concatenate matrix): określa sposób umieszczenia obrazu
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Użycie operatora Do: ten operator rysuje obraz
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Korzystanie z operatora GRestore: ten operator przywraca stan grafiki
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dodać obraz do dokumentu PDF przy użyciu Aspose.PDF dla .NET. Szczegółowo omówiliśmy każdy krok, od otwarcia dokumentu po zapisanie zaktualizowanej wersji. Postępując zgodnie z tym przewodnikiem, powinno być teraz możliwe programowe osadzanie obrazów w plikach PDF przy użyciu języków C# i Aspose.PDF.

### Często zadawane pytania dotyczące dodawania obrazu w pliku PDF

#### P: Dlaczego miałbym chcieć dodać obraz do dokumentu PDF?

Odp.: Dodawanie obrazów do dokumentu PDF może ulepszyć zawartość wizualną, zapewnić dodatkowy kontekst lub dołączyć logo i grafikę do plików PDF.

#### P: Czy mogę dodawać obrazy do określonych stron dokumentu PDF?

Odp.: Tak, możesz określić stronę, do której chcesz dodać obraz. W dostarczonym kodzie obraz jest dodawany na drugiej stronie dokumentu PDF.

#### P: Jak dostosować położenie i rozmiar dodanego obrazu?

 Odp.: Możesz modyfikować plik`lowerLeftX`, `lowerLeftY`, `upperRightX` , I`upperRightY` zmienne w kodzie umożliwiające ustawienie współrzędnych obrazu oraz kontrolowanie jego rozmiaru i położenia na stronie.

#### P: Jakie typy formatów obrazów mogę dodać za pomocą tej metody?

O: W podanym przykładzie kodu założono, że ładujesz obraz JPG (`aspose-logo.jpg`). Aspose.PDF dla .NET obsługuje różne formaty obrazów, w tym PNG, BMP, GIF i inne.

#### P: Jak mogę się upewnić, że dodany obraz mieści się w określonych współrzędnych?

 Odp.: Pamiętaj, aby dostosować współrzędne i rozmiar pliku`Rectangle` obiekt (`rectangle`), aby dopasować wymiary obrazu i jego pożądane położenie na stronie.

#### P: Czy mogę dodać wiele obrazów do jednej strony PDF?

Odp.: Tak, możesz dodać wiele obrazów do jednej strony PDF, powtarzając proces dla każdego obrazu i odpowiednio dostosowując współrzędne i inne parametry.

####  P: W jaki sposób`GSave` and `GRestore` operator work in the code?

 O:`GSave` operator zapisuje aktualny stan grafiki, umożliwiając dokonanie zmian bez wpływu na ogólny kontekst graficzny. The`GRestore` operator przywraca poprzedni stan grafiki po dokonaniu zmian.

#### P: Co się stanie, jeśli plik obrazu nie zostanie znaleziony w określonej ścieżce?

Odp.: Jeśli plik obrazu nie zostanie znaleziony w określonej ścieżce, kod zgłosi wyjątek podczas próby załadowania strumienia obrazu. Upewnij się, że plik obrazu znajduje się we właściwym katalogu.

#### P: Czy mogę dodatkowo dostosować położenie i wygląd obrazu?

 O: Tak, możesz dostosować wygląd obrazu, modyfikując plik`Matrix`obiektu i dostosowywanie innych operatorów w kodzie. Aby zapoznać się z zaawansowanymi możliwościami dostosowywania, zapoznaj się z dokumentacją Aspose.PDF.

#### P: Jak mogę sprawdzić, czy obraz został pomyślnie dodany do pliku PDF?

Odp.: Po zastosowaniu dostarczonego kodu w celu dodania obrazu otwórz zmodyfikowany plik PDF i sprawdź, czy obraz jest wyświetlany na określonej stronie we właściwym miejscu.

#### P: Czy dodanie obrazów wpływa na oryginalną zawartość dokumentu PDF?

Odp.: Dodawanie obrazów nie ma wpływu na oryginalną zawartość dokumentu PDF. Uatrakcyjnia dokument poprzez dodanie elementów wizualnych.