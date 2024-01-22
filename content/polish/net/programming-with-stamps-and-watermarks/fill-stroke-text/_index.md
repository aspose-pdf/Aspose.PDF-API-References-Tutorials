---
title: Wypełnij tekst obrysu w pliku PDF
linktitle: Wypełnij tekst obrysu w pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak łatwo wypełnić i obrysować tekst w pliku PDF za pomocą Aspose.PDF dla .NET.
type: docs
weight: 90
url: /pl/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
tym samouczku przeprowadzimy Cię krok po kroku, jak wypełnić i obrysować tekst w pliku PDF za pomocą Aspose.PDF dla .NET. Pokażemy Ci, jak używać dostarczonego kodu źródłowego C#, aby zastosować kolory wypełnienia i konturu do tekstu w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i przywołana w Twoim projekcie.

## Krok 2: Tworzenie obiektu TextState

Pierwszym krokiem jest utworzenie obiektu TextState w celu przekazania zaawansowanych właściwości. Oto jak:

```csharp
// Utwórz obiekt TextState, aby przenieść zaawansowane właściwości
TextState ts = new TextState();

// Ustaw kolor konturu
ts.StrokingColor = Color.Gray;

// Zdefiniuj tryb renderowania tekstu
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Powyższy kod tworzy nowy obiekt TextState i ustawia kolor konturu oraz sposób renderowania tekstu.

## Krok 3: Ładowanie dokumentu PDF

Teraz, gdy obiekt TextState jest już gotowy, możemy załadować dokument PDF, w którym chcemy zastosować wypełnienie i kontur tekstu. Oto jak:

```csharp
// Załaduj dokument PDF jako dane wejściowe
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Powyższy kod ładuje istniejący dokument PDF przy użyciu klasy PdfFileStamp z biblioteki Aspose.PDF.Facades.

## Krok 4: Dodaj wypełnienie i obrys do tekstu

Teraz, gdy dokument PDF jest załadowany, możemy dodać wypełnienie i kontur do tekstu. Oto jak:

```csharp
// Utwórz stempel (Stempel) ze zdefiniowanym tekstem i właściwościami
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Powiąż obiekt TextState
stamp.BindTextState(ts);

// Ustaw początek X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Dodaj pieczątkę do dokumentu
fileStamp.AddStamp(stamp);
```

Powyższy kod tworzy Stamp z określonym tekstem i zdefiniowanymi właściwościami Fill i Stroke.

## Krok 5: Zapisz dokument wyjściowy

Po dodaniu stempla tekstowego możemy zapisać zmodyfikowany dokument PDF. Oto jak:

```csharp
// Zapisz zmodyfikowany dokument
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Powyższy kod zapisuje edytowany dokument PDF we wskazanym katalogu.

### Przykładowy kod źródłowy tekstu obrysu wypełnienia przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt TextState, aby przenieść zaawansowane właściwości
TextState ts = new TextState();

// Ustaw kolor obrysu
ts.StrokingColor = Color.Gray;

// Ustaw tryb renderowania tekstu
ts.RenderingMode = TextRenderingMode.StrokeText;

// Załaduj wejściowy dokument PDF
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Powiąż stan tekstu
stamp.BindTextState(ts);

// Ustaw początek X, Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Dodaj pieczęć
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Wniosek

Gratulacje! Nauczyłeś się, jak wypełniać i obrysowywać tekst w dokumencie PDF przy użyciu Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę, aby dostosować kolory wypełnienia i konturu w dokumentach PDF.

### Często zadawane pytania dotyczące tekstu obrysu wypełnienia w pliku PDF

#### P: Co oznacza wypełnianie i obrysowywanie tekstu w dokumencie PDF i kiedy może być to konieczne?

Odp.: Wypełnianie i obrysowywanie tekstu w dokumencie PDF polega na zastosowaniu kolorów do wnętrza znaków tekstowych (wypełnienie) i obramowań wokół tekstu (kontur). Można to wykorzystać do poprawy wyglądu tekstu, uwypuklenia lub wyróżnienia określonej treści w pliku PDF.

#### P: W jaki sposób dostarczony kod źródłowy C# umożliwia wypełnianie i obrysowywanie tekstu w pliku PDF?

 O: Dostarczony kod źródłowy pokazuje, jak utworzyć plik`TextState` obiekt, aby zdefiniować zaawansowane właściwości tekstu, takie jak kolor konturu i tryb renderowania. Następnie używa Aspose.PDF.Facades do załadowania istniejącego dokumentu PDF, utworzenia stempla zawierającego tekst z określonymi właściwościami wypełnienia i obrysu oraz dodania stempla do dokumentu.

####  P: Jaki jest cel`TextState` object in the code?

 O:`TextState`obiekt służy do definiowania zaawansowanych właściwości tekstu, w tym koloru konturu tekstu (obrysu) i trybu renderowania. Umożliwia dostosowanie sposobu wyświetlania tekstu pod względem obrysu i wypełnienia.

#### P: Czy mogę zastosować różne kolory wypełnienia i konturu do różnych części tego samego tekstu?

 Odp.: Tak, możesz zmodyfikować kod, aby utworzyć inny`TextState` obiekty o odrębnych kolorach wypełnienia i konturu i zastosuj je do określonych części tekstu, używając osobnych`Stamp` obiekty.

#### P: Czy mogę zastosować kolory wypełnienia i konturu do tekstu, który jest już obecny w dokumencie PDF?

 O: Tak, możesz zastosować podobne zasady, aby zastosować kolory wypełnienia i konturu do istniejącego tekstu w dokumencie PDF, wybierając odpowiednie obiekty tekstowe i dodając je jako stemple z żądanym`TextState` nieruchomości.

#### P: Jak mogę dostosować krycie i mieszanie wypełnionego i obrysowanego tekstu?

 Odp.: Dostarczony kod umożliwia ustawienie krycia i właściwości mieszania stempla za pomocą`Opacity` I`BlendingSpace`właściwości, odpowiednio. Możesz dostosować te wartości, aby uzyskać pożądany efekt wizualny.

#### P: Jak mogę zastosować różne kolory wypełnienia i konturu do wielu stempli w tym samym dokumencie PDF?

 Odp.: możesz utworzyć wiele`TextState` obiektów o różnych kolorach wypełnienia i konturu, a następnie utwórz osobne`Stamp` obiekty dla każdego zestawu tekstu w różnych kolorach. Dodaj te znaczki do tego samego dokumentu PDF za pomocą`PdfFileStamp` klasa.

#### P: Czy w obrysowanym i wypełnionym tekście mogę używać czcionek innych niż Arial?

 O: Tak, możesz zmienić czcionkę, modyfikując parametr nazwy czcionki w pliku`FormattedText` konstruktor podczas tworzenia stempla. Możesz użyć dowolnej czcionki dostępnej w Twoim systemie.

#### P: Jak mogę zmodyfikować kąt obrotu obrysowanego i wypełnionego tekstu?

 Odp.: Dostarczony kod umożliwia ustawienie kąta obrotu stempla za pomocą`Rotation` nieruchomość. Można dostosować tę właściwość, aby określić żądany kąt obrotu tekstu.

#### P: Jak mogę kontrolować położenie i rozmiar obrysowanego i wypełnionego tekstu na stronie?

Odp.: Możesz użyć`SetOrigin` metoda`Stamp` obiekt umożliwiający ustawienie współrzędnych X i Y położenia stempla na stronie. Dodatkowo możesz dostosować rozmiar czcionki w pliku`FormattedText` konstruktor do kontrolowania rozmiaru tekstu.