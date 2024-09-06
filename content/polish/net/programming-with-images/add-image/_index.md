---
title: Dodaj obraz do pliku PDF
linktitle: Dodaj obraz do pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Łatwe dodawanie obrazów do plików PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 10
url: /pl/net/programming-with-images/add-image/
---
Ten przewodnik krok po kroku pokaże Ci, jak dodać obraz do pliku PDF za pomocą Aspose.PDF dla .NET. Upewnij się, że skonfigurowałeś już swoje środowisko i wykonaj poniższe kroki:

## Krok 1: Zdefiniuj katalog dokumentów

Przed rozpoczęciem upewnij się, że ustawiłeś właściwy katalog dla dokumentów. Zastąp`"YOUR DOCUMENT DIRECTORY"` w kodzie podając ścieżkę do katalogu, w którym znajduje się Twój dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument

 W tym kroku otworzymy dokument PDF za pomocą`Document` klasa Aspose.PDF. Użyj`Document` konstruktora i przekazuje ścieżkę do dokumentu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Krok 3: Ustaw współrzędne obrazu

 Ustaw współrzędne obrazu, który chcesz dodać. Zmienne`lowerLeftX`, `lowerLeftY`, `upperRightX` I`upperRightY` reprezentują odpowiednio współrzędne lewego dolnego rogu i prawego górnego rogu obrazu.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Krok 4: Pobierz stronę, na której chcesz dodać obraz

Aby dodać obraz do określonej strony dokumentu PDF, najpierw musimy pobrać tę stronę. W tym przykładzie dodajemy obraz do drugiej strony (indeks 1) dokumentu.

```csharp
Page page = pdfDocument.Pages[1];
```

## Krok 5: Załaduj obraz ze strumienia

 Teraz załadujemy obraz, który chcemy dodać do dokumentu PDF. Ten przykład zakłada, że masz plik obrazu o nazwie`aspose-logo.jpg` w tym samym katalogu co twój dokument. W razie potrzeby zamień nazwę pliku.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Krok 6: Dodaj obraz do zasobów strony

Aby użyć obrazu w dokumencie PDF, musimy dodać go do kolekcji obrazów zasobów strony.

```csharp
page.Resources.Images.Add(imageStream);
```

## Krok 7: Zapisz aktualny stan grafiki

 Przed narysowaniem obrazu musimy zapisać aktualny stan grafiki za pomocą`GSave` operator. Dzięki temu zmiany stanu grafiki można później wycofać.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Krok 8: Utwórz obiekty Rectangle i Matrix

 Teraz utworzymy`Rectangle` obiekt i`Matrix` obiekt. Prostokąt reprezentuje pozycję i rozmiar obrazu, podczas gdy macierz definiuje, jak obraz powinien być umieszczony.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Krok 9: Połącz macierz w celu umieszczenia obrazu

 Aby określić, jak obraz powinien zostać umieszczony w prostokącie, używamy`ConcatenateMatrix` operator. Ten operator definiuje macierz transformacji, która mapuje przestrzeń współrzędnych obrazu na przestrzeń współrzędnych strony.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Krok 10: Narysuj obraz

 W tym kroku narysujemy obraz na stronie za pomocą`Do` operator.`Do`Operator pobiera nazwę obrazu z zasobów i rysuje ją na stronie.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Krok 11: Przywróć stan grafiki

 Po narysowaniu obrazu musimy przywrócić poprzedni stan grafiki za pomocą`GRestore` operator.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Krok 12: Zapisz zaktualizowany dokument

 Na koniec zapiszemy zaktualizowany dokument do nowego pliku. Zaktualizuj`dataDir` zmienna z żądanym katalogiem wyjściowym i nazwą pliku.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Przykładowy kod źródłowy dla funkcji Dodaj obraz za pomocą Aspose.PDF dla .NET 
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
// Pobierz stronę, na której należy dodać obraz
Page page = pdfDocument.Pages[1];
// Załaduj obraz do strumienia
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Dodaj obraz do kolekcji obrazów w zasobach strony
page.Resources.Images.Add(imageStream);
// Użycie operatora GSave: ten operator zapisuje bieżący stan grafiki
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Utwórz obiekty prostokąta i macierzy
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// Korzystanie z operatora ConcatenateMatrix (łączenie macierzy): definiuje sposób umieszczenia obrazu
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Używanie operatora Do: ten operator rysuje obraz
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Używanie operatora GRestore: ten operator przywraca stan grafiki
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Zapisz zaktualizowany dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Wniosek

tym samouczku nauczyliśmy się, jak dodać obraz do dokumentu PDF za pomocą Aspose.PDF dla .NET. Omówiliśmy każdy krok szczegółowo, od otwierania dokumentu do zapisywania zaktualizowanej wersji. Postępując zgodnie z tym przewodnikiem, powinieneś teraz móc osadzać obrazy w plikach PDF programowo za pomocą C# i Aspose.PDF.

### FAQ dotyczące dodawania obrazu do pliku PDF

#### P: Dlaczego miałbym chcieć dodać obraz do dokumentu PDF?

A: Dodanie obrazów do dokumentu PDF może wzbogacić zawartość wizualną, zapewnić dodatkowy kontekst lub uwzględnić w plikach PDF logo i grafiki.

#### P: Czy mogę dodawać obrazy do konkretnych stron w dokumencie PDF?

A: Tak, możesz określić stronę, na której chcesz dodać obraz. W podanym kodzie obraz jest dodawany do drugiej strony dokumentu PDF.

#### P: Jak mogę zmienić położenie i rozmiar dodanego obrazu?

 A: Możesz zmodyfikować`lowerLeftX`, `lowerLeftY`, `upperRightX` , I`upperRightY` zmienne w kodzie umożliwiające ustawienie współrzędnych obrazu oraz kontrolowanie jego rozmiaru i położenia na stronie.

#### P: Jakie formaty obrazów mogę dodać za pomocą tej metody?

A: W podanym przykładzie kodu przyjęto założenie, że ładujesz obraz JPG (`aspose-logo.jpg`). Aspose.PDF dla .NET obsługuje różne formaty obrazów, w tym PNG, BMP, GIF i inne.

#### P: Jak mogę mieć pewność, że dodany obraz zmieści się w określonych współrzędnych?

 A: Pamiętaj o dostosowaniu współrzędnych i rozmiaru`Rectangle` obiekt (`rectangle`) aby dopasować wymiary obrazu i jego pożądane umiejscowienie na stronie.

#### P: Czy mogę dodać wiele obrazów do jednej strony PDF?

O: Tak, możesz dodać wiele obrazów do jednej strony pliku PDF, powtarzając proces dla każdego obrazu i odpowiednio dostosowując współrzędne oraz inne parametry.

####  P: Jak to działa?`GSave` and `GRestore` operator work in the code?

 A: Ten`GSave` operator zapisuje aktualny stan grafiki, umożliwiając wprowadzanie zmian bez wpływu na ogólny kontekst grafiki.`GRestore` Operator przywraca poprzedni stan grafiki po wprowadzeniu zmian.

#### P: Co się stanie, jeśli pliku obrazu nie będzie można znaleźć w podanej ścieżce?

A: Jeśli plik obrazu nie zostanie znaleziony w określonej ścieżce, kod zgłosi wyjątek podczas próby załadowania strumienia obrazu. Upewnij się, że plik obrazu znajduje się w prawidłowym katalogu.

#### P: Czy mogę dodatkowo dostosować rozmieszczenie i wygląd obrazu?

 A: Tak, możesz dostosować wygląd obrazu, modyfikując`Matrix` obiekt i dostosowywanie innych operatorów w kodzie. Zapoznaj się z dokumentacją Aspose.PDF, aby uzyskać informacje o zaawansowanych dostosowaniach.

#### P: Jak mogę sprawdzić, czy obraz został pomyślnie dodany do pliku PDF?

A: Po zastosowaniu dostarczonego kodu w celu dodania obrazu otwórz zmodyfikowany plik PDF i sprawdź, czy obraz jest wyświetlany na określonej stronie w prawidłowym położeniu.

#### P: Czy dodawanie obrazów ma wpływ na oryginalną zawartość dokumentu PDF?

A: Dodawanie obrazów nie wpływa na oryginalną zawartość dokumentu PDF. Ulepsza dokument, dodając elementy wizualne.