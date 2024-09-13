---
title: Extrahera kant i PDF-fil
linktitle: Extrahera kant i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar gränsen i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-tables/extract-border/
---
den här handledningen ska vi lära oss hur man extraherar gränsen i en PDF-fil med Aspose.PDF för .NET. Vi kommer att förklara källkoden i C# steg för steg. I slutet av denna handledning vet du hur du extraherar gränsen från ett PDF-dokument och sparar den som en bild. Låt oss börja!

## Steg 1: Sätta upp miljön
Se först till att du har ställt in din C#-utvecklingsmiljö med Aspose.PDF för .NET. Lägg till referensen till biblioteket och importera de nödvändiga namnrymden.

## Steg 2: Ladda PDF-dokumentet
I det här steget laddar vi PDF-dokumentet från den angivna filen.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOGRAF" med den faktiska katalogen där din PDF-fil finns.

## Steg 3: Kantextraktion
Vi kommer att extrahera gränsen från PDF-dokumentet genom att iterera över operationerna i dokumentet.

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
     // Bearbeta alla innehållsoperationer
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Kontrollera typen av operation
         // ...
         // Lägg till kod för att bearbeta varje operation
     }
}
```

 Vi skapar en`graphicsState` stack för att lagra grafiktillstånd, en bitmappsbild för att fånga den extraherade gränsen, en`GraphicsPath` objekt för att lagra ritningsbanor och andra variabler för att spåra tillstånd och färger.

## Steg 4: Transaktionsbearbetning
det här steget behandlar vi varje operation av dokumentet för att extrahera gränsen.

```csharp
// Kontrollera typen av operation
if (opSaveState != null)
{
     // Spara det föregående tillståndet och skjut det aktuella tillståndet till toppen av stacken
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Ta bort nuvarande tillstånd och återställ tidigare tillstånd
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Hämta den aktuella transformationsmatrisen
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Multiplicera den aktuella matrisen med tillståndsmatrisen
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Uppdatera den sista ritpunkten
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Bearbeta ritningen av en linje
     // ...
     // Lägg till kod för att hantera att rita en linje
}
// ...
// Lägg till annat om-block för andra operationer
```

Vi kontrollerar typen av operation med hjälp av villkor och kör lämplig kod för varje operation.

## Steg 5: Säkerhetskopiera bild
Slutligen sparar vi bitmappsbilden som innehåller den extraherade gränsen till en specificerad fil.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Var noga med att ange rätt katalog och filnamn för att spara utdatabilden.

### Exempel på källkod för Extrahera Border med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Standardvärde för ctm-matris är 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//System.Drawing koordinatsystem är upptill vänster baserat, medan pdf koordinatsystem är låg vänster baserat, så vi måste tillämpa inversionsmatrisen
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Bearbeta alla innehållskommandon
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
			// Spara föregående tillstånd och tryck aktuellt tillstånd till toppen av stacken
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Kasta bort nuvarande tillstånd och återställ föregående
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

			// Multiplicera nuvarande matris med tillståndsmatrisen
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

## Slutsats
I den här handledningen lärde vi oss hur man extraherar gränsen från ett PDF-dokument med Aspose.PDF för .NET. Du kan använda den här steg-för-steg-guiden för att extrahera ramar från andra PDF-dokument.

### Vanliga frågor för extrahera gräns i PDF-fil

#### F: Vad är syftet med att extrahera gränsen från en PDF-fil?

S: Att extrahera gränsen från en PDF-fil kan vara användbart för olika ändamål. Det låter dig isolera och analysera de strukturella elementen i dokumentet, såsom tabeller, diagram eller grafiska element. Du kan använda den extraherade kanten för att identifiera layout, dimensioner och placering av innehållet i PDF-dokumentet.

#### F: Kan jag extrahera gränsen från specifika sidor eller områden i PDF-dokumentet?

 S: Ja, du kan ändra den medföljande C#-källkoden för att extrahera gränsen från specifika sidor eller regioner i PDF-dokumentet. Genom att manipulera`doc.Pages` insamling och specificering av anpassade kriterier kan du välja att extrahera gränsen från särskilda sidor eller intresseområden.

#### F: Hur kan jag anpassa utdatabildens format och kvalitet?

 S: I den medföljande C#-koden sparas den extraherade gränsen som en PNG-bild. Om du vill ändra utdatabildens format kan du ändra`ImageFormat.Png` parametern i`bitmap.Save` metoden till andra bildformat som stöds, såsom JPEG, BMP eller GIF. Dessutom kan du justera bildkvaliteten eller komprimeringsinställningarna baserat på dina krav.

#### F: Vilka andra operationer kan jag utföra på den extraherade gränsen?

S: När du har extraherat gränsen som en bild kan du bearbeta den ytterligare med bildbehandlingsbibliotek eller algoritmer. Du kan analysera bilden, använda bildfilter, upptäcka mönster eller utföra OCR (Optical Character Recognition) för att extrahera text från bilden om det behövs.

#### F: Finns det några begränsningar eller överväganden när man extraherar gränser från komplexa PDF-dokument?

S: Extraheringsprocessen kan variera beroende på PDF-dokumentets komplexitet. Komplexa PDF-filer med flera lager, transparens eller avancerad grafik kan kräva ytterligare bearbetning eller justeringar för att extrahera gränsen korrekt. Det är viktigt att noggrant testa utvinningsprocessen på olika PDF-dokument för att säkerställa tillförlitliga resultat.