---
title: Lijnobject toevoegen in PDF-bestand
linktitle: Lijnobject toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een aangepast lijnobject toevoegt aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-graphs/add-line-object/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om een lijnobject toe te voegen met behulp van Aspose.PDF voor .NET.

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

## Stap 3: Een grafiekobject maken en aan de pagina toevoegen

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Stap 4: Lijnobject maken en toevoegen aan grafiek

We maken een Line-object met de opgegeven coördinaten en voegen dit toe aan de vormverzameling van de grafiek.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Stap 5: Lijninstelling

We kunnen eigenschappen voor de lijn opgeven, zoals het type streepje en de fase van het streepje.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Stap 6: Het PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "AddLineObject_out.pdf" in de opgegeven directory.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Voorbeeldbroncode voor het toevoegen van een lijnobject met behulp van Aspose.PDF voor .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Geef de vulkleur voor het grafiekobject op
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Rechthoekig object toevoegen aan vormenverzameling van Grafiekobject
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we stap voor stap uitgelegd hoe u een lijnobject toevoegt met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om PDF-documenten met aangepaste lijnen in uw toepassingen te maken.

### FAQ's voor het toevoegen van een lijnobject in een PDF-bestand

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het toevoegen van een lijnobject met behulp van Aspose.PDF voor .NET om uw PDF-documenten te verbeteren.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Daarnaast wordt een basiskennis van C#-programmering aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" aanpassen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Wat is het doel van het Graph-object?

A: Het Graph-object dient als een container voor tekenelementen. Het wordt gemaakt met opgegeven afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### V: Hoe kan ik een lijnobject toevoegen aan het PDF-document?

A: Om een lijnobject toe te voegen, maakt u een instantie van de klasse Line met opgegeven coördinaten en voegt u deze toe aan de vormverzameling van de grafiek.

#### V: Kan ik het uiterlijk van de lijn aanpassen?

A: Ja, u kunt het uiterlijk van de lijn aanpassen door eigenschappen zoals het streepjestype en de streepjesfase in te stellen via de eigenschap GraphInfo van het Line-object.

#### V: Wat is het doel van het specificeren van de dash-array en de dash-fase?

A: Met de eigenschappen dash array en dash phase kunt u stippellijnen of streeplijnen met specifieke patronen maken.

#### V: Hoe kan ik het PDF-bestand opslaan nadat ik het lijnobject heb toegevoegd?

 A: Nadat u het lijnobject hebt toegevoegd, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "AddLineObject_out.pdf");` regel in de meegeleverde broncode.

#### V: Is er een voorbeeldbroncode beschikbaar?

A: Ja, de tutorial bevat een voorbeeldbroncode die u kunt gebruiken bij het implementeren van de beschreven stappen.