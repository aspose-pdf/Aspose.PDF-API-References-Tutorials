---
title: Zoek tekst en teken een rechthoek
linktitle: Zoek tekst en teken een rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekst in een PDF kunt zoeken, rechthoeken rond de gevonden tekst kunt tekenen en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET.
type: docs
weight: 460
url: /nl/net/programming-with-text/search-text-and-draw-rectangle/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om naar specifieke tekst in een PDF-document te zoeken, een rechthoek rond de gevonden tekst te tekenen en het gewijzigde document op te slaan. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Vervangen`"SearchAndGetTextFromAll.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 5: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle exemplaren van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Vervangen`@"[\S]+"` met uw gewenste reguliere expressiepatroon.

## Stap 6: Schakel zoeken naar reguliere expressies in

 Schakel het zoeken naar reguliere expressies in door de`TextSearchOptions` eigenschap van de absorber:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Stap 7: Zoek op alle pagina's

Accepteer de absorber voor alle pagina's van het document:

```csharp
document.Pages.Accept(textAbsorber);
```

## Stap 8: Teken een rechthoek rond de gevonden tekst

 Maak een`PdfContentEditor` object en loop door de opgehaalde tekstfragmenten, waarbij u een rechthoek rond elk tekstsegment tekent:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Stap 9: Sla het gewijzigde document op

Sla het gewijzigde document op:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Zorg ervoor dat u vervangt`"SearchTextAndDrawRectangle_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor het zoeken naar tekst en het tekenen van een rechthoek met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u naar specifieke tekst in een PDF-document kunt zoeken, een rechthoek rond de gevonden tekst kunt tekenen en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het uitvoeren van de vereiste acties. U kunt deze code nu in uw eigen C#-projecten opnemen om tekst te manipuleren en rechthoeken in PDF-bestanden te tekenen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Tekst zoeken en rechthoek tekenen"?

A: De tutorial "Tekst zoeken en rechthoek tekenen" is bedoeld om gebruikers te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om naar specifieke tekst in een PDF-document te zoeken, rechthoeken rond de gevonden tekstsegmenten te tekenen en de gewijzigde tekst op te slaan. document. De tutorial biedt gedetailleerde instructies en C#-codevoorbeelden om elke stap van het proces te illustreren.

#### Vraag: Hoe helpt deze tutorial bij het tekenen van rechthoeken rond specifieke tekst in een PDF-document?

A: Deze tutorial biedt een uitgebreide handleiding voor het lokaliseren en tekenen van rechthoeken rond specifieke tekstsegmenten in een PDF-document. Het demonstreert het proces van het opzetten van een project, het laden van een PDF-document, het inschakelen van zoeken in reguliere expressies, het tekenen van rechthoeken rond gevonden tekstsegmenten en het opslaan van de gewijzigde PDF.

#### Vraag: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de zelfstudie begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet de Aspose.PDF voor .NET-bibliotheek zijn geïnstalleerd. U kunt het verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Begin met het maken van een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur. Voeg vervolgens een verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe aan uw project. Hierdoor kunt u de functionaliteit van de bibliotheek gebruiken om PDF-documenten te manipuleren.

#### Vraag: Kan ik met deze tutorial rechthoeken rond specifieke tekst tekenen?

A: Ja, de tutorial richt zich op het tekenen van rechthoeken rond specifieke tekstsegmenten in een PDF-document. Het laat zien hoe u de gewenste tekst kunt lokaliseren met behulp van reguliere expressies, rechthoeken rond de geïdentificeerde tekstsegmenten kunt maken en de gewijzigde PDF kunt opslaan.

#### Vraag: Hoe kan ik de tekst opgeven waarnaar ik wil zoeken en hoe kan ik er rechthoeken omheen tekenen?

 A: Om de tekst op te geven waarnaar u wilt zoeken en er rechthoeken omheen te tekenen, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`@"[\S]+"` in de code van de tutorial met het gewenste reguliere-expressiepatroon.

#### Vraag: Hoe schakel ik zoeken in reguliere expressies naar tekst in?

 A: Zoeken in reguliere expressies wordt mogelijk gemaakt door een`TextSearchOptions` object en de waarde ervan instellen`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere expressiepatroon wordt gebruikt tijdens het zoeken naar tekst.

#### Vraag: Hoe teken ik rechthoeken rond de gevonden tekst?

 A: Na het identificeren van de tekstsegmenten met behulp van de`TextFragmentAbsorber` , biedt de zelfstudie een lus waarmee u deze segmenten kunt doorlopen. Voor elk tekstsegment laat de tutorial zien hoe u er een rechthoek omheen kunt maken met behulp van de`DrawBox` methode en specificeer het uiterlijk van de rechthoek.

#### Vraag: Wat zijn de stappen om de gewijzigde PDF met getekende rechthoeken op te slaan?

A: Nadat u rechthoeken rond de gewenste tekstsegmenten heeft getekend, gebruikt u de`Document` klasse`Save` methode om het gewijzigde document op te slaan. De voorbeeldcode van de tutorial laat zien hoe u de bewerkte PDF kunt opslaan en een succesbericht kunt weergeven.

#### Vraag: Kan ik het uiterlijk van de getekende rechthoeken aanpassen?

 A: Ja, u kunt het uiterlijk van de getekende rechthoeken aanpassen. In de voorbeeldcode van de zelfstudie wordt de`DrawBox` methode wordt gebruikt om rechthoeken te maken. U kunt eigenschappen zoals kleur, stijl en dikte wijzigen om het uiterlijk van de getekende rechthoeken aan te passen.