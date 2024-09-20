---
title: Przechowuj obraz w kolekcji XImage
linktitle: Przechowuj obraz w kolekcji XImage
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak przechowywać obrazy w kolekcji XImage za pomocą Aspose.PDF dla platformy .NET, korzystając z tego kompletnego przewodnika krok po kroku.
type: docs
weight: 290
url: /pl/net/programming-with-images/store-image-in-ximage-collection/
---
## Wstęp

W dzisiejszej erze cyfrowej obsługa i manipulowanie dokumentami programowo jest niezbędne dla wielu aplikacji. Aspose.PDF dla .NET umożliwia programistom bezproblemową pracę z plikami PDF, ulepszając przepływy pracy i umożliwiając tworzenie dynamicznej zawartości. W tym przewodniku zagłębimy się w proces przechowywania obrazu w kolekcji XImage, kluczowej funkcji, która umożliwia osadzanie wizualizacji bezpośrednio w plikach PDF. Gotowy do wyruszenia w podróż tworzenia oszałamiającej zawartości.

## Wymagania wstępne

Zanim zagłębimy się w kod i procesy, musisz upewnić się, że masz kilka rzeczy na swoim miejscu:

- Środowisko .NET: Powinieneś mieć zainstalowany .NET Framework na swoim komputerze. Wybierz odpowiednią wersję na podstawie wymagań swojego projektu.
- Aspose.PDF dla .NET: Upewnij się, że masz bibliotekę Aspose.PDF. Możesz ją pobrać z[Tutaj](https://releases.aspose.com/pdf/net/) lub zacznij od bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
- Plik obrazu: Potrzebujesz również pliku obrazu (takiego jak JPG lub PNG), który chcesz zapisać w pliku PDF. W tym przykładzie użyjemy pliku o nazwie „aspose-logo.jpg”.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# pomoże Ci płynnie nadążać za językiem.

## Importuj pakiety

Aby rozpocząć korzystanie z Aspose.PDF dla .NET, musisz zaimportować wymagane przestrzenie nazw. Ten krok stanowi podstawę do wykorzystania wszystkich funkcjonalności oferowanych przez bibliotekę.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Operators;
```

Importując te przestrzenie nazw, włączasz różne funkcje w Aspose.PDF, w tym tworzenie dokumentów, przetwarzanie obrazów i inne.

Podzielmy to na mniejsze, łatwiejsze do wykonania kroki, dzięki którym będzie Ci łatwiej je śledzić.

## Krok 1: Skonfiguruj katalog dokumentów

Co musisz zrobić jako pierwsze? Określ, gdzie będą przechowywane Twoje dokumenty. Będziesz chciał skonfigurować zmienną, która będzie zawierać ścieżkę do katalogu dokumentów. To tutaj zostanie zapisany Twój plik PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zastąp rzeczywistym katalogiem dokumentów.
```

## Krok 2: Zainicjuj dokument

Teraz czas na utworzenie nowego dokumentu PDF. W tym kroku Twój PDF nabiera życia. 

```csharp
Aspose.Pdf.Document document = new Document();
```

Tutaj tworzymy nowy obiekt Document, który będzie służył jako nasz obszar roboczy.

## Krok 3: Dodaj nową stronę

Każde arcydzieło potrzebuje płótna, prawda? W naszym przypadku potrzebujemy strony, nad którą będziemy pracować w dokumencie.

```csharp
document.Pages.Add();
Page page = document.Pages[1]; // Pobierz pierwszą stronę.
```

Dodajemy nową stronę do naszego dokumentu. Teraz będziemy działać na tej stronie.

## Krok 4: Załaduj plik obrazu

Następnie musisz załadować obraz do swojego programu. Ten krok jest bardzo podobny do otwierania książki, aby ją przeczytać; musisz uzyskać dostęp do treści, zanim będziesz mógł jej użyć.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
```

Ten wiersz otwiera plik obrazu jako strumień, co pozwala na jego manipulowanie i osadzanie w pliku PDF.

## Krok 5: Dodaj obraz do zasobów strony

Teraz, gdy masz już gotowy obraz, czas dodać go do zasobów strony, mówiąc w zasadzie plikowi PDF: „Hej, mam fajny obraz, o którym chcę, żebyś pamiętał!”.

```csharp
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

 Ten kod wykonuje ciężką pracę polegającą na dodawaniu obrazu do pliku PDF i przypisywaniu go do`XImage` zmienna, do której możemy odwołać się później.

## Krok 6: Przygotuj się do narysowania obrazu

Teraz nadchodzi zabawna część — umieszczenie obrazu na stronie. Będziesz chciał ustawić współrzędne tak, aby obraz był umieszczony dokładnie tam, gdzie chcesz.

```csharp
page.Contents.Add(new GSave());
```

Ta linia zapisuje stan grafiki do późniejszego przywrócenia. To tak, jakby zrobić migawkę tego, jak rzeczy są ustawione, zanim cokolwiek zmienimy.

## Krok 7: Określ położenie i rozmiar obrazu

Teraz zdefiniuj, jak duży i gdzie chcesz umieścić swój obraz:

```csharp
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
```

Ten blok kodu ustala wymiary prostokąta, w którym zmieści się Twój obraz, zapewniając mu w zasadzie miejsce na Twojej stronie.

## Krok 8: Utwórz macierz transformacji 

Aby kontrolować sposób umieszczania obrazu, zdefiniujemy macierz transformacji. Ona rządzi tym, jak obraz pojawia się w współrzędnych docelowych.

```csharp
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

Pomyśl o tym jak o kreśleniu mapy przed wyruszeniem w podróż. Pomaga to ustalić, jak obraz będzie się wyświetlał na stronie.

## Krok 9: Umieść obraz na stronie

Teraz nadszedł czas, aby wskazać plikowi PDF, gdzie ma umieścić ten obraz.

```csharp
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
```

Tutaj dodajemy polecenia do strumienia zawartości pliku PDF, które faktycznie narysują obraz zgodnie z macierzą, którą właśnie ustanowiliśmy.

## Krok 10: Zapisz dokument

Nareszcie możemy zapisać nasze arcydzieło! To jest moment, w którym cała ciężka praca łączy się w namacalny wynik.

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Kazałeś Aspose.PDF zapisać dokument pod podaną nazwą pliku. Po uruchomieniu tego kodu znajdziesz nowo utworzony plik PDF w określonym katalogu, wraz z osadzonym obrazem.

## Wniosek

masz to! Nauczyłeś się, jak używać Aspose.PDF dla .NET, aby punkt po punkcie przechowywać obraz w kolekcji XImage. Czyż nie jest satysfakcjonujące widzieć, jak Twój kod nabiera kształtu i generuje coś użytecznego? Niezależnie od tego, czy tworzysz aplikacje, czy po prostu chcesz zautomatyzować raporty, ten przewodnik stanowi świetny element podstawowy. Pamiętaj, że moc Aspose.PDF może pomóc Ci w wielu zadaniach wykraczających poza to, więc kontynuuj eksplorację!

## Najczęściej zadawane pytania

### Jakie formaty plików graficznych są obsługiwane w programie Aspose.PDF?
Aspose.PDF obsługuje różne formaty obrazów, w tym JPG, PNG, BMP i GIF.

### Czy mogę zmienić rozmiar obrazu podczas dodawania go do pliku PDF?
Tak, możesz zmienić rozmiar obrazu wyświetlanego w pliku PDF, zmieniając współrzędne zdefiniowane w prostokącie.

### Czy potrzebuję licencji, aby używać Aspose.PDF?
 Aspose oferuje bezpłatny okres próbny i różne opcje zakupu. Możesz je znaleźć[Tutaj](https://purchase.aspose.com/buy).

### Gdzie mogę uzyskać pomoc, jeśli wystąpią problemy?
 Możesz zwrócić się o pomoc do społeczności Aspose[Tutaj](https://forum.aspose.com/c/pdf/10).

### Czy istnieje sposób na zastosowanie kompresji obrazów dodanych do pliku PDF?
Tak, dodając obrazy do pliku PDF, możesz określić typ filtra obrazu, aby zastosować metodę kompresji, np. Flate.