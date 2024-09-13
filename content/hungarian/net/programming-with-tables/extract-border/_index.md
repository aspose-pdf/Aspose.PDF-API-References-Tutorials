---
title: Szegély kibontása PDF fájlból
linktitle: Szegély kibontása PDF fájlból
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthatja ki a szegélyt PDF-fájlból az Aspose.PDF for .NET segítségével.
type: docs
weight: 80
url: /hu/net/programming-with-tables/extract-border/
---
Ebben az oktatóanyagban megtudjuk, hogyan lehet kivonni a szegélyt PDF-fájlból az Aspose.PDF for .NET segítségével. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Ennek az oktatóanyagnak a végén tudni fogja, hogyan bontsa ki a szegélyt egy PDF-dokumentumból, és hogyan mentse el képként. Kezdjük!

## 1. lépés: A környezet beállítása
Először is győződjön meg arról, hogy beállította C# fejlesztői környezetét az Aspose.PDF for .NET segítségével. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: A PDF-dokumentum betöltése
Ebben a lépésben betöltjük a PDF dokumentumot a megadott fájlból.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet arra a könyvtárra, ahol a PDF-fájl található.

## 3. lépés: Élek kivonása
A szegélyt kivonjuk a PDF dokumentumból a dokumentumban szereplő műveletek iterációjával.

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
     // Az összes tartalomművelet feldolgozása
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Ellenőrizze a művelet típusát
         // ...
         // Adjon hozzá kódot az egyes műveletek feldolgozásához
     }
}
```

 Létrehozunk a`graphicsState` verem a grafikai állapotok tárolásához, bittérképes kép a kivont szegély rögzítéséhez, a`GraphicsPath` objektum a rajzi útvonalak tárolására, és egyéb változók az állapot és a színek nyomon követésére.

## 4. lépés: Tranzakció feldolgozása
Ebben a lépésben feldolgozzuk a dokumentum minden egyes műveletét a szegély kibontásához.

```csharp
// Ellenőrizze a művelet típusát
if (opSaveState != null)
{
     // Mentse el az előző állapotot, és tolja az aktuális állapotot a verem tetejére
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Törölje az aktuális állapotot és állítsa vissza az előző állapotot
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Az aktuális transzformációs mátrix lekérése
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Szorozzuk meg az aktuális mátrixot az állapotmátrixszal
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Frissítse az utolsó rajzpontot
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Egy vonal rajzolásának feldolgozása
     // ...
     // Adjon hozzá kódot a vonal rajzolásához
}
// ...
// Adjon hozzá else if blokkokat más műveletekhez
```

Feltételekkel ellenőrizzük a művelet típusát, és minden művelethez lefuttatjuk a megfelelő kódot.

## 5. lépés: Biztonsági kép
Végül elmentjük a kibontott szegélyt tartalmazó bittérképes képet egy megadott fájlba.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Ügyeljen arra, hogy a megfelelő könyvtárat és fájlnevet adja meg a kimeneti kép mentéséhez.

### Példa forráskód az Extract Borderhez az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Az alapértelmezett ctm-mátrix értéke 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
// System.Drawing koordinátarendszer bal felső alapú, míg a pdf koordinátarendszer bal alsó alapú, ezért az inverziós mátrixot kell alkalmaznunk
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Feldolgozza az összes tartalom parancsot
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
			// Mentse el az előző állapotot, és tolja a jelenlegi állapotot a verem tetejére
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Dobja el a jelenlegi állapotot, és állítsa vissza az előzőt
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

			// Szorozzuk meg az árammátrixot az állapotmátrixszal
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

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet szegélyt kivonni egy PDF-dokumentumból az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval szegélyt vonhat ki más PDF-dokumentumokból.

### GYIK a szegély kivonásához PDF-fájlban

#### K: Mi a célja a szegély kibontásának egy PDF-fájlból?

V: A szegély kibontása egy PDF-fájlból különféle célokra hasznos lehet. Lehetővé teszi a dokumentum szerkezeti elemeinek, például táblázatok, diagramok vagy grafikus elemek elkülönítését és elemzését. A kibontott szegély segítségével azonosíthatja a PDF-dokumentumban lévő tartalom elrendezését, méreteit és elhelyezését.

#### K: Kivonhatom a szegélyt a PDF-dokumentum bizonyos oldalairól vagy területeiről?

 V: Igen, módosíthatja a mellékelt C# forráskódot, hogy kivonja a szegélyt a PDF dokumentum bizonyos oldalairól vagy régióiról. Manipulálásával a`doc.Pages` gyűjtemény és egyéni feltételek megadásával kiválaszthatja, hogy kivonja a szegélyt bizonyos oldalakról vagy érdeklődési területekről.

#### K: Hogyan szabhatom testre a kimeneti képformátumot és minőséget?

 V: A mellékelt C# kódban a kibontott szegély PNG-képként kerül mentésre. Ha módosítani szeretné a kimeneti képformátumot, módosíthatja a`ImageFormat.Png` paraméter a`bitmap.Save` módszert más támogatott képformátumokhoz, például JPEG, BMP vagy GIF. Ezenkívül igénye szerint módosíthatja a képminőséget vagy a tömörítési beállításokat.

#### K: Milyen egyéb műveleteket hajthatok végre a kibontott határon?

V: Miután kibontotta a szegélyt képként, tovább dolgozhatja azt képfeldolgozó könyvtárak vagy algoritmusok segítségével. Szükség esetén elemezheti a képet, alkalmazhat képszűrőket, észlelheti a mintákat, vagy OCR-t (optikai karakterfelismerést) hajthat végre, hogy szöveget vonjon ki a képből.

#### K: Vannak-e korlátozások vagy megfontolások az összetett PDF-dokumentumok szegélyeinek kivonásakor?

V: A kibontási folyamat a PDF-dokumentum összetettségétől függően változhat. A többrétegű, átlátszó vagy fejlett grafikával rendelkező összetett PDF-fájlok további feldolgozást vagy módosításokat igényelhetnek a szegély pontos kibontása érdekében. Elengedhetetlen, hogy alaposan tesztelje a kinyerési folyamatot különböző PDF-dokumentumokon a megbízható eredmények érdekében.