---
title: Wyodrębnij obramowanie w pliku PDF
linktitle: Wyodrębnij obramowanie w pliku PDF
second_title: Aspose.PDF dla .NET API Reference
description: Dowiedz się, jak wyodrębnić obramowanie w pliku PDF za pomocą Aspose.PDF dla platformy .NET.
type: docs
weight: 80
url: /pl/net/programming-with-tables/extract-border/
---
tym samouczku nauczymy się, jak wyodrębnić obramowanie w pliku PDF za pomocą Aspose.PDF dla .NET. Wyjaśnimy kod źródłowy w C# krok po kroku. Na końcu tego samouczka dowiesz się, jak wyodrębnić obramowanie z dokumentu PDF i zapisać je jako obraz. Zaczynajmy!

## Krok 1: Konfigurowanie środowiska
Najpierw upewnij się, że skonfigurowałeś środowisko programistyczne C# z Aspose.PDF dla .NET. Dodaj odwołanie do biblioteki i zaimportuj niezbędne przestrzenie nazw.

## Krok 2: Ładowanie dokumentu PDF
W tym kroku ładujemy dokument PDF z określonego pliku.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Pamiętaj, aby zastąpić frazę „KATALOG DOKUMENTÓW” rzeczywistą nazwą katalogu, w którym znajduje się plik PDF.

## Krok 3: Ekstrakcja krawędzi
Wyodrębnimy obramowanie z dokumentu PDF, powtarzając operacje zawarte w dokumencie.

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
     // Przetwarzaj wszystkie operacje związane z treścią
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Sprawdź rodzaj operacji
         // ...
         // Dodaj kod do przetwarzania każdej operacji
     }
}
```

 Tworzymy`graphicsState` stos do przechowywania stanów grafiki, obraz bitmapowy do przechwytywania wyodrębnionej granicy,`GraphicsPath` obiekt do przechowywania ścieżek rysowania i inne zmienne do śledzenia stanu i kolorów.

## Krok 4: Przetwarzanie transakcji
Na tym etapie przetwarzamy każdą operację dokumentu, aby wyodrębnić obramowanie.

```csharp
// Sprawdź rodzaj operacji
if (opSaveState != null)
{
     // Zapisz poprzedni stan i przesuń bieżący stan na górę stosu
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

     // Pomnóż macierz bieżącą przez macierz stanu
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Zaktualizuj ostatni punkt rysunkowy
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Przetwarzanie rysowania linii
     // ...
     // Dodaj kod do obsługi rysowania linii
}
// ...
// Dodaj bloki else if dla innych operacji
```

Sprawdzamy typ operacji za pomocą warunków i uruchamiamy odpowiedni kod dla każdej operacji.

## Krok 5: Obraz kopii zapasowej
Na koniec zapisujemy obraz bitmapowy zawierający wyodrębnioną ramkę do określonego pliku.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Pamiętaj o podaniu prawidłowego katalogu i nazwy pliku, aby zapisać obraz wyjściowy.

### Przykładowy kod źródłowy dla Extract Border using Aspose.PDF dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Domyślna wartość macierzy ctm wynosi 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Układ współrzędnych rysunku jest oparty na lewym górnym rogu, podczas gdy układ współrzędnych pliku PDF jest oparty na lewym dolnym rogu, dlatego musimy zastosować macierz inwersji
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Przetwórz wszystkie polecenia dotyczące zawartości
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
			// Zapisz poprzedni stan i przenieś bieżący stan na górę stosu
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

			// Pomnóż macierz bieżącą przez macierz stanu
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
W tym samouczku nauczyliśmy się, jak wyodrębnić obramowanie z dokumentu PDF za pomocą Aspose.PDF dla .NET. Możesz użyć tego przewodnika krok po kroku, aby wyodrębnić obramowanie z innych dokumentów PDF.

### FAQ dotyczące wyodrębniania obramowania w pliku PDF

#### P: Jaki jest cel wyodrębniania obramowania z pliku PDF?

A: Wyodrębnienie obramowania z pliku PDF może być przydatne do różnych celów. Pozwala ono na wyizolowanie i przeanalizowanie elementów strukturalnych dokumentu, takich jak tabele, diagramy lub elementy graficzne. Wyodrębnioną ramkę można wykorzystać do identyfikacji układu, wymiarów i pozycjonowania treści w dokumencie PDF.

#### P: Czy mogę wyodrębnić obramowanie z określonych stron lub obszarów w dokumencie PDF?

 A: Tak, możesz zmodyfikować dostarczony kod źródłowy C#, aby wyodrębnić obramowanie z określonych stron lub regionów w dokumencie PDF. Manipulując`doc.Pages` Po wybraniu kolekcji i określeniu niestandardowych kryteriów możesz wyodrębnić obramowanie z konkretnych stron lub obszarów zainteresowania.

#### P: W jaki sposób mogę dostosować format i jakość obrazu wyjściowego?

 A: W podanym kodzie C# wyodrębniona granica jest zapisana jako obraz PNG. Jeśli chcesz zmienić format obrazu wyjściowego, możesz zmodyfikować`ImageFormat.Png` parametr w`bitmap.Save` metodę do innych obsługiwanych formatów obrazów, takich jak JPEG, BMP lub GIF. Ponadto możesz dostosować jakość obrazu lub ustawienia kompresji w zależności od swoich wymagań.

#### P: Jakie inne operacje mogę wykonać na wyodrębnionej granicy?

A: Po wyodrębnieniu obramowania jako obrazu możesz je dalej przetwarzać za pomocą bibliotek przetwarzania obrazu lub algorytmów. Możesz analizować obraz, stosować filtry obrazu, wykrywać wzorce lub wykonywać OCR (Optical Character Recognition), aby wyodrębnić tekst z obrazu, jeśli to konieczne.

#### P: Czy istnieją jakieś ograniczenia lub kwestie, które należy wziąć pod uwagę przy wyodrębnianiu obramowań ze złożonych dokumentów PDF?

A: Proces ekstrakcji może się różnić w zależności od złożoności dokumentu PDF. Złożone pliki PDF z wieloma warstwami, przezroczystością lub zaawansowaną grafiką mogą wymagać dodatkowego przetwarzania lub korekt, aby dokładnie wyodrębnić obramowanie. Konieczne jest dokładne przetestowanie procesu ekstrakcji na różnych dokumentach PDF, aby zapewnić wiarygodne wyniki.