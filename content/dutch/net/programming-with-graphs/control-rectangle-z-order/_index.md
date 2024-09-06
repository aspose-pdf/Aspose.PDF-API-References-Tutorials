---
title: Besturingselement Rechthoek Z-volgorde in PDF-bestand
linktitle: Besturingselement Rechthoek Z-volgorde in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de Z-volgorde van rechthoeken in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-graphs/control-rectangle-z-order/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om de Z-volgorde van rechthoeken te bepalen met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Heb ook basiskennis van C#-programmering.

## Stap 1: Documentdirectory instellen

In de meegeleverde broncode moet u de directory opgeven waar u het resulterende PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" naar de gewenste directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentobject instantiëren en een pagina toevoegen

We maken een instantie van de klasse Document en voegen een pagina toe aan dit document.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Stap 3: De paginagrootte instellen

We stellen de PDF-paginagrootte in met de SetPageSize-methode.

```csharp
page1.SetPageSize(375, 300);
```

## Stap 4: Paginamarges instellen

We kunnen de paginamarges configureren met behulp van de eigenschappen van het PageInfo-object.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Stap 5: Rechthoeken toevoegen met de opgegeven Z-volgorde

We maken rechthoeken aan op de pagina met verschillende kleuren en opgegeven Z-volgordes.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Stap 6: Het resulterende PDF-bestand opslaan

Ten slotte slaan we het resulterende PDF-bestand op onder de naam "ControlRectangleZOrder_out.pdf" in de opgegeven map.

```csharp
doc1.Save(dataDir);
```
### Voorbeeldbroncode voor Control Rectangle Z Order met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantieer Document klasse object
Document doc1 = new Document();
/// Voeg pagina toe aan paginaverzameling van PDF-bestand
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Grootte van PDF-pagina instellen
page1.SetPageSize(375, 300);
// Linkermarge voor pagina-object instellen op 0
page1.PageInfo.Margin.Left = 0;
// Stel de bovenmarge van het pagina-object in op 0
page1.PageInfo.Margin.Top = 0;
//Maak een nieuwe rechthoek met Kleur als Rood, Z-volgorde als 0 en bepaalde afmetingen
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Maak een nieuwe rechthoek met Kleur als Blauw, Z-volgorde als 0 en bepaalde afmetingen
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Maak een nieuwe rechthoek met Kleur als Groen, Z-volgorde als 0 en bepaalde afmetingen
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Resulterend PDF-bestand opslaan
doc1.Save(dataDir);

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u de Z-volgorde van rechthoeken kunt regelen met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om rechthoeken in uw PDF-bestanden nauwkeurig te ordenen en te layeren.

### FAQ's controle rechthoek z-volgorde in PDF-bestand

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial is bedoeld om u te begeleiden bij het proces van het regelen van de Z-volgorde van rechthoeken met behulp van Aspose.PDF voor .NET, zodat u rechthoeken in uw PDF-bestanden kunt ordenen en in lagen kunt aanbrengen.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Daarnaast wordt een basiskennis van C#-programmering aanbevolen.

#### V: Hoe geef ik de map op waar het PDF-bestand moet worden opgeslagen?

A: In de meegeleverde broncode kunt u de variabele "dataDir" aanpassen om de map aan te geven waar u het resulterende PDF-bestand wilt opslaan.

#### V: Wat is het doel van het instellen van de paginagrootte en marges?

A: Door het instellen van het paginaformaat en de marges kunt u de lay-out van de PDF-pagina configureren en beschikt u over een canvas waarop u de rechthoeken kunt rangschikken.

#### V: Hoe voeg ik rechthoeken toe met de opgegeven Z-volgorde?

A: U kunt rechthoeken maken en toevoegen aan de pagina met behulp van de`AddRectangle` methode, waarbij de positie, afmetingen, kleur en Z-volgorde voor elke rechthoek worden gespecificeerd.

#### V: Wat is Z-orde en waarom is het belangrijk?

A: Z-order bepaalt de stapelvolgorde van objecten op een pagina. Objecten met hogere Z-orderwaarden worden boven op objecten met lagere Z-orderwaarden geplaatst, wat hun zichtbaarheid en gelaagdheid beïnvloedt.

#### V: Kan ik de kleuren en afmetingen van de rechthoeken aanpassen?

 A: Ja, u kunt de kleuren, posities en afmetingen van de rechthoeken aanpassen door de parameters die aan de rechthoek worden doorgegeven te wijzigen.`AddRectangle` methode.

#### V: Hoe kan ik het resulterende PDF-bestand opslaan nadat ik de rechthoeken heb gerangschikt?

 A: Nadat u de rechthoeken hebt gerangschikt, kunt u het resulterende PDF-bestand opslaan met behulp van de`doc1.Save(dataDir);` regel in de meegeleverde broncode.