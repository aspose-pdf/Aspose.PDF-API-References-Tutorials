---
title: Tekst roteren met behulp van tekstfragment en alinea
linktitle: Tekst roteren met behulp van tekstfragment en alinea
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst kunt roteren met behulp van tekstfragmenten en alinea's in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 400
url: /nl/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om tekst te roteren met behulp van tekstfragmenten en alinea's. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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

 Meerdere maken`TextFragment` objecten, stel hun tekst en eigenschappen in en geef de rotatiehoek op:

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

 Voeg de gemaakte tekstfragmenten toe aan de pagina door ze toe te voegen aan de`Paragraphs` verzameling:

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

 Zorg ervoor dat u vervangt`"TextFragmentTests_Rotated3_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Rotate Text Using Text Fragment And Paragraph met behulp van Aspose.PDF voor .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentobject initialiseren
Document pdfDocument = new Document();
// Specifieke pagina ophalen
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Tekstfragment maken
TextFragment textFragment1 = new TextFragment("main text");
// Teksteigenschappen instellen
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Tekstfragment maken
TextFragment textFragment2 = new TextFragment("rotated text");
// Teksteigenschappen instellen
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotatie instellen
textFragment2.TextState.Rotation = 315;
// Tekstfragment maken
TextFragment textFragment3 = new TextFragment("rotated text");
// Teksteigenschappen instellen
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Rotatie instellen
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Document opslaan
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusie

Gefeliciteerd! U hebt succesvol geleerd hoe u tekst kunt roteren met behulp van tekstfragmenten en alinea's in een PDF-document met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het maken van het document tot het opslaan van de gewijzigde versie. U kunt deze code nu opnemen in uw eigen C#-projecten om tekstrotatie in PDF-bestanden te manipuleren.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Tekst roteren met behulp van tekstfragmenten en alinea's"?

A: De tutorial "Rotate Text Using Text Fragment And Paragraph" is bedoeld om u te begeleiden bij het proces van het gebruiken van de Aspose.PDF-bibliotheek voor .NET om tekst te roteren met behulp van zowel tekstfragmenten als paragrafen binnen een PDF-document. De tutorial biedt stapsgewijze instructies en voorbeeldcode om deze functionaliteit te bereiken.

#### V: Waarin verschilt deze tutorial van de vorige tutorials over tekstrotatie?

A: Deze tutorial combineert het gebruik van tekstfragmenten en paragrafen om tekstrotatie binnen een PDF-document te bereiken. Het laat zien hoe u tekstfragmenten individueel roteert en ze vervolgens aan een pagina toevoegt`Paragraphs` verzameling om een uitgebreider tekstrotatie-effect te bereiken.

#### V: Wat zijn de voordelen van het gebruik van tekstfragmenten en paragrafen voor tekstrotatie?

A: Door tekstfragmenten en paragrafen samen te gebruiken, is er meer flexibiliteit in tekstrotatie. Tekstfragmenten maken individuele rotatie- en opmaakinstellingen mogelijk, terwijl paragrafen structuur bieden voor het ordenen en positioneren van tekstfragmenten binnen een pagina.

#### V: Kan ik verschillende rotatiehoeken toepassen op verschillende tekstfragmenten binnen dezelfde alinea?

 A: Ja, u kunt verschillende rotatiehoeken toepassen op verschillende`TextFragment` objecten binnen dezelfde alinea. Elk tekstfragment kan een eigen rotatiehoek hebben die is opgegeven met behulp van de`TextState.Rotation` eigendom.

#### V: Is het mogelijk om met deze methode complexe tekstrotatie-effecten te bereiken?

A: Ja, door tekstfragmenten met verschillende rotatiehoeken te combineren en ze binnen alinea's te rangschikken, kunt u complexe en aangepaste tekstrotatie-effecten bereiken. Hierdoor worden uw PDF-documenten visueel aantrekkelijker.

#### V: Welke stappen zijn er nodig om tekst te roteren met behulp van tekstfragmenten en paragrafen?

A: De stappen omvatten:

1. Het project instellen door een nieuw C#-project te maken en een verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe te voegen.
2. Het PDF-document maken en een pagina toevoegen.
3. Tekstfragmenten maken, hun eigenschappen instellen en rotatiehoeken specificeren.
4.  Tekstfragmenten toevoegen aan de pagina met behulp van de`Paragraphs` verzameling.
5. Het gewijzigde PDF-document opslaan.

#### V: Kan ik rotatie toepassen op hele alinea's?

 A: Ja, u kunt rotatie toepassen op hele alinea's door de`TextState.Rotation` eigenschap van de alinea zelf. Dit zal alle tekstfragmenten binnen die alinea roteren.