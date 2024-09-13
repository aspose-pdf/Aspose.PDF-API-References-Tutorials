---
title: Informacje o obrazie w pliku PDF
linktitle: Informacje o obrazie w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Naucz się wyodrębniać informacje o obrazach z plików PDF za pomocą Aspose.PDF dla .NET dzięki naszemu kompleksowemu przewodnikowi krok po kroku.
type: docs
weight: 160
url: /pl/net/programming-with-images/image-information/
---
## Wstęp

Pliki PDF są obecnie wszędzie — praktycznie każdy dokument zawodowy i osobisty w pewnym momencie trafia do tego formatu. Niezależnie od tego, czy jest to raport, broszura czy e-book, zrozumienie, jak programowo wchodzić w interakcję z tymi plikami, oferuje niezliczone możliwości. Jednym z powszechnych wymagań jest wyodrębnianie informacji o obrazach z plików PDF. W tym przewodniku zagłębimy się w to, jak używać biblioteki Aspose.PDF dla .NET, aby wyodrębnić kluczowe szczegóły dotyczące obrazów osadzonych w dokumencie PDF.

## Wymagania wstępne

Zanim przejdziemy do szczegółów kodowania, musisz spełnić kilka warunków wstępnych:

1. Środowisko programistyczne: Będziesz potrzebować skonfigurowanego środowiska programistycznego .NET. Może to być Visual Studio lub inne IDE zgodne z .NET.
2.  Biblioteka Aspose.PDF: Upewnij się, że masz dostęp do biblioteki Aspose.PDF. Możesz ją pobrać z[Strona internetowa Aspose](https://releases.aspose.com/pdf/net/). 
3. Podstawowa wiedza o języku C#: Znajomość języka C# i koncepcji programowania obiektowego pomoże Ci bez problemu podążać za nauką tego samouczka.
4. Dokument PDF: Przygotuj przykładowy dokument PDF zawierający obrazy, aby móc przetestować swój kod. 

## Importowanie pakietów

Aby rozpocząć korzystanie z biblioteki Aspose.PDF, musisz zaimportować niezbędne przestrzenie nazw do pliku C#. Oto krótki przegląd:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Te przestrzenie nazw zapewnią Ci dostęp do wymaganych klas i metod umożliwiających manipulowanie plikami PDF i wyodrębnianie danych obrazu.

Teraz, gdy wszystko jest już skonfigurowane, czas podzielić to na łatwe do opanowania kroki. Napiszemy program C#, który wczyta dokument PDF, przejdzie przez każdą stronę i wyodrębni wymiary i rozdzielczość każdego obrazu w dokumencie.

## Krok 1: Zainicjuj dokument

 W tym kroku zainicjujemy dokument PDF, używając ścieżki do pliku PDF. Powinieneś zastąpić`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, gdzie znajduje się Twój plik PDF.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Załaduj plik źródłowy PDF
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Tworzymy`Document` obiekt, który ładuje PDF z określonego katalogu. To pozwoli nam pracować z zawartością pliku.

## Krok 2: Ustaw domyślną rozdzielczość i zainicjuj struktury danych

Następnie ustawiamy domyślną rozdzielczość obrazów, co jest przydatne do obliczeń. Przygotujemy również tablicę do przechowywania nazw obrazów i stos do zarządzania stanami graficznymi.

```csharp
// Zdefiniuj domyślną rozdzielczość obrazu
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Zdefiniuj obiekt listy tablicowej, który będzie zawierał nazwy obrazów
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 Ten`defaultResolution` zmienna pomaga nam poprawnie obliczyć rozdzielczość obrazów.`graphicsState`Stos służy do przechowywania bieżącego stanu graficznego dokumentu w przypadku napotkania operatorów transformacji.

## Krok 3: Przetwórz każdego operatora na stronie

Teraz przechodzimy przez wszystkich operatorów na pierwszej stronie dokumentu. To tutaj odbywa się ciężka praca. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Operatorzy procesów...
}
```
Każdy operator w pliku PDF to polecenie, które informuje moduł renderujący, w jaki sposób zarządzać elementami graficznymi, w tym obrazami.

## Krok 4: Obsługa operatorów GSave/GRestore

Wewnątrz pętli będziemy obsługiwać polecenia zapisywania i przywracania grafiki, aby śledzić zmiany wprowadzone w stanie graficznym.

```csharp
if (opSaveState != null) 
{
    // Zapisz poprzedni stan
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Przywróć poprzedni stan
    graphicsState.Pop();
}
```
`GSave` zapisuje aktualny stan graficzny, podczas gdy`GRestore` przywraca ostatnio zapisany stan, umożliwiając cofnięcie wszelkich transformacji podczas przetwarzania obrazów.

## Krok 5: Zarządzaj macierzami transformacji

Następnie zajmujemy się łączeniem macierzy transformacji podczas stosowania transformacji do obrazów.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Gdy stosowana jest macierz transformacji, mnożymy ją przez bieżącą macierz zapisaną w stanie grafiki, dzięki czemu możemy śledzić wszelkie skalowanie lub translację stosowane do obrazu.

## Krok 6: Wyodrębnij informacje o obrazie

Na koniec przetwarzamy operator rysowania obrazów i wyodrębniamy niezbędne informacje, takie jak wymiary i rozdzielczość.

```csharp
else if (opDo != null) 
{
    // Operator Do obsługujący obiekty
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Wyjście informacji
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Tutaj sprawdzamy, czy operator jest odpowiedzialny za rysowanie obrazu. Jeśli tak, pobieramy odpowiadający mu obiekt XImage, obliczamy jego skalowane wymiary i rozdzielczość oraz drukujemy niezbędne informacje.

## Wniosek

Gratulacje! Właśnie stworzyłeś działający przykład wyodrębniania informacji o obrazie z pliku PDF przy użyciu Aspose.PDF dla .NET. Ta możliwość może być niezwykle przydatna dla programistów, którzy muszą analizować lub manipulować dokumentami PDF dla różnych aplikacji, takich jak raportowanie, ekstrakcja danych, a nawet niestandardowe przeglądarki PDF. 


## Najczęściej zadawane pytania

### Czym jest biblioteka Aspose.PDF?
Biblioteka Aspose.PDF to potężne narzędzie do tworzenia, edytowania i konwertowania plików PDF w aplikacjach .NET.

### Czy mogę korzystać z biblioteki bezpłatnie?
 Tak, Aspose oferuje bezpłatną wersję próbną. Możesz ją pobrać[Tutaj](https://releases.aspose.com/).

### Jakie typy formatów obrazów można wyodrębnić?
Biblioteka obsługuje różne formaty obrazów, w tym JPEG, PNG i TIFF, pod warunkiem, że są osadzone w pliku PDF.

### Czy Aspose jest używany w celach komercyjnych?
 Tak, możesz używać produktów Aspose komercyjnie. Aby uzyskać licencję, odwiedź stronę[strona zakupu](https://purchase.aspose.com/buy).

### Jak uzyskać wsparcie dla Aspose?
 Możesz uzyskać dostęp do forum wsparcia[Tutaj](https://forum.aspose.com/c/pdf/10).