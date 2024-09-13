---
title: Zoek tekst en teken rechthoek
linktitle: Zoek tekst en teken rechthoek
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekst in een PDF zoekt, rechthoeken rond de gevonden tekst tekent en het gewijzigde document opslaat met Aspose.PDF voor .NET.
type: docs
weight: 460
url: /nl/net/programming-with-text/search-text-and-draw-rectangle/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken naar specifieke tekst in een PDF-document, een rechthoek rond de gevonden tekst te tekenen en het gewijzigde document op te slaan. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Laad het PDF-document

 Laad het PDF-document met behulp van de`Document` klas:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Vervangen`"SearchAndGetTextFromAll.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 5: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle instanties van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Vervangen`@"[\S]+"` met het door u gewenste reguliere-expressiepatroon.

## Stap 6: Schakel reguliere expressiezoekopdrachten in

 Schakel reguliere expressiezoekopdrachten in door de volgende instellingen in te stellen:`TextSearchOptions` Eigenschap van de absorber:

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

 Zorg ervoor dat u vervangt`"SearchTextAndDrawRectangle_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Zoektekst en teken rechthoek met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
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

Gefeliciteerd! U hebt succesvol geleerd hoe u specifieke tekst in een PDF-document kunt zoeken, een rechthoek kunt tekenen rond de gevonden tekst en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het instellen van het project tot het uitvoeren van de vereiste acties. U kunt deze code nu opnemen in uw eigen C#-projecten om tekst te manipuleren en rechthoeken te tekenen in PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Tekst zoeken en rechthoek tekenen"?

A: De tutorial "Zoek tekst en teken rechthoek" is bedoeld om gebruikers te begeleiden door het proces van het gebruiken van de Aspose.PDF bibliotheek voor .NET om te zoeken naar specifieke tekst in een PDF document, rechthoeken te tekenen rond de gevonden tekstsegmenten en het aangepaste document op te slaan. De tutorial biedt gedetailleerde instructies en C# codevoorbeelden om elke stap van het proces te illustreren.

#### V: Hoe helpt deze tutorial bij het tekenen van rechthoeken rond specifieke tekst in een PDF-document?

A: Deze tutorial biedt een uitgebreide handleiding over hoe u rechthoeken rond specifieke tekstsegmenten in een PDF-document kunt vinden en tekenen. Het demonstreert het proces van het opzetten van een project, het laden van een PDF-document, het inschakelen van reguliere expressiezoekopdrachten, het tekenen van rechthoeken rond gevonden tekstsegmenten en het opslaan van de gewijzigde PDF.

#### V: Welke vereisten zijn vereist om deze tutorial te volgen?

A: Voordat u met de tutorial begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben. U kunt deze verkrijgen via de Aspose-website of in uw project installeren met NuGet.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Begin met het maken van een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE). Voeg vervolgens een verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe aan uw project. Hiermee kunt u de functionaliteit van de bibliotheek gebruiken om PDF-documenten te manipuleren.

#### V: Kan ik met deze tutorial rechthoeken rond specifieke tekst tekenen?

A: Ja, de tutorial richt zich op het tekenen van rechthoeken rond specifieke tekstsegmenten in een PDF-document. Het laat zien hoe u de gewenste tekst kunt vinden met behulp van reguliere expressies, rechthoeken kunt maken rond de geïdentificeerde tekstsegmenten en de aangepaste PDF kunt opslaan.

#### V: Hoe kan ik de tekst opgeven waarnaar ik wil zoeken en er rechthoeken omheen tekenen?

 A: Om de tekst te specificeren waarnaar u wilt zoeken en er rechthoeken omheen wilt tekenen, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`@"[\S]+"` in de code van de tutorial met het door u gewenste reguliere-expressiepatroon.

#### V: Hoe schakel ik reguliere expressie-zoekopdrachten voor tekst in?

 A: Zoeken met reguliere expressies wordt ingeschakeld door een`TextSearchOptions` object en het instellen van de waarde ervan op`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere expressiepatroon wordt gebruikt tijdens tekst zoeken.

#### V: Hoe teken ik rechthoeken rond de gevonden tekst?

 A: Nadat u de tekstsegmenten hebt geïdentificeerd met behulp van de`TextFragmentAbsorber` , de tutorial biedt een lus om door deze segmenten te itereren. Voor elk tekstsegment laat de tutorial zien hoe je een rechthoek eromheen kunt maken met behulp van de`DrawBox` methode en specificeer het uiterlijk van de rechthoek.

#### V: Wat zijn de stappen om het aangepaste PDF-bestand met getekende rechthoeken op te slaan?

A: Nadat u rechthoeken rond de gewenste tekstsegmenten hebt getekend, gebruikt u de`Document` klas`Save` methode om het gewijzigde document op te slaan. De voorbeeldcode van de tutorial laat zien hoe u de bewerkte PDF kunt opslaan en een succesbericht kunt weergeven.

#### V: Kan ik het uiterlijk van de getekende rechthoeken aanpassen?

 A: Ja, u kunt het uiterlijk van de getekende rechthoeken aanpassen. In de voorbeeldcode van de tutorial staat de`DrawBox` methode wordt gebruikt om rechthoeken te maken. U kunt eigenschappen zoals kleur, stijl en dikte wijzigen om het uiterlijk van de getekende rechthoeken aan te passen.