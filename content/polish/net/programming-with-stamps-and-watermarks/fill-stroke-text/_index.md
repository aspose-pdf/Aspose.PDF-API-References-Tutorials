---
title: Wypełnij tekst obrysu w pliku PDF
linktitle: Wypełnij tekst obrysu w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak łatwo wypełniać i konturować tekst w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 90
url: /pl/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
tym samouczku pokażemy Ci krok po kroku, jak wypełnić i obrysować tekst w pliku PDF za pomocą Aspose.PDF dla .NET. Pokażemy Ci, jak użyć dostarczonego kodu źródłowego C#, aby zastosować kolory wypełnienia i obrysu do tekstu w pliku PDF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Zainstalowane środowisko programistyczne .NET.
- Biblioteka Aspose.PDF dla platformy .NET pobrana i wykorzystana w projekcie.

## Krok 2: Tworzenie obiektu TextState

Pierwszym krokiem jest utworzenie obiektu TextState, aby przekazać zaawansowane właściwości. Oto jak to zrobić:

```csharp
// Utwórz obiekt TextState, aby przenieść zaawansowane właściwości
TextState ts = new TextState();

// Ustaw kolor konturu
ts.StrokingColor = Color.Gray;

// Zdefiniuj tryb renderowania tekstu
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Powyższy kod tworzy nowy obiekt TextState i ustawia kolor obrysu oraz sposób renderowania tekstu.

## Krok 3: Ładowanie dokumentu PDF

Teraz, gdy obiekt TextState jest gotowy, możemy załadować dokument PDF, w którym chcemy zastosować wypełnienie i kontur tekstu. Oto jak to zrobić:

```csharp
// Załaduj dokument PDF jako dane wejściowe
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Powyższy kod ładuje istniejący dokument PDF korzystając z klasy PdfFileStamp z biblioteki Aspose.PDF.Facades.

## Krok 4: Dodaj wypełnienie i obrys do tekstu

Teraz, gdy dokument PDF jest załadowany, możemy dodać wypełnienie i kontur do tekstu. Oto jak to zrobić:

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

Powyższy kod tworzy stempel z określonym tekstem i zdefiniowanymi właściwościami wypełnienia i obrysu.

## Krok 5: Zapisz dokument wyjściowy

Po dodaniu znacznika tekstowego możemy zapisać zmodyfikowany dokument PDF. Oto jak to zrobić:

```csharp
// Zapisz zmodyfikowany dokument
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

Powyższy kod zapisuje edytowany dokument PDF w określonym katalogu.

### Przykładowy kod źródłowy dla funkcji Wypełnij tekst obrysu przy użyciu Aspose.PDF dla .NET 
```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz obiekt TextState, aby przenieść zaawansowane właściwości
TextState ts = new TextState();

// Ustaw kolor dla obrysu
ts.StrokingColor = Color.Gray;

// Ustaw tryb renderowania tekstu
ts.RenderingMode = TextRenderingMode.StrokeText;

// Załaduj dokument wejściowy PDF
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Powiąż tekst stanu
stamp.BindTextState(ts);

// Ustaw początek X,Y
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Dodaj znaczek
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Wniosek

Gratulacje! Nauczyłeś się wypełniać i konturować tekst w dokumencie PDF za pomocą Aspose.PDF dla .NET. Teraz możesz zastosować tę wiedzę, aby dostosować kolory wypełnienia i konturu w dokumentach PDF.

### Często zadawane pytania dotyczące tekstu obrysu wypełnienia w pliku PDF

#### P: Na czym polega wypełnianie i konturowanie tekstu w dokumencie PDF i kiedy mogę być zmuszony to zrobić?

A: Wypełnianie i konturowanie tekstu w dokumencie PDF obejmuje stosowanie kolorów do wnętrza znaków tekstowych (wypełnienie) i do obramowań wokół tekstu (kontur). Można tego użyć do poprawienia wyglądu wizualnego tekstu, stworzenia nacisku lub wyróżnienia określonej zawartości w pliku PDF.

#### P: W jaki sposób dostarczony kod źródłowy C# realizuje wypełnianie i konturowanie tekstu w pliku PDF?

 A: Dostarczony kod źródłowy pokazuje, jak utworzyć`TextState` obiekt do definiowania zaawansowanych właściwości tekstu, takich jak kolor obrysu i tryb renderowania. Następnie używa Aspose.PDF.Facades do załadowania istniejącego dokumentu PDF, utworzenia stempla zawierającego tekst z określonymi właściwościami wypełnienia i obrysu, a następnie dodania stempla do dokumentu.

####  P: Jaki jest cel`TextState` object in the code?

 A: Ten`TextState`obiekt służy do definiowania zaawansowanych właściwości tekstu, w tym koloru konturu tekstu (obrysu) i trybu renderowania. Umożliwia dostosowanie sposobu wyświetlania tekstu pod względem obrysu i wypełnienia.

#### P: Czy mogę zastosować różne kolory wypełnienia i konturu do różnych części tego samego tekstu?

 A: Tak, możesz zmodyfikować kod, aby utworzyć różne`TextState` obiekty z różnymi kolorami wypełnienia i konturu i stosować je do określonych części tekstu za pomocą oddzielnych`Stamp` obiekty.

#### P: Czy mogę zastosować kolory wypełnienia i konturu do tekstu, który już znajduje się w dokumencie PDF?

 O: Tak, możesz zastosować podobne zasady, aby zastosować kolory wypełnienia i konturu do istniejącego tekstu w dokumencie PDF, wybierając odpowiednie obiekty tekstowe i dodając je jako stemple z pożądanym kolorem.`TextState` Właściwości.

#### P: W jaki sposób mogę dostosować krycie i mieszanie tekstu wypełnionego i obrysowanego?

 A: Dostarczony kod umożliwia ustawienie właściwości krycia i mieszania stempla za pomocą`Opacity` I`BlendingSpace`właściwości. Możesz dostosować te wartości, aby uzyskać pożądany efekt wizualny.

#### P: Jak mogę zastosować różne kolory wypełnienia i konturu do wielu stempli w tym samym dokumencie PDF?

 A: Możesz utworzyć wiele`TextState` obiekty o różnych kolorach wypełnienia i konturu, a następnie utwórz oddzielne`Stamp` obiekty dla każdego zestawu tekstu z różnymi kolorami. Dodaj te znaczki do tego samego dokumentu PDF za pomocą`PdfFileStamp` klasa.

#### P: Czy mogę używać innych czcionek niż Arial do tekstu konturowanego i wypełnionego?

 A: Tak, możesz zmienić czcionkę, modyfikując parametr nazwy czcionki w`FormattedText` konstruktora podczas tworzenia znaczka. Możesz użyć dowolnego fontu dostępnego w systemie.

#### P: W jaki sposób mogę zmienić kąt obrotu tekstu obrysowanego i wypełnionego?

 A: Dostarczony kod pozwala na ustawienie kąta obrotu znaczka za pomocą`Rotation` Właściwość. Możesz dostosować tę właściwość, aby określić pożądany kąt obrotu tekstu.

#### P: W jaki sposób mogę kontrolować położenie i rozmiar tekstu obrysowanego i wypełnionego na stronie?

 A: Możesz użyć`SetOrigin` metoda`Stamp` obiekt, aby ustawić współrzędne X i Y pozycji znaczka na stronie. Dodatkowo możesz dostosować rozmiar czcionki w`FormattedText` konstruktor kontrolujący rozmiar tekstu.