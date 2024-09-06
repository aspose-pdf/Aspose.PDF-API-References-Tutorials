---
title: Tekstuitlijning voor zwevende vakinhoud in PDF-bestand
linktitle: Tekstuitlijning voor zwevende vakinhoud in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst in zwevende vakken in een PDF-bestand kunt uitlijnen met Aspose.PDF voor .NET.
type: docs
weight: 520
url: /nl/net/programming-with-text/text-alignment-for-floating-box-contents/
---
Deze tutorial legt uit hoe u tekst in zwevende vakken in een PDF-bestand kunt uitlijnen met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u verdergaat met de tutorial, moet u ervoor zorgen dat u het volgende hebt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen van de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Het project opzetten

Begin met het maken van een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg de volgende using-richtlijnen toe aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Maak een nieuw document

 Maak een nieuwe`Document` voorwerp:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Stap 5: Maak zwevende vakken met tekstfragmenten

 Meerdere maken`FloatingBox` objecten met verschillende verticale en horizontale uitlijningen:

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

 Wijzig de tekst en de stijl van de`TextFragment` objecten zoals gewenst.

## Stap 6: Sla het PDF-document op

Sla het gewijzigde PDF-document op:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Zorg ervoor dat u vervangt`"FloatingBox_alignment_review_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor tekstuitlijning voor zwevende vakinhoud met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst in zwevende vakken in een PDF-document kunt uitlijnen met Aspose.PDF voor .NET. Deze tutorial bevat een stapsgewijze handleiding, van het instellen van het project tot het opslaan van het gewijzigde document. U kunt deze code nu opnemen in uw eigen C#-projecten om de uitlijning van tekst in zwevende vakken in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Tekstuitlijning voor zwevende vakinhoud in PDF-bestand'?

A: De tutorial "Tekstuitlijning voor zwevende vakinhoud in PDF-bestand" is bedoeld om gebruikers te begeleiden bij het uitlijnen van tekst in zwevende vakken in een PDF-document met behulp van Aspose.PDF voor .NET. De tutorial biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### V: Hoe helpt deze tutorial bij het uitlijnen van tekst in zwevende vakken?

A: Deze tutorial helpt gebruikers te begrijpen hoe ze Aspose.PDF voor .NET kunnen gebruiken om tekst in zwevende vakken in een PDF-document uit te lijnen. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers de verticale en horizontale uitlijning van tekst in zwevende vakken aanpassen.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om te beginnen, maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE) en voeg een referentie toe aan de Aspose.PDF voor .NET-bibliotheek. Hiermee kunt u de functies van de bibliotheek gebruiken voor het werken met PDF-documenten en het uitlijnen van tekst binnen zwevende vakken.

#### V: Kan ik deze tutorial gebruiken om tekst in elk type zwevend vak uit te lijnen?

A: Ja, deze tutorial geeft instructies over hoe u tekst in zwevende vakken in een PDF-document kunt uitlijnen met Aspose.PDF voor .NET. U kunt de meegeleverde codevoorbeelden gebruiken om de verticale en horizontale uitlijning van tekst in zwevende vakken aan te passen.

#### V: Hoe geef ik de uitlijning van tekst in een zwevend vak op?

 A: De tutorial laat zien hoe je een`FloatingBox`objecten en stel hun`VerticalAlignment` En`HorizontalAlignment` eigenschappen om de uitlijning van de opgenomen tekst te regelen. U kunt deze eigenschappen aanpassen aan uw vereisten.

#### V: Hoe kan ik het uiterlijk van de zwevende vakken aanpassen?

 A: U kunt het uiterlijk van de zwevende vakken aanpassen door eigenschappen zoals de rand, grootte en tekstinhoud te wijzigen. De tutorial biedt codevoorbeelden die laten zien hoe u de`FloatingBox` objecten.

#### V: Kan ik meerdere zwevende vakken met verschillende uitlijningen toevoegen aan hetzelfde PDF-document?

 A: Ja, de tutorial laat zien hoe je meerdere`FloatingBox` objecten met verschillende verticale en horizontale uitlijningen en voeg ze toe aan hetzelfde PDF-document. Hiermee kunt u de effecten van verschillende uitlijningen binnen hetzelfde document zien.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan?

 A: Om het gewijzigde PDF-document op te slaan, kunt u de`Save` methode van de`Document` object. De tutorial biedt codevoorbeelden die laten zien hoe u het resulterende PDF-document kunt opslaan.