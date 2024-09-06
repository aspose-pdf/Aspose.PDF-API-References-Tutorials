---
title: Tekening met verloopvulling toevoegen
linktitle: Tekening met verloopvulling toevoegen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekening met verloopvulling toevoegt met Aspose.PDF voor .NET. Stapsgewijze tutorial om aantrekkelijke PDF-documenten te maken.
type: docs
weight: 20
url: /nl/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In deze tutorial leiden we je stap voor stap door de volgende C#-broncode om een tekening met verloopvulling toe te voegen aan programmeren met afbeeldingen met behulp van Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Heb ook basiskennis van C#-programmering.

## Stap 1: Documentdirectory instellen

In de meegeleverde broncode moet u de directory opgeven waar u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" naar de gewenste directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentobject instantiëren en een pagina toevoegen

We maken een instantie van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject maken en toevoegen aan de pagina

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Stap 4: Rechthoekig object maken en toevoegen aan grafiek

We maken een rechthoekobject met opgegeven afmetingen en voegen het toe aan de vormverzameling van het diagram.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Stap 5: Verloopvulling configureren

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

Hierdoor ontstaat een verloop van rood naar blauw, van punt (0, 0) naar punt (300, 300).

## Stap 6: Het PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "AddDrawingWithGradientFill_out.pdf" in de opgegeven map.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Voorbeeldbroncode voor Tekening met verloopvulling toevoegen met behulp van Aspose.PDF voor .NET 

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

In deze tutorial hebben we stap voor stap uitgelegd hoe je een tekening met een gradient fill toevoegt aan programmeren met graphics met Aspose.PDF voor .NET. Nu kun je deze kennis gebruiken om aantrekkelijke PDF-documenten te maken met aangepaste ontwerpen en gradient fills.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het toevoegen van een tekening met verloopvulling aan programmeren met afbeeldingen met behulp van Aspose.PDF voor .NET.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Daarnaast wordt een basiskennis van C#-programmering aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de waarde van de variabele "dataDir" wijzigen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Wat is het doel van het Graph-object?

A: Het Graph-object dient als een container voor de tekenelementen. Het wordt gemaakt met opgegeven afmetingen en toegevoegd aan de alineaverzameling van de pagina.

#### V: Hoe kan ik een verloopvulling voor een vorm configureren?

A: Om gradient fill te configureren, kunt u de FillColor-eigenschap van de GraphInfo van een vorm instellen met behulp van de GradientAxialShading-klasse. Hiermee kunt u de begin- en eindpunten van de gradient definiëren en de kleuren waartussen de overgang moet plaatsvinden.

#### V: Kan ik de kleuren en de richting van de verloopvulling aanpassen?

A: Ja, u kunt de kleuren en de richting van de verloopvulling aanpassen door de kleurobjecten aan te passen en de begin- en eindpunten van de GradientAxialShading op te geven.

#### V: Wat is de laatste stap van de tutorial?

A: De laatste stap is het opslaan van het resulterende PDF-bestand met de naam "AddDrawingWithGradientFill_out.pdf" in de opgegeven map.

#### V: Is er een voorbeeldbroncode beschikbaar?

A: Ja, de tutorial bevat een voorbeeldbroncode die u kunt gebruiken als referentie bij het implementeren van de beschreven stappen.

#### V: Kan ik verloopvulling toepassen op andere vormen dan rechthoeken?

A: Ja, u kunt ook gradient fill op andere vormen toepassen. Het proces omvat het configureren van de FillColor-eigenschap van de GraphInfo van de vorm met behulp van de GradientAxialShading-klasse.