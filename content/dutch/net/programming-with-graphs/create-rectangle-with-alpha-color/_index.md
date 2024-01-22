---
title: Creëer een rechthoek met alfakleur
linktitle: Creëer een rechthoek met alfakleur
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een rechthoek met transparante kleur maakt met Aspose.PDF voor .NET. Stapsgewijze handleiding om de transparantie aan te passen.
type: docs
weight: 60
url: /nl/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om een rechthoek met alfakleur te maken met behulp van Aspose.PDF voor .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Stap 3: Een grafiekobject en een rechthoek maken

We maken een Graph-object met gespecificeerde afmetingen en een rechthoek met specifieke afmetingen.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Stap 4: De alfakleur voor de rechthoek instellen

We kunnen een alfakleur voor de rechthoek opgeven met behulp van de FromArgb-methode van de klasse System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Stap 5: De rechthoek toevoegen aan het grafiekobject

We voegen de rechthoek toe aan de vormcollectie van het Graph-object.

```csharp
canvas.Shapes.Add(rect);
```

## Stap 6: Een tweede rechthoek maken met een andere alfakleur

We creëren een tweede rechthoek met specifieke afmetingen en een andere alfakleur.

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

Ten slotte slaan we het resulterende PDF-bestand op met de naam "CreateRectangleWithAlphaColor_out.pdf" in de opgegeven map.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Voorbeeldbroncode voor Rechthoek maken met alfakleur met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantie van documentinstantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
Aspose.Pdf.Page page = doc.Pages.Add();
// Maak een Graph-instantie
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Maak een rechthoekig object met specifieke afmetingen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Stel de grafiekvulkleur in vanuit de System.Drawing.Color-structuur op basis van een 32-bits ARGB-waarde
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Voeg een rechthoekig object toe aan de vormenverzameling van de Graph-instantie
canvas.Shapes.Add(rect);
// Maak een tweede rechthoekig object
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Voeg een grafiekinstantie toe aan de alineaverzameling van het paginaobject
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusie

In deze zelfstudie hebben we uitgelegd hoe u een rechthoek met alfakleur kunt maken met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om geometrische vormen met transparante kleuren in uw PDF-bestanden te maken.

## Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u door het proces te leiden van het maken van een rechthoek met alfakleur met behulp van Aspose.PDF voor .NET. U leert hoe u geometrische vormen met transparante kleuren aan uw PDF-bestanden kunt toevoegen.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Bovendien wordt een basiskennis van C#-programmeren aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" wijzigen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Wat is het doel van het Graph-object en de rechthoek?

A: Het Graph-object fungeert als container voor tekenelementen, terwijl de rechthoek de geometrische vorm vertegenwoordigt die u aan de PDF gaat toevoegen.

#### Vraag: Hoe kan ik een alfakleur voor de rechthoek instellen?

A: U kunt een alfakleur voor de rechthoek opgeven met behulp van de`FillColor` eigendom van de`GraphInfo` voorwerp en de`Color.FromRgb` methode met een ARGB-waarde.

#### Vraag: Kan ik meerdere rechthoeken maken met verschillende alfakleuren?

A: Ja, u kunt meerdere rechthoeken met verschillende alfakleuren maken door vergelijkbare stappen te volgen zoals gedemonstreerd in de zelfstudie.

#### Vraag: Hoe bewaar ik het resulterende PDF-bestand nadat ik rechthoeken met alfakleuren heb gemaakt?

 A: Nadat u de rechthoeken met alfakleuren hebt gemaakt, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` regel in de opgegeven broncode.