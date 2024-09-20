---
title: Rand in PDF-bestand extraheren
linktitle: Rand in PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u randen uit een PDF-bestand haalt en ze opslaat als een afbeelding met Aspose.PDF voor .NET. Stapsgewijze handleiding met codevoorbeelden en tips voor succes.
type: docs
weight: 80
url: /nl/net/programming-with-tables/extract-border/
---
## Invoering

Bij het werken met PDF's lijkt het extraheren van specifieke elementen zoals randen of grafische paden misschien een lastige opgave. Maar met Aspose.PDF voor .NET kunt u eenvoudig randen of vormen uit een PDF-bestand extraheren en deze opslaan als een afbeelding. In deze tutorial duiken we in het proces van het extraheren van een rand uit een PDF en het opslaan ervan als een PNG-afbeelding. Maak u klaar om de grafische inhoud van uw PDF te beheren!

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat alles is ingesteld:

1.  Aspose.PDF voor .NET: Als u de Aspose.PDF-bibliotheek nog niet hebt geïnstalleerd, kunt u[download het hier](https://releases.aspose.com/pdf/net/). U moet de licentie ook toepassen, via de gratis proefversie of een gekochte licentie.
2. IDE-installatie: Stel een C#-project in Visual Studio of een andere .NET IDE in. Zorg ervoor dat u de benodigde verwijzingen naar de Aspose.PDF-bibliotheek hebt toegevoegd.
3. Input PDF-bestand: Zorg dat u een PDF-bestand gereed hebt waaruit u de randen wilt extraheren. Deze tutorial verwijst naar een bestand met de naam`input.pdf`.

## Vereiste pakketten importeren

Laten we beginnen met het importeren van de vereiste naamruimten. Deze pakketten bieden de tools die nodig zijn om de PDF-inhoud te manipuleren.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Nu we de basis onder de knie hebben, gaan we verder met de stapsgewijze handleiding. Hierin leggen we elk onderdeel van de code gedetailleerd uit.


## Stap 1: Het PDF-document laden

De eerste stap is het laden van het PDF-document dat de rand bevat die u wilt extraheren. Zie het als het openen van een boek voordat u begint met lezen: u hebt toegang nodig tot de inhoud!

 We beginnen met het opgeven van de map waarin uw PDF-bestand is opgeslagen en laden het document met behulp van de`Aspose.Pdf.Document` klas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Deze code laadt de`input.pdf` bestand uit de opgegeven directory. Zorg ervoor dat het bestandspad correct is, anders krijgt u mogelijk de foutmelding 'bestand niet gevonden'.

## Stap 2: Afbeeldingen en bitmap instellen

Voordat we beginnen met extraheren, moeten we een canvas maken om op te tekenen. In de wereld van .NET betekent dit het instellen van een Bitmap en Graphics-objecten. De Bitmap vertegenwoordigt de afbeelding en het Graphics-object stelt ons in staat om vormen te tekenen, zoals randen, die uit de PDF zijn geëxtraheerd.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Hier is een overzicht:
- We maken een bitmapafbeelding ter grootte van de eerste pagina van de PDF.
- GraphicsPath wordt gebruikt om vormen te definiëren (in dit geval randen).
- Matrix definieert hoe afbeeldingen worden getransformeerd. We hebben een inversiematrix nodig omdat PDF en .NET verschillende coördinatensystemen hebben.

## Stap 3: PDF-inhoud verwerken


Het PDF-bestand bestaat uit een reeks tekenopdrachten. We moeten elk van deze opdrachten verwerken om de randinformatie te identificeren en te extraheren.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Verwerken van opdrachten zoals het opslaan/herstellen van de status, het tekenen van lijnen, het opvullen van vormen, etc.
}
```

De code loopt door elke tekenoperator in de contentstream van de PDF. Elke operator kan een lijn, rechthoek of andere grafische instructie vertegenwoordigen.

## Stap 4: PDF-operators verwerken

Elke operator in het PDF-bestand bestuurt een actie. Om de rand te extraheren, moeten we opdrachten identificeren zoals "move to", "line to" en "draw rectangle". De volgende operatoren behandelen deze acties:

- MoveTo: verplaatst de cursor naar een beginpunt.
- LineTo: Tekent een lijn van het huidige punt naar een nieuw punt.
- Re: Tekent een rechthoek (dit kan een deel van de rand zijn).

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

In deze stap:
- Wij leggen de punten vast voor elke getekende lijn of vorm.
- Voor rechthoeken (`opRe` ), voegen we ze direct toe aan de`graphicsPath`, die we later gebruiken om de rand te tekenen.

## Stap 5: De rand tekenen

Zodra we de lijnen en rechthoeken hebben geïdentificeerd die de rand vormen, moeten we ze daadwerkelijk op het Bitmap-object tekenen. Hier komt het Graphics-object om de hoek kijken.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- We maken een Graphics-object op basis van de bitmap.
- SmoothingMode.HighQuality zorgt ervoor dat we een mooi, vloeiend beeld krijgen.
- Ten slotte gebruiken we DrawPath om de rand te tekenen.

## Stap 6: De geëxtraheerde rand opslaan

Nu we de border hebben geëxtraheerd, is het tijd om deze op te slaan als een afbeeldingsbestand. Dit zal de border opslaan als een PNG.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- De bitmap wordt opgeslagen als een PNG-afbeelding.
- U kunt deze afbeelding nu openen om de geëxtraheerde rand te bekijken.

## Conclusie

Het extraheren van randen uit een PDF-bestand met Aspose.PDF voor .NET lijkt in eerste instantie lastig, maar zodra u het begrijpt, wordt het eenvoudig. Door de tekenoperatoren in een PDF te begrijpen en de krachtige .NET-bibliotheken te gebruiken, kunt u grafische inhoud efficiënt manipuleren en extraheren. Deze gids geeft u een robuuste basis om aan de slag te gaan met PDF-manipulatie!

## Veelgestelde vragen

### Hoe ga ik om met meerdere pagina's in een PDF?  
 U kunt door elke pagina in het document heen bladeren door eroverheen te itereren`doc.Pages` in plaats van hardcoderen`doc.Pages[1]`.

### Kan ik op dezelfde manier andere elementen, zoals tekst, extraheren?  
Ja, Aspose.PDF biedt uitgebreide API's om tekst, afbeeldingen en andere inhoud uit PDF-bestanden te extraheren.

### Hoe vraag ik een licentie aan om beperkingen te vermijden?  
 Je kan[een licentie aanvragen](https://purchase.aspose.com/temporary-license/) door het te laden via de`License` les verzorgd door Aspose.

### Wat als mijn PDF geen randen heeft?  
Als uw PDF geen zichtbare randen bevat, levert het grafische extractieproces mogelijk geen resultaat op. Zorg ervoor dat de PDF-inhoud tekenbare randen bevat.

### Kan ik de uitvoer opslaan in andere formaten dan PNG?  
 Ja, verander gewoon de`ImageFormat.Png` naar een ander ondersteund formaat zoals`ImageFormat.Jpeg`.