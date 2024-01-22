---
title: Lägg till ritning med gradientfyllning
linktitle: Lägg till ritning med gradientfyllning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till en ritning med gradientfyllning med Aspose.PDF för .NET. Steg för steg handledning för att skapa attraktiva PDF-dokument.
type: docs
weight: 20
url: /sv/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att lägga till en ritning med gradientfyllning till programmering med grafik med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

## Steg 1: Installation av dokumentkatalog

den medföljande källkoden måste du ange katalogen där du vill spara den resulterande PDF-filen. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt och lägga till en sida

Vi skapar en instans av klassen Document och lägger till en sida i detta dokument.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Steg 3: Skapa ett grafobjekt och lägga till det på sidan

Vi skapar ett Graph-objekt med specificerade mått och lägger till det i sidans styckesamling.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Steg 4: Skapa rektangelobjekt och lägg till i diagram

Vi skapar ett rektangelobjekt med specificerade dimensioner och lägger till det i diagrammets formsamling.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Steg 5: Konfigurera Gradient Fill

Vi konfigurerar gradientfyllningen för rektangeln med klassen GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Detta skapar en gradientfyllning från rött till blått, från punkt (0, 0) till punkt (300, 300).

## Steg 6: Spara PDF-filen

Slutligen sparar vi den resulterande PDF-filen med namnet "AddDrawingWithGradientFill_out.pdf" i den angivna katalogen.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Exempel på källkod för Lägg till ritning med gradientfyllning med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Slutsats

I den här handledningen har vi förklarat steg för steg hur man lägger till en ritning med en gradientfyllning till programmering med grafik med Aspose.PDF för .NET. Nu kan du använda denna kunskap för att skapa attraktiva PDF-dokument med anpassade mönster och övertoningsfyllningar.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning syftar till att guida dig genom processen att lägga till en ritning med gradientfyllning till programmering med grafik med Aspose.PDF för .NET.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö. Dessutom rekommenderas att ha en grundläggande förståelse för C#-programmering.

#### F: Hur anger jag katalogen för att spara PDF-filen?

S: I den medföljande källkoden kan du ändra värdet på variabeln "dataDir" för att ange katalogen där du vill spara den resulterande PDF-filen.

#### F: Vad är syftet med Graph-objektet?

S: Graph-objektet fungerar som en behållare för ritelementen. Den skapas med specificerade mått och läggs till sidans styckesamling.

#### F: Hur kan jag konfigurera övertoningsfyllning för en form?

S: För att konfigurera övertoningsfyllning kan du ställa in egenskapen FillColor för en forms GraphInfo med klassen GradientAxialShading. Detta gör att du kan definiera start- och slutpunkterna för övertoningen och färgerna för övergången mellan.

#### F: Kan jag anpassa färgerna och riktningen för gradientfyllningen?

S: Ja, du kan anpassa färgerna och riktningen för gradientfyllningen genom att justera färgobjekten och ange start- och slutpunkterna för GradientAxialShading.

#### F: Vad är det sista steget i handledningen?

S: Det sista steget innebär att spara den resulterande PDF-filen med namnet "AddDrawingWithGradientFill_out.pdf" i den angivna katalogen.

#### F: Finns det ett exempel på källkod?

S: Ja, handledningen tillhandahåller ett exempel på källkod som du kan använda som referens för att implementera de beskrivna stegen.

#### F: Kan jag använda gradientfyllning på andra former förutom rektanglar?

S: Ja, du kan använda gradientfyllning på andra former också. Processen innebär att konfigurera FillColor-egenskapen för formens GraphInfo med klassen GradientAxialShading.