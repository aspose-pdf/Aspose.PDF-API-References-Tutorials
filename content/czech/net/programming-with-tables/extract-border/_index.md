---
title: Extrahovat ohraničení v souboru PDF
linktitle: Extrahovat ohraničení v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak extrahovat ohraničení v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 80
url: /cs/net/programming-with-tables/extract-border/
---
tomto tutoriálu se naučíme, jak extrahovat ohraničení v souboru PDF pomocí Aspose.PDF pro .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak extrahovat okraj z dokumentu PDF a uložit jej jako obrázek. Začněme!

## Krok 1: Nastavení prostředí
Nejprve se ujistěte, že jste nastavili vývojové prostředí C# pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Načtení dokumentu PDF
V tomto kroku načteme PDF dokument ze zadaného souboru.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Nezapomeňte nahradit "VÁŠ ADRESÁŘ DOKUMENTŮ" skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 3: Extrakce okrajů
Ohraničení extrahujeme z dokumentu PDF iterací přes operace obsažené v dokumentu.

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
     // Zpracujte všechny operace s obsahem
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Zkontrolujte typ operace
         // ...
         // Přidejte kód pro zpracování každé operace
     }
}
```

 Vytváříme a`graphicsState` zásobník pro uložení grafických stavů, bitmapový obrázek pro zachycení extrahovaného okraje, a`GraphicsPath` objekt pro ukládání cest výkresu a další proměnné pro sledování stavu a barev.

## Krok 4: Zpracování transakce
tomto kroku zpracujeme každou operaci dokumentu, abychom extrahovali hranici.

```csharp
// Zkontrolujte typ operace
if (opSaveState != null)
{
     // Uložte předchozí stav a posuňte aktuální stav na vrchol zásobníku
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Smazat aktuální stav a obnovit předchozí stav
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Načtěte aktuální transformační matici
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Vynásobte aktuální matici stavovou maticí
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Aktualizujte poslední bod kreslení
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Zpracujte kreslení čáry
     // ...
     // Přidejte kód pro zpracování čáry
}
// ...
// Přidejte bloky else if pro další operace
```

Zkontrolujeme typ operace pomocí podmínek a pro každou operaci spustíme příslušný kód.

## Krok 5: Záložní obrázek
Nakonec bitmapový obrázek obsahující extrahovaný okraj uložíme do určeného souboru.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Nezapomeňte zadat správný adresář a název souboru pro uložení výstupního obrazu.

### Příklad zdrojového kódu pro Extract Border pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Výchozí hodnota matice ctm je 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing souřadnicový systém je založen vlevo nahoře, zatímco pdf souřadný systém je založen vlevo dole, takže musíme použít inverzní matici
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Zpracujte všechny příkazy obsahu
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
			// Uložte předchozí stav a přesuňte aktuální stav na vrchol zásobníku
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Zahodit současný stav a obnovit předchozí
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

			// Vynásobte aktuální matici stavovou maticí
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

## Závěr
V tomto tutoriálu jsme se naučili, jak extrahovat ohraničení z dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí tohoto podrobného průvodce můžete extrahovat ohraničení z jiných dokumentů PDF.

### Časté dotazy k extrahování ohraničení v souboru PDF

#### Otázka: Jaký je účel extrahování ohraničení ze souboru PDF?

Odpověď: Extrahování ohraničení ze souboru PDF může být užitečné pro různé účely. Umožňuje izolovat a analyzovat strukturální prvky dokumentu, jako jsou tabulky, diagramy nebo grafické prvky. Extrahovaný okraj můžete použít k identifikaci rozvržení, rozměrů a umístění obsahu v dokumentu PDF.

#### Otázka: Mohu extrahovat ohraničení z konkrétních stránek nebo oblastí v dokumentu PDF?

 Odpověď: Ano, můžete upravit poskytnutý zdrojový kód C# a extrahovat ohraničení z konkrétních stránek nebo oblastí v dokumentu PDF. Manipulací s`doc.Pages` shromažďování a specifikování vlastních kritérií, můžete si vybrat extrahování ohraničení z konkrétních stránek nebo oblastí zájmu.

#### Otázka: Jak mohu přizpůsobit formát a kvalitu výstupního obrázku?

 Odpověď: V poskytnutém kódu C# je extrahovaný okraj uložen jako obrázek PNG. Pokud chcete změnit výstupní formát obrázku, můžete upravit`ImageFormat.Png` parametr v`bitmap.Save` na jiné podporované formáty obrázků, jako je JPEG, BMP nebo GIF. Kromě toho můžete upravit nastavení kvality obrazu nebo komprese podle vašich požadavků.

#### Otázka: Jaké další operace mohu provést na extrahovaném okraji?

Odpověď: Jakmile vyjmete okraj jako obrázek, můžete jej dále zpracovat pomocí knihoven nebo algoritmů pro zpracování obrazu. Můžete analyzovat obraz, aplikovat obrazové filtry, detekovat vzory nebo provádět OCR (Optical Character Recognition), abyste v případě potřeby extrahovali text z obrazu.

#### Otázka: Existují nějaká omezení nebo úvahy při extrahování okrajů ze složitých dokumentů PDF?

Odpověď: Proces extrakce se může lišit v závislosti na složitosti dokumentu PDF. Složité soubory PDF s více vrstvami, průhledností nebo pokročilou grafikou mohou vyžadovat další zpracování nebo úpravy, aby bylo možné přesně extrahovat okraj. Pro zajištění spolehlivých výsledků je nezbytné důkladně otestovat proces extrakce na různých dokumentech PDF.