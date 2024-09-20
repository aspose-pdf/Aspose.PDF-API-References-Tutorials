---
title: Wyodrębnij obramowanie w pliku PDF
linktitle: Wyodrębnij obramowanie w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić obramowania z pliku PDF i zapisać je jako obraz za pomocą Aspose.PDF dla .NET. Przewodnik krok po kroku z przykładami kodu i wskazówkami dotyczącymi sukcesu.
type: docs
weight: 80
url: /pl/net/programming-with-tables/extract-border/
---
## Wstęp

Podczas pracy z plikami PDF wyodrębnianie określonych elementów, takich jak obramowania lub ścieżki graficzne, może wydawać się zniechęcającym zadaniem. Ale dzięki Aspose.PDF dla .NET możesz łatwo wyodrębnić obramowania lub kształty z pliku PDF i zapisać je jako obraz. W tym samouczku zagłębimy się w proces wyodrębniania obramowania z pliku PDF i zapisywania go jako obrazu PNG. Przygotuj się na przejęcie kontroli nad zawartością graficzną swojego pliku PDF!

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że wszystko jest skonfigurowane:

1.  Aspose.PDF dla .NET: Jeśli jeszcze nie zainstalowałeś biblioteki Aspose.PDF, możesz to zrobić[pobierz tutaj](https://releases.aspose.com/pdf/net/). Będziesz musiał również zastosować licencję, albo poprzez bezpłatną wersję próbną, albo zakupioną licencję.
2. Konfiguracja IDE: Skonfiguruj projekt C# w Visual Studio lub innym IDE .NET. Upewnij się, że dodałeś niezbędne odwołania do biblioteki Aspose.PDF.
3. Wprowadź plik PDF: Przygotuj plik PDF, z którego wyodrębnisz obramowania. Ten samouczek będzie odwoływał się do pliku o nazwie`input.pdf`.

## Importowanie wymaganych pakietów

Zacznijmy od zaimportowania wymaganych przestrzeni nazw. Te pakiety zapewniają narzędzia potrzebne do manipulowania zawartością PDF.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Teraz, gdy omówiliśmy już podstawy, możemy przejść do przewodnika krok po kroku, w którym szczegółowo wyjaśnimy każdą część kodu.


## Krok 1: Ładowanie dokumentu PDF

Pierwszym krokiem jest załadowanie dokumentu PDF zawierającego obramowanie, które chcesz wyodrębnić. Pomyśl o tym jak o otwarciu książki przed rozpoczęciem czytania — potrzebujesz dostępu do treści!

 Zaczniemy od określenia katalogu, w którym przechowywany jest plik PDF i wczytania dokumentu za pomocą`Aspose.Pdf.Document` klasa.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Ten kod ładuje`input.pdf` plik z określonego katalogu. Upewnij się, że ścieżka do pliku jest poprawna, w przeciwnym razie może pojawić się błąd „plik nie znaleziony”.

## Krok 2: Konfigurowanie grafiki i mapy bitowej

Zanim zaczniemy wyodrębniać, musimy utworzyć płótno, na którym będziemy rysować. W świecie .NET oznacza to skonfigurowanie obiektów Bitmap i Graphics. Bitmap reprezentuje obraz, a obiekt Graphics pozwoli nam rysować kształty, takie jak obramowania, wyodrębnione z pliku PDF.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Oto szczegółowe informacje:
- Tworzymy obraz bitmapowy o rozmiarze pierwszej strony dokumentu PDF.
- GraphicsPath służy do definiowania kształtów (w tym przypadku obramowań).
- Macierz definiuje sposób transformacji grafiki. Potrzebujemy macierzy inwersji, ponieważ PDF i .NET mają różne układy współrzędnych.

## Krok 3: Przetwarzanie zawartości pliku PDF


Plik PDF zawiera serię poleceń rysunkowych. Musimy przetworzyć każde z tych poleceń, aby zidentyfikować i wyodrębnić informacje o obramowaniu.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Polecenia przetwarzania, takie jak zapisywanie/przywracanie stanu, rysowanie linii, wypełnianie kształtów itp.
}
```

Kod przechodzi przez każdy operator rysowania w strumieniu treści PDF. Każdy operator może reprezentować linię, prostokąt lub inną instrukcję graficzną.

## Krok 4: Obsługa operatorów PDF

Każdy operator w pliku PDF kontroluje akcję. Aby wyodrębnić obramowanie, musimy zidentyfikować polecenia, takie jak „move to”, „line to” i „draw rectangle”. Następujące operatory obsługują te akcje:

- MoveTo: Przenosi kursor do punktu początkowego.
- LineTo: Rysuje linię od bieżącego punktu do nowego punktu.
- Re: Rysuje prostokąt (może to być część obramowania).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

W tym kroku:
- Rejestrujemy punkty dla każdej narysowanej linii lub kształtu.
- Dla prostokątów (`opRe` ), dodajemy je bezpośrednio do`graphicsPath`, którego użyjemy później do narysowania granicy.

## Krok 5: Rysowanie granicy

Gdy już zidentyfikujemy linie i prostokąty tworzące obramowanie, musimy je narysować na obiekcie Bitmap. Tutaj wkracza obiekt Graphics.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- Tworzymy obiekt graficzny na podstawie mapy bitowej.
- SmoothingMode.HighQuality zapewnia uzyskanie ładnego, gładkiego obrazu.
- Na koniec używamy DrawPath, aby narysować obramowanie.

## Krok 6: Zapisywanie wyodrębnionej ramki

Teraz, gdy wyodrębniliśmy obramowanie, czas zapisać je jako plik obrazu. Spowoduje to zapisanie obramowania jako PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- Mapa bitowa jest zapisywana jako obraz PNG.
- Teraz możesz otworzyć ten obraz, aby obejrzeć wyodrębnioną ramkę.

## Wniosek

Wyodrębnianie obramowań z pliku PDF za pomocą Aspose.PDF dla .NET może wydawać się trudne na początku, ale po rozłożeniu staje się proste. Rozumiejąc operatory rysowania w pliku PDF i wykorzystując potężne biblioteki .NET, możesz sprawnie manipulować i wyodrębniać zawartość graficzną. Ten przewodnik daje solidne podstawy do rozpoczęcia manipulowania plikami PDF!

## Najczęściej zadawane pytania

### Jak radzić sobie z wieloma stronami w pliku PDF?  
 Możesz przeglądać każdą stronę dokumentu, powtarzając ją`doc.Pages` zamiast kodowania na stałe`doc.Pages[1]`.

### Czy mogę wyodrębnić inne elementy, np. tekst, stosując to samo podejście?  
Tak, Aspose.PDF oferuje rozbudowane interfejsy API umożliwiające wyodrębnianie tekstu, obrazów i innej zawartości z plików PDF.

### Jak ubiegać się o licencję, aby uniknąć ograniczeń?  
 Możesz[zastosować licencję](https://purchase.aspose.com/temporary-license/) ładując go przez`License` klasa udostępniona przez Aspose.

### Co zrobić, jeśli mój plik PDF nie ma obramowań?  
Jeśli Twój plik PDF nie zawiera widocznych obramowań, proces ekstrakcji grafiki może nie dać żadnego rezultatu. Upewnij się, że zawartość pliku PDF zawiera rysowalne obramowania.

### Czy mogę zapisać dane wyjściowe w formatach innych niż PNG?  
 Tak, po prostu zmień`ImageFormat.Png` do innego obsługiwanego formatu, takiego jak`ImageFormat.Jpeg`.