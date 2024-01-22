---
title: Dash-lengte
linktitle: Dash-lengte
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de lengte van streepjes instelt met Aspose.PDF voor .NET. Stapsgewijze handleiding om streepjespatronen aan te passen.
type: docs
weight: 70
url: /nl/net/programming-with-graphs/dash-length/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om de lengte van streepjes in te stellen met Aspose.PDF voor .NET.

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

We voegen de lijn toe aan de vormcollectie van het Graph-object.

```csharp
canvas.Shapes.Add(line);
```

## Stap 6: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op met de naam "DashLength_out.pdf" in de opgegeven map.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Voorbeeldbroncode voor Dash Length met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantie van documentinstantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van Document-object
Page page = doc.Pages.Add();
// Maak een tekenobject met bepaalde afmetingen
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Voeg een tekenobject toe aan de alineaverzameling van een pagina-instantie
page.Paragraphs.Add(canvas);
// Lijnobject maken
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Kleur instellen voor lijnobject
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Geef een dash-array op voor het lijnobject
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Stel de streepjesfase in voor Line-instantie
line.GraphInfo.DashPhase = 1;
// Voeg een lijn toe aan de vormenverzameling van tekenobjecten
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF-document opslaan
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe je de lengte van streepjes instelt met Aspose.PDF voor .NET. Nu kunt u deze kennis gebruiken om lijnen met aangepaste streepjespatronen in uw PDF-bestanden te maken.

## Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Het doel van deze tutorial is om u te begeleiden bij het instellen van de lengte van streepjes voor lijnen met behulp van Aspose.PDF voor .NET. U leert hoe u lijnen met aangepaste streepjespatronen in uw PDF-bestanden kunt maken.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Een basiskennis van programmeren in C# wordt ook aanbevolen.

#### Vraag: Hoe geef ik de map op waarin het PDF-bestand moet worden opgeslagen?

A: Wijzig de variabele "dataDir" in de meegeleverde broncode om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### Vraag: Hoe maak ik een lijn met aangepaste streepjespatronen?

 A: In de tutorial wordt gedemonstreerd hoe u een Line-object maakt en de kleur, streepjesreeks en streepjesfase configureert met behulp van de`GraphInfo` voorwerp. Wijzig deze instellingen om het gewenste streepjespatroon te bereiken.

#### Vraag: Kan ik de kleur van de lijn aanpassen?

 A: Ja, u kunt de kleur van de lijn aanpassen door de`Color` eigendom van de`GraphInfo` object dat aan de lijn is gekoppeld.

#### Vraag: Hoe bewaar ik het PDF-document nadat ik de streepjeslengte heb ingesteld?

 A: Nadat u het Line-object met het gewenste streepjespatroon hebt geconfigureerd, kunt u het resulterende PDF-document opslaan met behulp van de`doc.Save(dataDir + "DashLength_out.pdf");` regel in de opgegeven broncode.