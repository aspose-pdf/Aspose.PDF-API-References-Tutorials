---
title: Zmień orientację
linktitle: Zmień orientację
second_title: Aspose.PDF z dokumentacją API .NET
description: Przewodnik krok po kroku dotyczący zmiany orientacji strony pliku PDF za pomocą Aspose.PDF dla .NET. Łatwe do naśladowania i wdrażania w swoich projektach.
type: docs
weight: 10
url: /pl/net/programming-with-pdf-pages/change-orientation/
---
W tym samouczku przeprowadzimy Cię krok po kroku przez proces zmiany orientacji strony dokumentu PDF przy użyciu Aspose.PDF dla .NET. Wyjaśnimy dołączony kod źródłowy C# i udostępnimy kompleksowy przewodnik, który pomoże Ci zrozumieć i wdrożyć tę funkcję we własnych projektach. Pod koniec tego samouczka dowiesz się, jak zmienić orientację strony dokumentów PDF za pomocą Aspose.PDF dla .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Podstawowa znajomość języka programowania C#
- Aspose.PDF dla .NET zainstalowany w Twoim środowisku programistycznym

## Krok 1: Zdefiniuj katalog dokumentów
Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Jest to lokalizacja, w której znajduje się wejściowy plik PDF i gdzie chcesz zapisać zmodyfikowany wyjściowy plik PDF. Zastąp „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument PDF
 Następnie możesz załadować dokument PDF z pliku wejściowego za pomocą`Document` klasa Aspose.PDF. Pamiętaj, aby podać poprawną ścieżkę do pliku PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 3: Zmień orientację strony
Teraz przejrzymy każdą stronę dokumentu i zmienimy jego orientację. Dla każdej strony modyfikujemy wymiary media boxu (`MediaBox`) zamieniając szerokość i wysokość, następnie dostosowujemy współrzędne pola multimedialnego, aby zachować pozycję strony. Na koniec ustawiamy obrót strony na 90 stopni.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Krok 4: Zapisz zmodyfikowany dokument PDF
 Na koniec możesz zapisać zmodyfikowany dokument PDF w pliku wyjściowym za pomocą`Save()` metoda`Document`klasa. Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Przykładowy kod źródłowy dla zmiany orientacji przy użyciu Aspose.PDF dla .NET 

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Musimy przesunąć stronę w górę, aby skompensować zmianę rozmiaru strony
	// (dolna krawędź strony to 0,0, a informacje umieszczane są zazwyczaj od
	// Góra strony. Dlatego przesuwamy krawędź kochanka wyżej na różnicy pomiędzy
	// Stara i nowa wysokość.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Czasami musimy także ustawić CropBox (jeśli był ustawiony w oryginalnym pliku)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Ustawianie kąta obrotu strony
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Zapisz plik wyjściowy
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Wniosek
W tym samouczku dowiedzieliśmy się, jak zmienić orientację strony dokumentu PDF za pomocą Aspose.PDF dla .NET. Wykonując kroki opisane powyżej, możesz łatwo wdrożyć tę funkcjonalność we własnych projektach. Zachęcamy do dalszego zapoznania się z dokumentacją Aspose.PDF, aby odkryć inne przydatne funkcje do pracy z plikami PDF.

### Często zadawane pytania

#### P: Jaki jest cel zmiany orientacji strony w dokumencie PDF?

Odp.: Zmiana orientacji strony w dokumencie PDF umożliwia obrócenie zawartości strony o 90 stopni. Może to być przydatne w scenariuszach, w których oryginalna treść musi zostać wyświetlona lub wydrukowana w innej orientacji, na przykład podczas przełączania z trybu pionowego na poziomy i odwrotnie.

#### P: Czy mogę zmienić orientację określonych stron w dokumencie PDF?

 Odp.: Tak, możesz zmienić orientację określonych stron w dokumencie PDF. W dostarczonym kodzie źródłowym C# plik`foreach` pętla służy do przeglądania każdej strony dokumentu i zmiany jej orientacji. Jeśli chcesz zmienić tylko orientację określonych stron, możesz zmodyfikować pętlę, aby kierować reklamy na te strony na podstawie ich numerów stron lub innych kryteriów.

#### P: Czy zmiana orientacji strony wpływa na układ treści na stronie?

Odpowiedź: Tak, zmiana orientacji strony będzie miała wpływ na układ treści na stronie. Treść zostanie obrócona o 90 stopni, a szerokość i wysokość strony zostaną zamienione. W rezultacie rozmieszczenie i wyrównanie treści na stronie może ulec zmianie.

#### P: Czy mogę obrócić stronę o kąt inny niż 90 stopni?

 Odp.: W dostarczonym kodzie źródłowym C# obrót strony jest ustawiony na 90 stopni za pomocą`page.Rotate = Rotate.on90;` . W razie potrzeby można jednak zmienić kąt obrotu na inną wartość. Możesz na przykład użyć`Rotate.on180` aby obrócić stronę o 180 stopni lub`Rotate.on270` obrócić go o 270 stopni.

#### P: Jak sobie poradzić z treścią strony, która przepełnia się po zmianie orientacji?

Odp.: Podczas zmiany orientacji strony wymiary strony mogą się zmienić, co może spowodować przepełnienie treści. Aby sobie z tym poradzić, może być konieczne dostosowanie układu i formatowania treści na stronie. Możesz użyć funkcji dostępnych w Aspose.PDF dla .NET, takich jak zmiana rozmiaru elementów, dopasowywanie marginesów lub reorganizacja zawartości, aby mieć pewność, że zawartość strony będzie prawidłowo dopasowana po zmianie orientacji.