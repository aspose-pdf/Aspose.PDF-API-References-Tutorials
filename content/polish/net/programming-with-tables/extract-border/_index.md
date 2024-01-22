---
title: Wyodrębnij obramowanie z pliku PDF
linktitle: Wyodrębnij obramowanie z pliku PDF
second_title: Aspose.PDF z dokumentacją API .NET
description: Dowiedz się, jak wyodrębnić obramowanie z pliku PDF przy użyciu Aspose.PDF dla .NET.
type: docs
weight: 80
url: /pl/net/programming-with-tables/extract-border/
---
tym samouczku nauczymy się, jak wyodrębnić obramowanie z pliku PDF za pomocą Aspose.PDF dla .NET. Krok po kroku wyjaśnimy kod źródłowy w języku C#. Pod koniec tego samouczka dowiesz się, jak wyodrębnić obramowanie z dokumentu PDF i zapisać je jako obraz. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Najpierw upewnij się, że skonfigurowałeś środowisko programistyczne C# za pomocą Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Ładowanie dokumentu PDF
W tym kroku ładujemy dokument PDF z określonego pliku.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Pamiętaj, aby zastąpić „KATALOG TWOJEGO DOKUMENTU” rzeczywistym katalogiem, w którym znajduje się plik PDF.

## Krok 3: Ekstrakcja krawędzi
Wyodrębnimy obramowanie z dokumentu PDF, iterując po operacjach zawartych w dokumencie.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // Przetwarzaj wszystkie operacje dotyczące zawartości
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Sprawdź rodzaj operacji
         // ...
         // Dodaj kod, aby przetworzyć każdą operację
     }
}
```

 Tworzymy`graphicsState` stos do przechowywania stanów graficznych, obraz bitmapowy do przechwytywania wyodrębnionej granicy, a`GraphicsPath` obiekt do przechowywania ścieżek rysowania i innych zmiennych do śledzenia stanu i kolorów.

## Krok 4: Przetwarzanie transakcji
Na tym etapie przetwarzamy każdą operację dokumentu w celu wyodrębnienia granicy.

```csharp
// Sprawdź rodzaj operacji
if (opSaveState != null)
{
     // Zapisz poprzedni stan i wypchnij bieżący stan na górę stosu
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Usuń bieżący stan i przywróć poprzedni stan
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Pobierz bieżącą macierz transformacji
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Pomnóż aktualną macierz przez macierz stanu
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Zaktualizuj ostatni punkt rysunku
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Przetwórz rysunek linii
     // ...
     // Dodaj kod obsługujący rysowanie linii
}
// ...
// Dodaj else if bloki dla innych operacji
```

Sprawdzamy rodzaj operacji za pomocą warunków i uruchamiamy odpowiedni kod dla każdej operacji.

## Krok 5: Obraz zapasowy
Na koniec zapisujemy obraz bitmapowy zawierający wyodrębnioną ramkę do określonego pliku.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Pamiętaj, aby określić prawidłowy katalog i nazwę pliku, aby zapisać obraz wyjściowy.

### Przykładowy kod źródłowy dla wyodrębnienia obramowania przy użyciu Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Domyślna wartość macierzy ctm to 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Układ współrzędnych System.Drawing opiera się na lewym górnym rogu, podczas gdy układ współrzędnych PDF znajduje się na dole po lewej stronie, więc musimy zastosować macierz inwersji
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Przetwórz wszystkie polecenia zawartości
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//Zapisz poprzedni stan i wypchnij bieżący stan na górę stosu
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Wyrzuć obecny stan i przywróć poprzedni
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opCtm != null)
		{
			System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
				(float)opCtm.Matrix.A,
				(float)opCtm.Matrix.B,
				(float)opCtm.Matrix.C,
				(float)opCtm.Matrix.D,
				(float)opCtm.Matrix.E,
				(float)opCtm.Matrix.F);

			// Pomnóż aktualną macierz przez macierz stanu
			((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
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
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## Wniosek
W tym samouczku nauczyliśmy się, jak wyodrębnić obramowanie z dokumentu PDF za pomocą Aspose.PDF dla .NET. Możesz skorzystać z tego przewodnika krok po kroku, aby wyodrębnić obramowanie z innych dokumentów PDF.

### Często zadawane pytania dotyczące wyodrębniania obramowania w pliku PDF

#### P: Jaki jest cel wyodrębniania obramowania z pliku PDF?

Odp.: Wyodrębnienie obramowania z pliku PDF może być przydatne do różnych celów. Pozwala wyodrębnić i przeanalizować elementy strukturalne dokumentu, takie jak tabele, diagramy czy elementy graficzne. Wyodrębnionego obramowania można użyć do określenia układu, wymiarów i położenia treści w dokumencie PDF.

#### P: Czy mogę wyodrębnić obramowanie z określonych stron lub obszarów dokumentu PDF?

O: Tak, możesz zmodyfikować dostarczony kod źródłowy C#, aby wyodrębnić obramowanie z określonych stron lub regionów w dokumencie PDF. Manipulując`doc.Pages` zbierania i określania niestandardowych kryteriów, możesz wyodrębnić obramowanie z poszczególnych stron lub obszarów zainteresowań.

#### P: Jak mogę dostosować format i jakość obrazu wyjściowego?

 Odp.: W dostarczonym kodzie C# wyodrębniona ramka jest zapisywana jako obraz PNG. Jeśli chcesz zmienić format obrazu wyjściowego, możesz zmodyfikować plik`ImageFormat.Png` parametr w`bitmap.Save` metodę na inne obsługiwane formaty obrazów, takie jak JPEG, BMP lub GIF. Dodatkowo możesz dostosować jakość obrazu lub ustawienia kompresji w zależności od wymagań.

#### P: Jakie inne operacje mogę wykonać na wyodrębnionej granicy?

Odp.: Po wyodrębnieniu obramowania jako obrazu można go dalej przetwarzać przy użyciu bibliotek lub algorytmów przetwarzania obrazu. Możesz analizować obraz, stosować filtry obrazu, wykrywać wzorce lub wykonywać OCR (optyczne rozpoznawanie znaków), aby w razie potrzeby wyodrębnić tekst z obrazu.

#### P: Czy istnieją jakieś ograniczenia lub uwagi dotyczące wyodrębniania obramowań ze złożonych dokumentów PDF?

Odp.: Proces wyodrębniania może się różnić w zależności od złożoności dokumentu PDF. Złożone pliki PDF z wieloma warstwami, przezroczystością lub zaawansowaną grafiką mogą wymagać dodatkowego przetwarzania lub dostosowań w celu dokładnego wyodrębnienia obramowania. Aby zapewnić wiarygodne wyniki, konieczne jest dokładne przetestowanie procesu ekstrakcji różnych dokumentów PDF.