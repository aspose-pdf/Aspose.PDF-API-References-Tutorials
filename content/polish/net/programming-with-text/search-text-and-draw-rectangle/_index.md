---
title: Wyszukaj tekst i narysuj prostokąt
linktitle: Wyszukaj tekst i narysuj prostokąt
second_title: Aspose.PDF dla .NET API Reference
description: Naucz się wyszukiwać tekst w plikach PDF i wyróżniać go prostokątami za pomocą Aspose.PDF dla .NET! Łatwy samouczek krok po kroku dla ulepszonych umiejętności manipulowania plikami PDF.
type: docs
weight: 460
url: /pl/net/programming-with-text/search-text-and-draw-rectangle/
---
## Wstęp

Chcesz poprawić swoje umiejętności manipulowania plikami PDF? Chcesz dowiedzieć się, jak wyszukiwać określony tekst w plikach PDF i zaznaczać go prostokątem? Trafiłeś na idealny przewodnik! Dzisiaj przeprowadzę Cię przez proces używania Aspose.PDF dla .NET do wyszukiwania tekstu w dokumencie PDF i rysowania wokół niego prostokątów. Ten artykuł zawiera samouczek krok po kroku zaprojektowany z myślą o przejrzystości i użyteczności, dzięki czemu będziesz w stanie śledzić i stosować te techniki w swoich projektach. 

## Wymagania wstępne

Zanim przejdziemy do samouczka, przygotujmy wszystko, co będzie potrzebne, aby zapewnić płynny przepływ pracy:

1. Podstawowa znajomość platformy .NET: Aby efektywnie korzystać z tego samouczka, powinieneś znać programowanie w języku C# i platformę .NET.
   
2. Zainstalowany program Visual Studio: Będziesz potrzebować zintegrowanego środowiska programistycznego (IDE), aby pisać i testować swój kod. Visual Studio Community to świetna opcja i jest bezpłatna.
   
3. Aspose.PDF dla .NET: Musisz mieć zainstalowaną bibliotekę Aspose.PDF w swoim projekcie. Możesz ją pobrać[Tutaj](https://releases.aspose.com/pdf/net/) lub rozważ[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla rozszerzonych funkcji.
   
4.  Przykładowy dokument PDF: Do tego samouczka będziesz potrzebować przykładowego pliku PDF o nazwie`SearchAndGetTextFromAll.pdf` zapisane w katalogu Twojego projektu. 

## Importuj pakiety

Aby rozpocząć, musisz najpierw zaimportować niezbędne pakiety do swojego projektu .NET. Wykonaj następujące kroki:

### Otwórz program Visual Studio

Uruchom program Visual Studio i utwórz nową aplikację konsolową lub użyj istniejącej, w której chcesz zaimplementować funkcje PDF.

### Dodaj Aspose.PDF do swojego projektu

1. Kliknij prawym przyciskiem myszy swój projekt w Eksploratorze rozwiązań.
2. Wybierz „Zarządzaj pakietami NuGet”.
3.  Szukaj`Aspose.PDF` i zainstaluj najnowszą wersję.

W ten sposób tworzysz podwaliny pod wszystkie niesamowite manipulacje plikami PDF, które zamierzasz wykonać.

## Importuj przestrzenie nazw

Na górze pliku programu należy zaimportować odpowiednie przestrzenie nazw z biblioteki Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Dzięki temu dostęp do klas i metod w bibliotece Aspose.PDF podczas wykonywania zadań będzie łatwiejszy.


Teraz, gdy wszystko już skonfigurowałeś, możemy podzielić proces wyszukiwania tekstu w pliku PDF i rysowania wokół niego prostokąta na mniejsze, łatwiejsze do wykonania kroki.

## Krok 1: Ustaw ścieżkę do swojego dokumentu

 Najpierw ustaw ścieżkę do pliku PDF. Upewnij się, że zastąpiłeś`YOUR DOCUMENT DIRECTORY` z rzeczywistą ścieżką, gdzie jesteś`SearchAndGetTextFromAll.pdf` jest przechowywany.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otwórz dokument PDF

 Następnie utwórz instancję`Document` klasa, aby załadować swój plik PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Ta linijka kodu otwiera określony plik PDF, umożliwiając dalsze manipulowanie nim.

## Krok 3: Utwórz absorber tekstu

 Teraz będziesz potrzebować sposobu na wyszukiwanie tekstu w tym dokumencie. W tym celu użyjemy`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Wyrażenie regularne`@"[\S]+"` jest zaprojektowany tak, aby pasował do dowolnego ciągu znaków w pliku PDF, który nie jest spacją. 

## Krok 4: Skonfiguruj opcje wyszukiwania tekstu

Następnie należy skonfigurować opcje wyszukiwania tekstowego:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Tutaj,`true` parametr oznacza, że wyszukiwanie będzie uwzględniać wielkość liter. Możesz ustawić go na`false` jeśli nie chcesz uwzględniać wielkości liter w wyszukiwaniu.

## Krok 5: Zaakceptuj Absorber Tekstu w Dokumencie

 Z twoim`TextFragmentAbsorber` i opcje wyszukiwania gotowe, czas na wczytanie tekstu z dokumentu:

```csharp
document.Pages.Accept(textAbsorber);
```

Ta metoda polega na sprawdzeniu każdej strony dokumentu PDF w celu znalezienia fragmentów tekstu odpowiadających określonemu wzorcowi.

## Krok 6: Utwórz edytor treści PDF

 Aby rysować kształty w dokumencie, będziesz potrzebować`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Ten edytor umożliwia łatwą edycję i modyfikowanie zawartości plików PDF.

## Krok 7: Przejrzyj znalezione fragmenty tekstu

Teraz należy przejść przez znalezione fragmenty tekstu i narysować wokół nich prostokąty:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Ta pętla iteruje po każdym fragmencie tekstu i ich segmentach, wywołując`DrawBox` metoda rysowania prostokątów.

## Krok 8: Zdefiniuj metodę DrawBox

 Musisz zdefiniować`DrawBox` metoda, która będzie obsługiwać logikę rysowania prostokątów. Oto prosta implementacja:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Oblicz wymiary prostokąta na podstawie segmentu tekstu
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Narysuj prostokąt, używając obliczonych wartości
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Ta metoda określa położenie i rozmiar prostokąta na podstawie prostokąta ograniczającego segment i rysuje go za pomocą edytora.

## Krok 9: Zapisz zmodyfikowany dokument

Po narysowaniu prostokątów wokół znalezionego tekstu możesz zapisać zmodyfikowany dokument:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Upewnij się, że nowy plik jest zapisany pod unikalną nazwą, aby uniknąć nadpisania oryginalnego dokumentu.

## Krok 10: Wiadomość potwierdzająca

Na koniec wyświetl na konsoli komunikat potwierdzający, że operacja zakończyła się powodzeniem:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

I masz! Udało Ci się stworzyć skrypt do wyszukiwania tekstu w pliku PDF i zaznaczania go prostokątami.

## Wniosek

Gratulacje! Właśnie odblokowałeś potężną umiejętność, która może znacznie zwiększyć Twoje możliwości manipulacji plikami PDF za pomocą Aspose.PDF dla .NET. Za pomocą zaledwie kilku prostych kroków możesz wyszukać dowolny tekst w dokumencie i wizualnie go wyróżnić, dzięki czemu Twoje dokumenty PDF będą bardziej interaktywne i łatwiejsze w zarządzaniu. Nie wahaj się eksperymentować z różnymi wzorcami wyrażeń regularnych i opcjami kolorów, aby naprawdę dostosować to narzędzie do swoich potrzeb!

## Najczęściej zadawane pytania

### Czym jest Aspose.PDF dla .NET?
Aspose.PDF dla platformy .NET to biblioteka zapewniająca kompleksowy sposób programowego tworzenia, modyfikowania i konwertowania dokumentów PDF.

### Czy mogę używać Aspose.PDF bezpłatnie?
Tak, Aspose oferuje bezpłatną wersję próbną, której możesz użyć do przetestowania funkcjonalności biblioteki. Sprawdź to[Tutaj](https://releases.aspose.com/).

### Jakiego języka programowania muszę użyć w przypadku Aspose.PDF na platformie .NET?
Aspose.PDF dla .NET jest przeznaczony do użytku z językiem C# i innymi językami .NET.

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.PDF?
 Możesz odwiedzić forum pomocy technicznej Aspose, aby uzyskać pomoc dotyczącą dowolnego problemu lub zapytania, które możesz mieć. Znajdź pomoc[Tutaj](https://forum.aspose.com/c/pdf/10).

### Gdzie mogę pobrać Aspose.PDF dla platformy .NET?
 Bibliotekę można pobrać ze strony internetowej Aspose,[Tutaj](https://releases.aspose.com/pdf/net/).