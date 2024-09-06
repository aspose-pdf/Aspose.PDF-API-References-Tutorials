---
title: Lijn tekenen
linktitle: Lijn tekenen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een lijn over een pagina tekent met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het maken van aangepaste lijnen.
type: docs
weight: 80
url: /nl/net/programming-with-graphs/drawing-line/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om een lijn te tekenen met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Heb ook basiskennis van C#-programmering.

## Stap 1: Documentdirectory instellen

In de meegeleverde broncode moet u de directory opgeven waar u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" naar de gewenste directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentinstantie maken en een pagina toevoegen

We maken een instantie van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Stap 3: Paginamarges instellen

We stellen de paginamarges aan alle kanten in op 0.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Stap 4: Een grafiekobject en de eerste lijn maken

We maken een grafiekobject met afmetingen die gelijk zijn aan die van de pagina en tekenen de eerste lijn van de linkeronderhoek naar de rechterbovenhoek van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Stap 5: De tweede lijn tekenen

We tekenen de tweede lijn van de linkerbovenhoek naar de rechteronderhoek van de pagina.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Stap 6: Het grafiekobject aan de pagina toevoegen

We voegen het Graph-object toe aan de alineaverzameling van de pagina.

```csharp
pg.Paragraphs.Add(graph);
```

## Stap 7: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "DrawingLine_out.pdf" in de opgegeven directory.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Voorbeeldbroncode voor het tekenen van lijnen met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentinstantie maken
Document pDoc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-document
Page pg = pDoc.Pages.Add();
// Stel de paginamarge aan alle kanten in op 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Maak een grafiekobject met breedte en hoogte gelijk aan de pagina-afmetingen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Maak een object op de eerste regel, beginnend in de linkerbenedenhoek tot de rechterbovenhoek van de pagina
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Lijn toevoegen aan vormenverzameling van Grafiekobject
graph.Shapes.Add(line);
// Trek een lijn van de linkerbovenhoek van de pagina naar de rechteronderhoek van de pagina
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Lijn toevoegen aan vormenverzameling van Grafiekobject
graph.Shapes.Add(line2);
// Grafiekobject toevoegen aan alineaverzameling van pagina
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF-bestand opslaan
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u een lijn tekent met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met aangepaste lijnen te maken in uw PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden bij het tekenen van lijnen met Aspose.PDF voor .NET. U leert hoe u lijnen op een PDF-pagina kunt maken en hun uiterlijk kunt aanpassen.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Basiskennis van C#-programmering wordt ook aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: Wijzig de variabele "dataDir" in de meegeleverde broncode om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Hoe maak ik lijnen op een PDF-pagina?

A: De tutorial laat zien hoe je een Graph-object maakt met de afmetingen van de pagina en er vervolgens Line-objecten aan toevoegt. Wijzig de coördinaten en eigenschappen van de Line-objecten om de gewenste lijnen te maken.

#### V: Kan ik het uiterlijk van de lijnen aanpassen?

A: Ja, u kunt het uiterlijk van de lijnen aanpassen door de eigenschappen van de Line-objecten te wijzigen. Dit omvat het wijzigen van hun coördinaten, kleur, dikte en andere grafische kenmerken.

#### V: Hoe kan ik het PDF-document opslaan nadat ik de lijnen heb getekend?

 A: Nadat u het grafiekobject met lijnobjecten aan de pagina hebt toegevoegd, kunt u het resulterende PDF-document opslaan met behulp van de`pDoc.Save(dataDir + "DrawingLine_out.pdf");` regel in de meegeleverde broncode.

#### V: Kan ik lijnen met verschillende hoeken en oriëntaties tekenen?

A: Ja, u kunt lijnen met verschillende hoeken en oriëntaties tekenen door de coördinaten en eigenschappen van de lijnobjecten in de grafiek aan te passen.