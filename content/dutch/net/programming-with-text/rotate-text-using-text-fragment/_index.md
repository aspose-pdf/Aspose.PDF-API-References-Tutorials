---
title: Tekst roteren met behulp van een tekstfragment in een PDF-bestand
linktitle: Tekst roteren met behulp van een tekstfragment in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt roteren met behulp van tekstfragmenten in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 390
url: /nl/net/programming-with-text/rotate-text-using-text-fragment/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om tekst te roteren met behulp van tekstfragmenten in een PDF-bestand. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using Aspose.Pdf.Text.TextBuilder;
```

## Stap 3: Maak het PDF-document

 Initialiseer de`Document` object om een nieuw PDF-document te maken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Een pagina toevoegen

 Haal een bepaalde pagina uit het document met behulp van de`Pages.Add()` methode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Stap 5: Tekstfragmenten maken

 Meerdere maken`TextFragment` objecten, stel hun tekst en eigenschappen in en specificeer hun posities op de pagina:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Pas de tekst, posities en andere eigenschappen naar wens aan.

## Stap 6: Maak een TextBuilder en voeg tekstfragmenten toe

 Maak een`TextBuilder` object met behulp van de`pdfPage` en voeg de tekstfragmenten toe aan de PDF-pagina:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Stap 7: Sla het PDF-document op

 Sla het gewijzigde PDF-document op in een bestand met behulp van de`Save` methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Zorg ervoor dat u vervangt`"TextFragmentTests_Rotated1_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Rotate Text Using Text Fragment met Aspose.PDF voor .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentobject initialiseren
Document pdfDocument = new Document();
// Specifieke pagina ophalen
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tekstfragment maken
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Teksteigenschappen instellen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Maak een gedraaid tekstfragment
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Teksteigenschappen instellen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Maak een gedraaid tekstfragment
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Teksteigenschappen instellen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// TextBuilder-object maken
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Voeg het tekstfragment toe aan de PDF-pagina
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Document opslaan
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst kunt roteren met behulp van tekstfragmenten in een PDF-document met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het maken van het document tot het opslaan van de gewijzigde versie. U kunt deze code nu opnemen in uw eigen C#-projecten om tekstrotatie in PDF-bestanden te manipuleren.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Tekst roteren met behulp van een tekstfragment'?

A: De tutorial "Rotate Text Using Text Fragment" is bedoeld om u te begeleiden bij het proces van het gebruiken van de Aspose.PDF-bibliotheek voor .NET om tekst te roteren met behulp van tekstfragmenten in een PDF-document. De tutorial biedt stapsgewijze instructies en voorbeeldcode om deze functionaliteit te bereiken.

#### V: Wat wordt bedoeld met "roterende tekst met behulp van tekstfragmenten"?

A: Roteren van tekst met behulp van tekstfragmenten verwijst naar de mogelijkheid om rotatie toe te passen op individuele tekstfragmenten binnen een PDF-document met behulp van de Aspose.PDF-bibliotheek. Met deze techniek kunt u de oriëntatie van tekst in verschillende hoeken of posities binnen de PDF-inhoud regelen.

#### V: Waarom zou ik tekstfragmenten in een PDF-document willen roteren?

A: Het roteren van tekstfragmenten in een PDF-document kan voor verschillende doeleinden nuttig zijn, bijvoorbeeld om specifieke inhoud te benadrukken, artistieke ontwerpen te maken of de lay-out en leesbaarheid te verbeteren.

#### V: Hoe stel ik het project voor de tutorial in?

A: Om het project op te zetten:

1. Maak een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE).
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.
3. Voeg de benodigde using-richtlijnen toe aan uw C#-bestand.

#### V: Hoe kan ik een nieuw PDF-document maken?

 A: Om een nieuw PDF-document te maken, initialiseert u een`Document`object uit de Aspose.PDF-bibliotheek. U kunt dit object gebruiken om pagina's en inhoud aan de PDF toe te voegen.

#### V: Hoe kan ik tekstfragmenten roteren met behulp van tekstfragmenten?

A: Om tekstfragmenten te roteren met behulp van tekstfragmenten:

1.  Creëren`TextFragment` objecten.
2. Stel de tekst en eigenschappen van de tekstfragmenten in.
3. Geef de posities van de tekstfragmenten op de pagina op.
4.  Stel de rotatiehoek in met behulp van de`TextState.Rotation` eigenschap van de tekstfragmenten.
5.  Maak een`TextBuilder`object en voeg de tekstfragmenten toe aan de PDF-pagina.

#### V: Kan ik verschillende rotatiehoeken toepassen op verschillende tekstfragmenten?

 A: Ja, u kunt verschillende rotatiehoeken toepassen op verschillende`TextFragment` objecten. Elk tekstfragment kan een eigen rotatiehoek hebben die is opgegeven met behulp van de`TextState.Rotation` eigendom.

#### V: Hoe kan ik het PDF-document met geroteerde tekstfragmenten opslaan?

 A: Om het PDF-document met geroteerde tekstfragmenten op te slaan, gebruikt u de`Save` methode van de`Document` object en geef het gewenste pad en de gewenste naam van het uitvoerbestand op.