---
title: Tekstuitlijning voor zwevende doosinhoud in PDF-bestand
linktitle: Tekstuitlijning voor zwevende doosinhoud in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uitlijnt in zwevende vakken in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 520
url: /nl/net/programming-with-text/text-alignment-for-floating-box-contents/
---
In deze zelfstudie wordt uitgelegd hoe u tekst uitlijnt in zwevende vakken in een PDF-bestand met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

## Vereisten

Voordat u doorgaat met de zelfstudie, moet u ervoor zorgen dat u over het volgende beschikt:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd. U kunt het verkrijgen via de Aspose-website of NuGet gebruiken om het in uw project te installeren.

## Stap 1: Zet het project op

Begin met het maken van een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten

Voeg het volgende toe met behulp van richtlijnen aan het begin van uw C#-bestand om de vereiste naamruimten te importeren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Maak een nieuw document

 Maak een nieuwe`Document` voorwerp:

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## Stap 5: Maak zwevende vakken met tekstfragmenten

 Maak er meerdere`FloatingBox` objecten met verschillende verticale uitlijningen en horizontale uitlijningen:

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

 Wijzig de tekst en stijl van de`TextFragment` objecten naar wens.

## Stap 6: Sla het PDF-document op

Sla het gewijzigde PDF-document op:

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 Zorg ervoor dat u vervangt`"FloatingBox_alignment_review_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor tekstuitlijning voor zwevende doosinhoud met Aspose.PDF voor .NET 
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

Gefeliciteerd! U hebt met succes geleerd hoe u tekst binnen zwevende vakken in een PDF-document kunt uitlijnen met behulp van Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het opslaan van het gewijzigde document. U kunt deze code nu in uw eigen C#-projecten opnemen om de uitlijning van tekst in zwevende vakken in PDF-bestanden aan te passen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekstuitlijning voor zwevende boxinhoud in PDF-bestand"?

A: De tutorial "Tekstuitlijning voor zwevende kaderinhoud in PDF-bestand" is bedoeld om gebruikers te begeleiden bij het uitlijnen van tekst binnen zwevende kaders in een PDF-document met behulp van Aspose.PDF voor .NET. De zelfstudie biedt stapsgewijze instructies en C#-codevoorbeelden om het proces te demonstreren.

#### Vraag: Hoe helpt deze tutorial bij het uitlijnen van tekst binnen zwevende vakken?

A: Deze tutorial helpt gebruikers begrijpen hoe ze Aspose.PDF voor .NET kunnen gebruiken om tekst uit te lijnen in zwevende vakken in een PDF-document. Door de gegeven stappen en codevoorbeelden te volgen, kunnen gebruikers de verticale en horizontale uitlijning van tekst binnen zwevende vakken aanpassen.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Om aan de slag te gaan, maakt u een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur en voegt u een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek. Hierdoor kunt u de functies van de bibliotheek benutten voor het werken met PDF-documenten en het uitlijnen van tekst in zwevende vakken.

#### Vraag: Kan ik deze tutorial gebruiken om tekst uit te lijnen binnen elk type zwevend kader?

A: Ja, deze tutorial biedt instructies voor het uitlijnen van tekst binnen zwevende vakken in een PDF-document met Aspose.PDF voor .NET. U kunt de meegeleverde codevoorbeelden gebruiken om de verticale en horizontale uitlijning van tekst in zwevende vakken aan te passen.

#### Vraag: Hoe geef ik de uitlijning van tekst binnen een zwevend kader op?

 A: In de tutorial wordt gedemonstreerd hoe u kunt maken`FloatingBox`objecten en stel hun in`VerticalAlignment` En`HorizontalAlignment` eigenschappen om de uitlijning van de ingesloten tekst te bepalen. U kunt deze eigenschappen aanpassen aan uw wensen.

#### Vraag: Hoe kan ik het uiterlijk van de zwevende dozen aanpassen?

 A: U kunt het uiterlijk van de zwevende vakken aanpassen door eigenschappen zoals de rand, grootte en tekstinhoud te wijzigen. De tutorial biedt codevoorbeelden die laten zien hoe u de`FloatingBox` voorwerpen.

#### Vraag: Kan ik meerdere zwevende vakken met verschillende uitlijningen in hetzelfde PDF-document toevoegen?

 A: Ja, de tutorial illustreert hoe u er meerdere kunt maken`FloatingBox` objecten met verschillende verticale en horizontale uitlijningen en voeg deze toe aan hetzelfde PDF-document. Hierdoor kunt u de effecten van verschillende uitlijningen binnen hetzelfde document zien.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document?

 A: Om het gewijzigde PDF-document op te slaan, kunt u de`Save` werkwijze van de`Document` voorwerp. De zelfstudie biedt codevoorbeelden die laten zien hoe u het resulterende PDF-document kunt opslaan.