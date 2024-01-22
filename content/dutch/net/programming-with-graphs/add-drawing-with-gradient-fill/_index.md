---
title: Tekening met verloopvulling toevoegen
linktitle: Tekening met verloopvulling toevoegen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekening met verloopvulling toevoegt met Aspose.PDF voor .NET. Stapsgewijze zelfstudie om aantrekkelijke PDF-documenten te maken.
type: docs
weight: 20
url: /nl/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om een tekening met verloopvulling toe te voegen aan programmeren met afbeeldingen met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Daarnaast heb je basiskennis van programmeren in C#.

## Stap 1: Documentmap instellen

In de meegeleverde broncode moet u de map opgeven waarin u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" in de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentobject instantiëren en een pagina toevoegen

We maken een exemplaar van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject maken en aan de pagina toevoegen

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Stap 4: Maak een rechthoekig object en voeg het toe aan het diagram

We maken een rechthoekobject met opgegeven afmetingen en voegen dit toe aan de vormcollectie van het diagram.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Stap 5: Verloopopvulling configureren

We configureren de verloopvulling voor de rechthoek met behulp van de klasse GradientAxialShading.

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

Hierdoor ontstaat een verloopvulling van rood naar blauw, van punt (0, 0) tot punt (300, 300).

## Stap 6: Het PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op met de naam "AddDrawingWithGradientFill_out.pdf" in de opgegeven map.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Voorbeeldbroncode voor het toevoegen van een tekening met verloopvulling met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
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
## Conclusie

In deze tutorial hebben we stap voor stap uitgelegd hoe je een tekening met verloopvulling kunt toevoegen aan programmeren met afbeeldingen met Aspose.PDF voor .NET. Nu kunt u deze kennis gebruiken om aantrekkelijke PDF-documenten te maken met aangepaste ontwerpen en verloopvullingen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u door het proces te leiden van het toevoegen van een tekening met verloopvulling aan het programmeren met afbeeldingen met Aspose.PDF voor .NET.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Bovendien wordt een basiskennis van C#-programmeren aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de waarde van de variabele "dataDir" wijzigen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Wat is het doel van het Graph-object?

A: Het Graph-object dient als container voor de tekenelementen. Het wordt gemaakt met gespecificeerde afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### Vraag: Hoe kan ik de verloopvulling voor een vorm configureren?

A: Om de verloopvulling te configureren, kunt u de eigenschap FillColor van de GraphInfo van een vorm instellen met behulp van de klasse GradientAxialShading. Hiermee kunt u de begin- en eindpunten van het verloop en de kleuren waartussen de overgang plaatsvindt definiëren.

#### Vraag: Kan ik de kleuren en richting van de verloopvulling aanpassen?

A: Ja, u kunt de kleuren en richting van de verloopvulling aanpassen door de Color-objecten aan te passen en de begin- en eindpunten van de GradientAxialShading op te geven.

#### Vraag: Wat is de laatste stap van de tutorial?

A: De laatste stap bestaat uit het opslaan van het resulterende PDF-bestand met de naam "AddDrawingWithGradientFill_out.pdf" in de opgegeven map.

#### Vraag: Is er een voorbeeldbroncode beschikbaar?

A: Ja, de tutorial biedt een voorbeeldbroncode die u als referentie kunt gebruiken om de beschreven stappen te implementeren.

#### Vraag: Kan ik naast rechthoeken ook verloopvulling op andere vormen toepassen?

A: Ja, u kunt ook een verloopvulling op andere vormen toepassen. Het proces omvat het configureren van de eigenschap FillColor van de GraphInfo van de vorm met behulp van de klasse GradientAxialShading.