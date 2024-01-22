---
title: Zoek tekst en voeg een hyperlink toe
linktitle: Zoek tekst en voeg een hyperlink toe
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekst in een PDF kunt zoeken, hyperlinks aan de gevonden tekst kunt toevoegen en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET.
type: docs
weight: 450
url: /nl/net/programming-with-text/search-text-and-add-hyperlink/
---
In deze zelfstudie wordt uitgelegd hoe u Aspose.PDF voor .NET kunt gebruiken om naar specifieke tekst in een PDF-document te zoeken, een hyperlink aan de gevonden tekst toe te voegen en het gewijzigde document op te slaan. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van de`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 4: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle exemplaren van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Vervangen`"\\d{4}-\\d{4}"` met uw gewenste reguliere expressiepatroon.

## Stap 5: Schakel zoeken naar reguliere expressies in

 Schakel het zoeken naar reguliere expressies in door de`TextSearchOptions` eigenschap van de absorber:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Stap 6: Open en bind het PDF-document

 Maak een`PdfContentEditor` object en bind het aan het bron-PDF-bestand:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Vervangen`"SearchRegularExpressionPage.pdf"` met de werkelijke naam van uw PDF-bestand.

## Stap 7: Accepteer de absorber voor de pagina

Accepteer de absorber voor de gewenste pagina van het document:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Vervangen`1` met het gewenste paginanummer.

## Stap 8: Voeg hyperlinks toe aan de gevonden tekst

Loop door de opgehaalde tekstfragmenten en voeg er hyperlinks aan toe:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Maak een rechthoek op basis van de positie van het tekstfragment
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Voeg een weblink toe aan de rechthoek
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Vervangen`"http://www.aspose.com"` met de gewenste hyperlink-URL.

## Stap 9: Bewaar en sluit het gewijzigde document

Sla het gewijzigde document op en sluit de editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Zorg ervoor dat u vervangt`"SearchTextAndAddHyperlink_out.pdf"` met de gewenste uitvoerbestandsnaam.

### Voorbeeldbroncode voor het zoeken naar tekst en het toevoegen van een hyperlink met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een absorber-object om alle exemplaren van de invoerzoekterm te vinden
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Schakel zoeken naar reguliere expressies in
absorber.TextSearchOptions = new TextSearchOptions(true);
// Document openen
PdfContentEditor editor = new PdfContentEditor();
// Bron-PDF-bestand binden
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Accepteer de absorber voor de pagina
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Loop door de fragmenten
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blauw, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u naar specifieke tekst in een PDF-document kunt zoeken, hyperlinks naar de gevonden tekst kunt toevoegen en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het opzetten van het project tot het uitvoeren van de vereiste acties. U kunt deze code nu in uw eigen C#-projecten opnemen om tekst te manipuleren en hyperlinks in PDF-bestanden toe te voegen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial 'Tekst zoeken en hyperlink toevoegen'?

A: De tutorial "Tekst zoeken en hyperlink toevoegen" is bedoeld om te demonstreren hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om naar specifieke tekst in een PDF-document te zoeken, hyperlinks aan de gevonden tekst toe te voegen en vervolgens het gewijzigde document op te slaan. De zelfstudie biedt een uitgebreide handleiding en C#-codevoorbeelden om het stapsgewijze proces te illustreren.

#### Vraag: Hoe helpt deze tutorial bij het toevoegen van hyperlinks naar specifieke tekst in een PDF-document?

A: Deze tutorial begeleidt u bij het gebruik van de Aspose.PDF-bibliotheek om specifieke tekst in een PDF-document te zoeken, een hyperlink op de geïdentificeerde tekst toe te passen en de gewijzigde PDF op te slaan. Het behandelt essentiële stappen zoals het opzetten van het project, het laden van het document, het inschakelen van zoeken in reguliere expressies en het toevoegen van hyperlinks aan de gevonden tekst.

#### Vraag: Welke vereisten zijn nodig om deze tutorial te volgen?

A: Voordat u begint, moet u een basiskennis hebben van de programmeertaal C#. Bovendien moet u de Aspose.PDF voor .NET-bibliotheek hebben geïnstalleerd, die u kunt verkrijgen via de Aspose-website of kunt installeren met NuGet in uw project.

#### Vraag: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Begin met het maken van een nieuw C#-project in de geïntegreerde ontwikkelomgeving (IDE) van uw voorkeur. Voeg vervolgens een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek, zodat u de mogelijkheden van de bibliotheek in uw project kunt gebruiken.

#### Vraag: Kan ik met deze tutorial hyperlinks naar specifieke tekst toevoegen?

A: Ja, deze tutorial richt zich specifiek op het toevoegen van hyperlinks naar specifieke tekst in een PDF-document. Er wordt gedemonstreerd hoe u de gewenste tekst kunt vinden en extraheren met behulp van reguliere expressies, hoe u hyperlinks kunt maken die aan de tekstfragmenten zijn gekoppeld, en hoe u de gewijzigde PDF kunt opslaan.

#### Vraag: Hoe definieer ik de tekst waarnaar ik wil zoeken en hoe ik een hyperlink wil toevoegen?

 A: Om de tekst op te geven waarnaar u wilt zoeken en waaraan u een hyperlink wilt toevoegen, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`"\\d{4}-\\d{4}"` in de code van de tutorial met het gewenste reguliere-expressiepatroon.

#### Vraag: Hoe kan ik zoeken met reguliere expressies naar tekst inschakelen?

 A: Zoeken in reguliere expressies wordt mogelijk gemaakt door een`TextSearchOptions` object en de waarde ervan instellen`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere-expressiepatroon wordt toegepast tijdens het zoeken naar tekst.

#### Vraag: Hoe voeg ik hyperlinks toe aan de gevonden tekst?

 A: Na het identificeren van de tekstfragmenten met behulp van de`TextFragmentAbsorber` , biedt de tutorial een lus waarmee u deze fragmenten kunt doorlopen. Voor elk tekstfragment laat de tutorial zien hoe u de tekstkleur op blauw kunt instellen en een hyperlink kunt maken met behulp van de`CreateWebLink` methode.

#### Vraag: Wat zijn de stappen om de gewijzigde PDF met hyperlinks op te slaan?

 A: Nadat u hyperlinks naar de gewenste tekstfragmenten heeft toegevoegd, gebruikt u de`PdfContentEditor` klasse om het gewijzigde document op te slaan. De voorbeeldcode van de tutorial laat zien hoe u de bewerkte PDF kunt opslaan, de editor kunt sluiten en een succesbericht kunt weergeven.