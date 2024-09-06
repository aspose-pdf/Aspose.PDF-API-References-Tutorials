---
title: Lengte streepje
linktitle: Lengte streepje
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de lengte van streepjes instelt met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het aanpassen van streepjespatronen.
type: docs
weight: 70
url: /nl/net/programming-with-graphs/dash-length/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om de lengte van streepjes in te stellen met Aspose.PDF voor .NET.

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

## Stap 3: Een grafiekobject maken en aan de pagina toevoegen

We maken een Graph-object met opgegeven afmetingen en voegen dit toe aan de alineaverzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Stap 4: Een lijnobject maken en configureren

We maken een Line-object met de opgegeven coördinaten en configureren de kleur en lengte van de streepjes.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Stap 5: De lijn toevoegen aan het grafiekobject

We voegen de lijn toe aan de vormverzameling van het Graph-object.

```csharp
canvas.Shapes.Add(line);
```

## Stap 6: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "DashLength_out.pdf" in de opgegeven directory.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Voorbeeldbroncode voor Dash Length met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-instantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van Document-object
Page page = doc.Pages.Add();
// Tekenobject met bepaalde afmetingen maken
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Tekenobject toevoegen aan alineaverzameling van pagina-instantie
page.Paragraphs.Add(canvas);
// Lijnobject maken
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Kleur instellen voor Lijn-object
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Geef een dash-array op voor een lijnobject
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Stel de streepjesfase in voor het Line-exemplaar
line.GraphInfo.DashPhase = 1;
// Lijn toevoegen aan vormenverzameling van tekenobject
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u de lengte van streepjes instelt met Aspose.PDF voor .NET. Nu kunt u deze kennis gebruiken om lijnen met aangepaste streepjespatronen in uw PDF-bestanden te maken.

## Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden door het proces van het instellen van de lengte van streepjes voor lijnen met behulp van Aspose.PDF voor .NET. U leert hoe u lijnen met aangepaste streepjespatronen in uw PDF-bestanden kunt maken.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Een basiskennis van C#-programmering wordt ook aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: Wijzig de variabele "dataDir" in de meegeleverde broncode om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Hoe maak ik een lijn met aangepaste streepjespatronen?

 A: De tutorial laat zien hoe je een Line-object kunt maken en de kleur, de streepjesmatrix en de streepjesfase kunt configureren met behulp van de`GraphInfo` object. Wijzig deze instellingen om het gewenste streepjespatroon te verkrijgen.

#### V: Kan ik de kleur van de lijn aanpassen?

 A: Ja, u kunt de kleur van de lijn aanpassen door de`Color` eigendom van de`GraphInfo` object dat aan de lijn is gekoppeld.

#### V: Hoe kan ik het PDF-document opslaan nadat ik de streepjeslengte heb ingesteld?

 A: Nadat u het Line-object hebt geconfigureerd met het gewenste streepjespatroon, kunt u het resulterende PDF-document opslaan met behulp van de`doc.Save(dataDir + "DashLength_out.pdf");` regel in de meegeleverde broncode.