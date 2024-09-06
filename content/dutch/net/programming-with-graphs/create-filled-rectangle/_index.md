---
title: Maak een gevulde rechthoek
linktitle: Maak een gevulde rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een gevulde rechthoek maakt met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het aanpassen van de vulkleur.
type: docs
weight: 50
url: /nl/net/programming-with-graphs/create-filled-rectangle/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om een gevulde rechthoek te maken met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Heb ook basiskennis van C#-programmering.

## Stap 1: Documentdirectory instellen

In de meegeleverde broncode moet u de directory opgeven waar u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" naar de gewenste directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentinstantie maken en een pagina toevoegen

We maken een instantie van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject maken en toevoegen aan de pagina

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Stap 4: Rechthoekig object maken en toevoegen aan grafiek

We maken een rechthoekobject met de opgegeven afmetingen en voegen het toe aan de vormverzameling van het diagram.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Stap 5: De vulkleur instellen

We kunnen de opvulkleur voor de rechthoek specificeren met behulp van de eigenschap FillColor van het GraphInfo-object.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Stap 6: Het resulterende PDF-bestand opslaan

Tot slot slaan we het resulterende PDF-bestand op onder de naam "CreateFilledRectangle_out.pdf" in de opgegeven directory.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Voorbeeldbroncode voor Create Filled Rectangle met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentinstantie maken
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Page page = doc.Pages.Add();
// Grafiekinstantie maken
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Grafiekobject toevoegen aan alineaverzameling van pagina-instantie
page.Paragraphs.Add(graph);
// Maak een rechthoek-instantie
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Geef de vulkleur voor het grafiekobject op
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Rechthoekig object toevoegen aan vormenverzameling van Grafiekobject
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u een gevulde rechthoek maakt met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met aangepaste vulkleuren te maken in uw PDF-bestanden.

## Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden bij het maken van een gevulde rechthoek met Aspose.PDF voor .NET, zodat u aangepaste geometrische vormen met opvulkleuren aan uw PDF-bestanden kunt toevoegen.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Daarnaast wordt een basiskennis van C#-programmering aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" aanpassen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Wat is het doel van het Graph-object?

A: Het Graph-object fungeert als een container voor tekenelementen. Het wordt gemaakt met opgegeven afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### V: Hoe kan ik een gevulde rechthoek toevoegen aan het PDF-document?

A: Om een gevulde rechthoek toe te voegen, maakt u een instantie van de klasse Rectangle met opgegeven afmetingen en vulkleur en voegt u deze toe aan de vormverzameling van de grafiek.

#### V: Kan ik de afmetingen en de vulkleur van de rechthoek aanpassen?

 A: Ja, u kunt de afmetingen en de vulkleur van de rechthoek aanpassen door de parameters te wijzigen die aan de rechthoek zijn doorgegeven.`Aspose.Pdf.Drawing.Rectangle` constructor en het instellen van de eigenschap FillColor.

#### V: Hoe kan ik het resulterende PDF-bestand opslaan nadat ik de gevulde rechthoek heb gemaakt?

 A: Nadat u de gevulde rechthoek hebt gemaakt, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` regel in de meegeleverde broncode.