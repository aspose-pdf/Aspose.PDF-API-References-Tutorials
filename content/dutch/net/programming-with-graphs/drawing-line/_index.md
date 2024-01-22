---
title: Lijn tekenen
linktitle: Lijn tekenen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een lijn over een pagina tekent met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het maken van aangepaste lijnen.
type: docs
weight: 80
url: /nl/net/programming-with-graphs/drawing-line/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om een lijn te tekenen met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Daarnaast heb je basiskennis van programmeren in C#.

## Stap 1: Documentmap instellen

In de meegeleverde broncode moet u de map opgeven waarin u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" in de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentinstantie maken en een pagina toevoegen

We maken een exemplaar van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Stap 3: Paginamarges instellen

We hebben de paginamarges aan alle kanten op 0 gezet.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Stap 4: Een grafiekobject en de eerste regel maken

We maken een Graph-object met afmetingen die gelijk zijn aan die van de pagina en tekenen de eerste lijn die van de linkerbenedenhoek naar de rechterbovenhoek van de pagina gaat.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Stap 5: Het tekenen van de tweede lijn

We tekenen de tweede lijn die van de linkerbovenhoek naar de rechteronderhoek van de pagina gaat.

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

Ten slotte slaan we het resulterende PDF-bestand op met de naam "DrawingLine_out.pdf" in de opgegeven map.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Voorbeeldbroncode voor Drawing Line met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentinstantie maken
Document pDoc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-document
Page pg = pDoc.Pages.Add();
// Stel de paginamarge aan alle zijden in op 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Maak een Graph-object waarvan de breedte en hoogte gelijk zijn aan de paginaafmetingen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Maak een eerste regelobject, beginnend vanaf de linkerbenedenhoek tot de rechterbovenhoek van de pagina
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Voeg een lijn toe aan de vormenverzameling van het Graph-object
graph.Shapes.Add(line);
// Trek een lijn van de linkerbovenhoek van de pagina naar de rechterbenedenhoek van de pagina
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Voeg een lijn toe aan de vormenverzameling van het Graph-object
graph.Shapes.Add(line2);
// Voeg een Graph-object toe aan de alineaverzameling van de pagina
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF-bestand opslaan
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe je een lijn tekent met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met aangepaste lijnen in uw PDF-bestanden te maken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden bij het tekenen van lijnen met Aspose.PDF voor .NET. U leert hoe u lijnen op een PDF-pagina kunt maken en hoe u de weergave ervan kunt aanpassen.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Basiskennis van programmeren in C# wordt ook aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: Wijzig de variabele "dataDir" in de meegeleverde broncode om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Hoe maak ik lijnen op een PDF-pagina?

A: In de tutorial wordt gedemonstreerd hoe u een Graph-object maakt met de afmetingen van de pagina en er vervolgens Line-objecten aan toevoegt. Wijzig de coördinaten en eigenschappen van de lijnobjecten om de gewenste lijnen te maken.

#### Vraag: Kan ik het uiterlijk van de lijnen aanpassen?

A: Ja, u kunt het uiterlijk van de lijnen aanpassen door de eigenschappen van de lijnobjecten te wijzigen. Dit omvat het wijzigen van hun coördinaten, kleur, dikte en andere grafische kenmerken.

#### Vraag: Hoe bewaar ik het PDF-document nadat ik de lijnen heb getekend?

A: Nadat u het Graph-object met Line-objecten aan de pagina hebt toegevoegd, kunt u het resulterende PDF-document opslaan met behulp van de`pDoc.Save(dataDir + "DrawingLine_out.pdf");` regel in de opgegeven broncode.

#### Vraag: Kan ik lijnen tekenen met verschillende hoeken en oriëntaties?

A: Ja, u kunt lijnen tekenen met verschillende hoeken en oriëntaties door de coördinaten en eigenschappen van de lijnobjecten in de grafiek aan te passen.