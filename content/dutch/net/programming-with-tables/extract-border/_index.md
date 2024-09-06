---
title: Rand in PDF-bestand extraheren
linktitle: Rand in PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de rand uit een PDF-bestand kunt halen met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/programming-with-tables/extract-border/
---
In deze tutorial gaan we leren hoe je de rand uit een PDF-bestand haalt met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet je hoe je de rand uit een PDF-document haalt en opslaat als een afbeelding. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg er eerst voor dat u uw C#-ontwikkelomgeving hebt ingesteld met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: Het PDF-document laden
In deze stap laden we het PDF-document vanuit het opgegeven bestand.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door de map waarin uw PDF-bestand zich bevindt.

## Stap 3: Randextractie
We halen de rand uit het PDF-document door de bewerkingen in het document te herhalen.

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
     // Verwerk alle inhoudsbewerkingen
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // Controleer het type operatie
         // ...
         // Voeg code toe om elke bewerking te verwerken
     }
}
```

 Wij creëren een`graphicsState` stapel om grafische toestanden op te slaan, een bitmapafbeelding om de geëxtraheerde rand vast te leggen, een`GraphicsPath` object om tekenpaden en andere variabelen op te slaan om de status en kleuren bij te houden.

## Stap 4: Transactieverwerking
In deze stap verwerken we elke bewerking van het document om de rand te extraheren.

```csharp
// Controleer het type operatie
if (opSaveState != null)
{
     // Sla de vorige status op en duw de huidige status naar de bovenkant van de stapel
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // Verwijder de huidige staat en herstel de vorige staat
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // Haal de huidige transformatiematrix op
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // Vermenigvuldig de huidige matrix met de toestandsmatrix
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // Laatste tekenpunt bijwerken
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // Verwerk het tekenen van een lijn
     // ...
     // Voeg code toe om het tekenen van een lijn te verwerken
}
// ...
// Voeg else if-blokken toe voor andere bewerkingen
```

We controleren het type bewerking aan de hand van voorwaarden en voeren voor elke bewerking de juiste code uit.

## Stap 5: Back-upimage
Ten slotte slaan we de bitmapafbeelding met de geëxtraheerde rand op in een opgegeven bestand.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

Zorg ervoor dat u de juiste map en bestandsnaam opgeeft om de uitvoerafbeelding op te slaan.

### Voorbeeldbroncode voor Extract Border met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// Standaard ctm-matrixwaarde is 1,0,0,1,0,0
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//Systeem. Het coördinatensysteem van de tekening is gebaseerd op linksboven, terwijl het coördinatensysteem van de pdf gebaseerd is op linksonder, dus we moeten de inversiematrix toepassen
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// Verwerk alle inhoudsopdrachten
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
			//Vorige staat opslaan en huidige staat bovenaan de stapel plaatsen
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// Gooi de huidige staat weg en herstel de vorige
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

			// Vermenigvuldig de huidige matrix met de toestandsmatrix
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

## Conclusie
In deze tutorial hebben we geleerd hoe je de rand uit een PDF-document kunt halen met Aspose.PDF voor .NET. Je kunt deze stapsgewijze handleiding gebruiken om de rand uit andere PDF-documenten te halen.

### FAQ's voor het extraheren van randen in PDF-bestanden

#### V: Wat is het doel van het extraheren van de rand uit een PDF-bestand?

A: Het extraheren van de rand uit een PDF-bestand kan voor verschillende doeleinden nuttig zijn. Hiermee kunt u de structurele elementen van het document isoleren en analyseren, zoals tabellen, diagrammen of grafische elementen. U kunt de geëxtraheerde rand gebruiken om de lay-out, afmetingen en positionering van de inhoud binnen het PDF-document te identificeren.

#### V: Kan ik de rand van specifieke pagina's of gebieden in het PDF-document extraheren?

A: Ja, u kunt de meegeleverde C#-broncode aanpassen om de rand van specifieke pagina's of regio's in het PDF-document te extraheren. Door de`doc.Pages` Door het verzamelen en specificeren van aangepaste criteria kunt u ervoor kiezen om de rand van specifieke pagina's of interessegebieden te extraheren.

#### V: Hoe kan ik het uitvoerformaat en de kwaliteit van de afbeelding aanpassen?

 A: In de meegeleverde C#-code wordt de geëxtraheerde rand opgeslagen als een PNG-afbeelding. Als u het uitvoerformaat van de afbeelding wilt wijzigen, kunt u de`ImageFormat.Png` parameter in de`bitmap.Save` methode naar andere ondersteunde afbeeldingsformaten, zoals JPEG, BMP of GIF. Bovendien kunt u de beeldkwaliteit of compressie-instellingen aanpassen op basis van uw vereisten.

#### V: Welke andere handelingen kan ik uitvoeren op de geëxtraheerde grens?

A: Nadat u de rand als afbeelding hebt geëxtraheerd, kunt u deze verder verwerken met behulp van beeldverwerkingsbibliotheken of algoritmen. U kunt de afbeelding analyseren, beeldfilters toepassen, patronen detecteren of OCR (Optical Character Recognition) uitvoeren om tekst uit de afbeelding te extraheren, indien nodig.

#### V: Zijn er beperkingen of overwegingen bij het extraheren van randen uit complexe PDF-documenten?

A: Het extractieproces kan variëren afhankelijk van de complexiteit van het PDF-document. Complexe PDF's met meerdere lagen, transparantie of geavanceerde afbeeldingen vereisen mogelijk extra verwerking of aanpassingen om de rand nauwkeurig te extraheren. Het is essentieel om het extractieproces grondig te testen op verschillende PDF-documenten om betrouwbare resultaten te garanderen.