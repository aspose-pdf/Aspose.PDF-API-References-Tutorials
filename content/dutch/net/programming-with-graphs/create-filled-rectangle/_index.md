---
title: Maak een gevulde rechthoek
linktitle: Maak een gevulde rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een gevulde rechthoek maakt met Aspose.PDF voor .NET. Stapsgewijze handleiding om de vulkleur aan te passen.
type: docs
weight: 50
url: /nl/net/programming-with-graphs/create-filled-rectangle/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om een gevulde rechthoek te maken met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Daarnaast heb je basiskennis van programmeren in C#.

## Stap 1: Documentmap instellen

In de meegeleverde broncode moet u de map opgeven waarin u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" in de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentinstantie maken en een pagina toevoegen

We maken een exemplaar van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject maken en aan de pagina toevoegen

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Stap 4: Maak een rechthoekig object en voeg het toe aan het diagram

We maken een rechthoekobject met de opgegeven afmetingen en voegen dit toe aan de vormcollectie van het diagram.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Stap 5: De vulkleur instellen

We kunnen de vulkleur voor de rechthoek opgeven met behulp van de eigenschap FillColor van het GraphInfo-object.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Stap 6: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op met de naam "CreateFilledRectangle_out.pdf" in de opgegeven map.

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
// Maak een Graph-instantie
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Voeg een grafiekobject toe aan de alineaverzameling van een pagina-instantie
page.Paragraphs.Add(graph);
// Rechthoekinstantie maken
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Geef de vulkleur op voor het Graph-object
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Voeg een rechthoekig object toe aan de vormencollectie van het Graph-object
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe je een gevulde rechthoek maakt met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met aangepaste vulkleuren in uw PDF-bestanden te maken.

## Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden bij het maken van een gevulde rechthoek met Aspose.PDF voor .NET, zodat u aangepaste geometrische vormen met opvulkleuren aan uw PDF-bestanden kunt toevoegen.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Bovendien wordt een basiskennis van C#-programmeren aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" wijzigen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Wat is het doel van het Graph-object?

A: Het Graph-object fungeert als container voor tekenelementen. Het wordt gemaakt met gespecificeerde afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### Vraag: Hoe kan ik een gevulde rechthoek aan het PDF-document toevoegen?

A: Om een gevulde rechthoek toe te voegen, maakt u een exemplaar van de klasse Rectangle met opgegeven afmetingen en vulkleur, en voegt u deze toe aan de vormcollectie van de grafiek.

#### Vraag: Kan ik de afmetingen en de vulkleur van de rechthoek aanpassen?

 A: Ja, u kunt de afmetingen en de vulkleur van de rechthoek aanpassen door de parameters te wijzigen die aan de rechthoek worden doorgegeven`Aspose.Pdf.Drawing.Rectangle` constructor en het instellen van de eigenschap FillColor.

#### Vraag: Hoe bewaar ik het resulterende PDF-bestand nadat ik de gevulde rechthoek heb gemaakt?

 A: Nadat u de gevulde rechthoek hebt gemaakt, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` regel in de opgegeven broncode.