---
title: Maak een rechthoek met alfa-kleur
linktitle: Maak een rechthoek met alfa-kleur
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een rechthoek met transparante kleur maakt met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het aanpassen van transparantie.
type: docs
weight: 60
url: /nl/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om een rechthoek met alfa-kleur te maken met behulp van Aspose.PDF voor .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject en een rechthoek maken

We maken een grafiekobject met specifieke afmetingen en een rechthoek met specifieke afmetingen.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Stap 4: De alfa-kleur voor de rechthoek instellen

We kunnen een alfa-kleur voor de rechthoek specificeren met behulp van de FromArgb-methode van de klasse System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Stap 5: De rechthoek toevoegen aan het grafiekobject

We voegen de rechthoek toe aan de vormverzameling van het Graph-object.

```csharp
canvas.Shapes.Add(rect);
```

## Stap 6: Een tweede rechthoek maken met een andere alfa-kleur

We maken een tweede rechthoek met specifieke afmetingen en een andere alfakleur.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Stap 7: Het grafiekobject aan de pagina toevoegen

We voegen het Graph-object toe aan de Paragraph-verzameling van het Page-object.

```csharp
page.Paragraphs.Add(canvas);
```

## Stap 8: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "CreateRectangleWithAlphaColor_out.pdf" in de opgegeven directory.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Voorbeeldbroncode voor het maken van een rechthoek met alfa-kleur met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document-instantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
// Grafiekinstantie maken
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Maak een rechthoekig object met specifieke afmetingen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Stel de grafiekvulkleur in vanuit de System.Drawing.Color-structuur vanuit een 32-bits ARGB-waarde
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Rechthoekig object toevoegen aan vormenverzameling van grafiekinstantie
canvas.Shapes.Add(rect);
// Tweede rechthoekobject maken
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Grafiekinstantie toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u een rechthoek met alfakleur kunt maken met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met transparante kleuren te maken in uw PDF-bestanden.

## Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden door het proces van het maken van een rechthoek met alfa-kleur met behulp van Aspose.PDF voor .NET. U leert hoe u geometrische vormen met transparante kleuren toevoegt aan uw PDF-bestanden.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Daarnaast wordt een basiskennis van C#-programmering aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" aanpassen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Wat is het doel van het Graph-object en het Rectangle-object?

A: Het grafiekobject fungeert als een container voor tekenelementen, terwijl het rechthoek de geometrische vorm vertegenwoordigt die u aan de PDF toevoegt.

#### V: Hoe kan ik een alfa-kleur voor de rechthoek instellen?

 A: U kunt een alfa-kleur voor de rechthoek opgeven met behulp van de`FillColor` eigendom van de`GraphInfo` object en de`Color.FromRgb` methode met een ARGB-waarde.

#### V: Kan ik meerdere rechthoeken met verschillende alfa-kleuren maken?

A: Ja, u kunt meerdere rechthoeken met verschillende alfa-kleuren maken door vergelijkbare stappen te volgen die in de tutorial worden uitgelegd.

#### V: Hoe kan ik het resulterende PDF-bestand opslaan nadat ik rechthoeken met alfa-kleuren heb gemaakt?

 A: Nadat u de rechthoeken met alfa-kleuren hebt gemaakt, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` regel in de meegeleverde broncode.