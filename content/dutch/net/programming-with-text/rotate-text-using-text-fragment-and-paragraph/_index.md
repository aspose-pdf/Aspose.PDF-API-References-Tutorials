---
title: Roteer tekst met behulp van tekstfragmenten en alinea's
linktitle: Roteer tekst met behulp van tekstfragmenten en alinea's
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt roteren met behulp van tekstfragmenten en alinea's in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 400
url: /nl/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
In deze tutorial wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om tekst te roteren met behulp van tekstfragmenten en alinea's. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

## Stap 3: Maak het PDF-document

 Initialiseer de`Document` object om een nieuw PDF-document te maken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Zorg ervoor dat u vervangt`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Voeg een pagina toe

 Haal een bepaalde pagina uit het document op met behulp van de`Pages.Add()` methode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Stap 5: Maak tekstfragmenten

 Maak er meerdere`TextFragment` objecten, stel hun tekst en eigenschappen in en specificeer de rotatiehoek:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Pas de tekst, rotatiehoek en andere eigenschappen naar wens aan.

## Stap 6: Voeg tekstfragmenten toe aan de pagina

 Voeg de gemaakte tekstfragmenten toe aan de pagina door ze toe te voegen aan het`Paragraphs` verzameling:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Stap 7: Sla het PDF-document op

 Sla het gewijzigde PDF-document op in een bestand met behulp van de`Save` methode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Zorg ervoor dat u vervangt`"TextFragmentTests_Rotated3_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor het roteren van tekst met behulp van tekstfragmenten en alinea's met Aspose.PDF voor .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiseer het documentobject
Document pdfDocument = new Document();
// Krijg een specifieke pagina
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Maak een tekstfragment
TextFragment textFragment1 = new TextFragment("main text");
// Teksteigenschappen instellen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Maak een tekstfragment
TextFragment textFragment2 = new TextFragment("rotated text");
// Teksteigenschappen instellen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotatie instellen
textFragment2.TextState.Rotation = 315;
// Maak een tekstfragment
TextFragment textFragment3 = new TextFragment("rotated text");
// Teksteigenschappen instellen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotatie instellen
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Bewaar document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u tekst kunt roteren met behulp van tekstfragmenten en alinea's in een PDF-document met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het maken van het document tot het opslaan van de gewijzigde versie. U kunt deze code nu in uw eigen C#-projecten opnemen om tekstrotatie in PDF-bestanden te manipuleren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekst roteren met tekstfragmenten en alinea's"?

A: De tutorial "Tekst roteren met tekstfragment en alinea" is bedoeld om u te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om tekst te roteren met behulp van zowel tekstfragmenten als alinea's in een PDF-document. De tutorial biedt stapsgewijze instructies en voorbeeldcode om deze functionaliteit te bereiken.

#### Vraag: Waarin verschilt deze tutorial van de vorige tutorials over tekstrotatie?

A: Deze tutorial combineert het gebruik van tekstfragmenten en alinea's om tekstrotatie binnen een PDF-document te bewerkstelligen. Het laat zien hoe u tekstfragmenten afzonderlijk kunt roteren en ze vervolgens aan een pagina kunt toevoegen`Paragraphs` verzameling om een uitgebreider tekstrotatie-effect te bereiken.

#### Vraag: Wat zijn de voordelen van het gebruik van tekstfragmenten en alinea's voor tekstrotatie?

A: Het samen gebruiken van tekstfragmenten en alinea's zorgt voor meer flexibiliteit bij het roteren van de tekst. Tekstfragmenten maken individuele rotatie- en opmaakinstellingen mogelijk, terwijl alinea's structuur bieden voor het ordenen en positioneren van tekstfragmenten binnen een pagina.

#### Vraag: Kan ik verschillende rotatiehoeken toepassen op verschillende tekstfragmenten binnen dezelfde alinea?

 A: Ja, u kunt verschillende rotatiehoeken toepassen op verschillende`TextFragment` objecten binnen dezelfde alinea. Voor elk tekstfragment kan een eigen rotatiehoek worden opgegeven met behulp van de`TextState.Rotation` eigendom.

#### Vraag: Is het mogelijk om met deze methode complexe tekstrotatie-effecten te bereiken?

A: Ja, door tekstfragmenten met verschillende rotatiehoeken te combineren en deze binnen alinea's te rangschikken, kunt u complexe en aangepaste tekstrotatie-effecten bereiken, waardoor de visuele aantrekkingskracht van uw PDF-documenten wordt vergroot.

#### Vraag: Welke stappen zijn nodig bij het roteren van tekst met behulp van tekstfragmenten en alinea's?

A: De stappen omvatten:

1. Stel het project in door een nieuw C#-project te maken en een verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe te voegen.
2. Het PDF-document maken en een pagina toevoegen.
3. Tekstfragmenten maken, hun eigenschappen instellen en rotatiehoeken opgeven.
4.  Tekstfragmenten aan de pagina toevoegen met behulp van de`Paragraphs` verzameling.
5. Het gewijzigde PDF-document opslaan.

#### Vraag: Kan ik rotatie op hele alinea's toepassen?

 A: Ja, u kunt rotatie op hele alinea's toepassen door de`TextState.Rotation` eigenschap van de alinea zelf. Hierdoor worden alle tekstfragmenten binnen die alinea geroteerd.