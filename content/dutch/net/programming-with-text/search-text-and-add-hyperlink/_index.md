---
title: Zoek tekst en voeg hyperlink toe
linktitle: Zoek tekst en voeg hyperlink toe
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u naar tekst in een PDF zoekt, hyperlinks aan de gevonden tekst toevoegt en het gewijzigde document opslaat met Aspose.PDF voor .NET.
type: docs
weight: 450
url: /nl/net/programming-with-text/search-text-and-add-hyperlink/
---
Deze tutorial legt uit hoe u Aspose.PDF voor .NET kunt gebruiken om te zoeken naar specifieke tekst in een PDF-document, een hyperlink naar de gevonden tekst kunt toevoegen en het gewijzigde document kunt opslaan. De meegeleverde C#-broncode demonstreert het proces stap voor stap.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Stap 3: Stel het pad naar de documentmap in

 Stel het pad naar uw documentmap in met behulp van`dataDir` variabele:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 4: Maak een TextFragmentAbsorber

 Maak een`TextFragmentAbsorber` object om alle instanties van de ingevoerde zoekterm te vinden:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Vervangen`"\\d{4}-\\d{4}"` met het door u gewenste reguliere-expressiepatroon.

## Stap 5: Schakel reguliere expressiezoekopdrachten in

 Schakel reguliere expressiezoekopdrachten in door de volgende instellingen in te stellen:`TextSearchOptions` Eigenschap van de absorber:

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

## Stap 9: Sla het gewijzigde document op en sluit het

Sla het gewijzigde document op en sluit de editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Zorg ervoor dat u vervangt`"SearchTextAndAddHyperlink_out.pdf"` met de gewenste naam van het uitvoerbestand.

### Voorbeeldbroncode voor Zoektekst en voeg hyperlink toe met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Maak een absorberobject om alle instanties van de invoerzoekzin te vinden
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Schakel reguliere expressie zoeken in
absorber.TextSearchOptions = new TextSearchOptions(true);
// Document openen
PdfContentEditor editor = new PdfContentEditor();
// Bron PDF-bestand binden
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

Gefeliciteerd! U hebt succesvol geleerd hoe u specifieke tekst in een PDF-document kunt zoeken, hyperlinks kunt toevoegen aan de gevonden tekst en het gewijzigde document kunt opslaan met Aspose.PDF voor .NET. Deze tutorial bood een stapsgewijze handleiding, van het instellen van het project tot het uitvoeren van de vereiste acties. U kunt deze code nu opnemen in uw eigen C#-projecten om tekst te manipuleren en hyperlinks toe te voegen in PDF-bestanden.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Tekst zoeken en hyperlink toevoegen"?

A: De tutorial "Zoek tekst en voeg hyperlink toe" is bedoeld om te laten zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om te zoeken naar specifieke tekst in een PDF-document, hyperlinks aan de gevonden tekst kunt toevoegen en vervolgens het gewijzigde document kunt opslaan. De tutorial biedt een uitgebreide handleiding en C#-codevoorbeelden om het stapsgewijze proces te illustreren.

#### V: Hoe helpt deze tutorial bij het toevoegen van hyperlinks naar specifieke tekst in een PDF-document?

A: Deze tutorial begeleidt u door het proces van het gebruiken van de Aspose.PDF-bibliotheek om specifieke tekst in een PDF-document te vinden, een hyperlink toe te passen op de geïdentificeerde tekst en de gewijzigde PDF op te slaan. Het behandelt essentiële stappen zoals het instellen van het project, het laden van het document, het inschakelen van reguliere expressiezoekopdrachten en het toevoegen van hyperlinks aan de gevonden tekst.

#### V: Welke vereisten zijn er nodig om deze tutorial te volgen?

A: Voordat u begint, moet u een basiskennis hebben van de programmeertaal C#. Daarnaast moet u de Aspose.PDF voor .NET-bibliotheek geïnstalleerd hebben, die u kunt verkrijgen via de Aspose-website of kunt installeren met NuGet in uw project.

#### V: Hoe stel ik mijn project in om deze tutorial te volgen?

A: Begin met het maken van een nieuw C#-project in uw favoriete geïntegreerde ontwikkelomgeving (IDE). Voeg vervolgens een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek, zodat u de mogelijkheden van de bibliotheek in uw project kunt gebruiken.

#### V: Kan ik met behulp van deze tutorial hyperlinks naar specifieke tekst toevoegen?

A: Ja, deze tutorial richt zich specifiek op het toevoegen van hyperlinks aan specifieke tekst in een PDF-document. Het laat zien hoe u de gewenste tekst kunt vinden en extraheren met behulp van reguliere expressies, hyperlinks kunt maken die zijn gekoppeld aan de tekstfragmenten en de aangepaste PDF kunt opslaan.

#### V: Hoe definieer ik de tekst waarnaar ik wil zoeken en waaraan ik een hyperlink wil toevoegen?

 A: Om de tekst te specificeren waarnaar u wilt zoeken en waaraan u een hyperlink wilt toevoegen, maakt u een`TextFragmentAbsorber` object en stel het patroon ervan in met behulp van de`Text` parameter. Vervang het standaardpatroon`"\\d{4}-\\d{4}"` in de code van de tutorial met het door u gewenste reguliere-expressiepatroon.

#### V: Hoe kan ik reguliere expressie-zoekopdrachten voor tekst inschakelen?

 A: Zoeken met reguliere expressies wordt ingeschakeld door een`TextSearchOptions` object en het instellen van de waarde ervan op`true` . Wijs dit object toe aan de`TextSearchOptions` eigendom van de`TextFragmentAbsorber` voorbeeld. Dit zorgt ervoor dat het reguliere-expressiepatroon wordt toegepast tijdens tekstzoekopdrachten.

#### V: Hoe voeg ik hyperlinks toe aan de gevonden tekst?

 A: Nadat de tekstfragmenten zijn geïdentificeerd met behulp van de`TextFragmentAbsorber` , de tutorial biedt een lus om door deze fragmenten te itereren. Voor elk tekstfragment laat de tutorial zien hoe u de tekstkleur op blauw instelt en een hyperlink maakt met behulp van de`CreateWebLink` methode.

#### V: Wat zijn de stappen om het gewijzigde PDF-bestand met hyperlinks op te slaan?

 A: Nadat u hyperlinks naar de gewenste tekstfragmenten hebt toegevoegd, gebruikt u de`PdfContentEditor` class om het gewijzigde document op te slaan. De voorbeeldcode van de tutorial laat zien hoe u de bewerkte PDF opslaat, de editor sluit en een succesbericht weergeeft.