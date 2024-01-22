---
title: Lijnobject toevoegen aan PDF-bestand
linktitle: Lijnobject toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een aangepast lijnobject aan een PDF-bestand toevoegt met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-graphs/add-line-object/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om een lijnobject toe te voegen met Aspose.PDF voor .NET.

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

## Stap 4: Maak een lijnobject en voeg het toe aan het diagram

We maken een Line-object met de opgegeven coördinaten en voegen dit toe aan de vormcollectie van het diagram.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Stap 5: Lijnconfiguratie

We kunnen eigenschappen voor de lijn opgeven, zoals streepjestype en streepjesfase.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Stap 6: Het PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op met de naam "AddLineObject_out.pdf" in de opgegeven map.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Voorbeeldbroncode voor Line Object toevoegen met Aspose.PDF voor .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Geef de vulkleur op voor het Graph-object
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Voeg een rechthoekig object toe aan de vormencollectie van het Graph-object
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we stap voor stap uitgelegd hoe je een lijnobject toevoegt met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om PDF-documenten met aangepaste lijnen in uw toepassingen te maken.

### Veelgestelde vragen over het toevoegen van lijnobjecten aan PDF-bestanden

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het toevoegen van een lijnobject met Aspose.PDF voor .NET om uw PDF-documenten te verbeteren.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Bovendien wordt een basiskennis van C#-programmeren aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" wijzigen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Wat is het doel van het Graph-object?

A: Het Graph-object dient als container voor tekenelementen. Het wordt gemaakt met gespecificeerde afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### Vraag: Hoe kan ik een lijnobject aan het PDF-document toevoegen?

A: Om een lijnobject toe te voegen, maakt u een instantie van de klasse Line met gespecificeerde coördinaten en voegt u deze toe aan de vormverzameling van de grafiek.

#### Vraag: Kan ik het uiterlijk van de lijn aanpassen?

A: Ja, u kunt het uiterlijk van de lijn aanpassen door eigenschappen in te stellen, zoals het streepjestype en de streepjesfase, met behulp van de eigenschap GraphInfo van het Line-object.

#### Vraag: Wat is het doel van het specificeren van de dash-array en dash-fase?

A: Met de eigenschappen van de streepjesreeks en de streepjesfase kunt u stippellijnen of stippellijnen met specifieke patronen maken.

#### Vraag: Hoe kan ik het PDF-bestand opslaan nadat ik het lijnobject heb toegevoegd?

 A: Nadat u het lijnobject hebt toegevoegd, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "AddLineObject_out.pdf");` regel in de opgegeven broncode.

#### Vraag: Is er een voorbeeldbroncode beschikbaar?

A: Ja, de tutorial bevat een voorbeeldbroncode die u kunt raadplegen voor het implementeren van de beschreven stappen.