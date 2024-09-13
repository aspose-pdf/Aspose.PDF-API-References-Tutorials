---
title: Inhoud opnieuw ordenen met behulp van tekstvervanging
linktitle: Inhoud opnieuw ordenen met behulp van tekstvervanging
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de inhoud van een PDF-document opnieuw kunt rangschikken met behulp van tekstvervanging met Aspose.PDF voor .NET.
type: docs
weight: 270
url: /nl/net/programming-with-text/rearrange-contents-using-text-replacement/
---
In deze tutorial leggen we uit hoe u de inhoud van een PDF-document kunt herschikken met behulp van tekstvervanging met de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het laden van een PDF, het zoeken naar specifieke tekstfragmenten, het vervangen van de tekst en het opslaan van de gewijzigde PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar uw PDF-bestanden zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestanden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad de bron-PDF

 Vervolgens laden we het bron-PDF-document met behulp van de`Document` klas uit de Aspose.PDF bibliotheek.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Stap 3: Tekstfragmenten zoeken en vervangen

 Wij creëren een`TextFragmentAbsorber` object met een reguliere expressie om te zoeken naar specifieke tekstfragmenten. Vervolgens itereren we door de tekstfragmenten, passen hun lettertype, grootte, kleur aan en vervangen de tekst.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Stap 4: Sla de gewijzigde PDF op

Ten slotte slaan we het gewijzigde PDF-document op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het opnieuw rangschikken van inhoud met behulp van tekstvervanging met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bron PDF-bestand laden
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Maak een TextFragment Absorber-object met een reguliere expressie
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Vervang elk TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Stel het lettertype in van het te vervangen tekstfragment
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Lettergrootte instellen
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Vervang de tekst door een tekenreeks die groter is dan de tijdelijke aanduiding
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Resulterende PDF opslaan
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze tutorial hebt u geleerd hoe u de inhoud van een PDF-document kunt herschikken met behulp van tekstvervanging met de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u zoeken naar specifieke tekstfragmenten, hun uiterlijk aanpassen en de tekst in een PDF-document vervangen.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Inhoud herschikken met behulp van tekstvervanging'?

A: De tutorial "Rearrange Contents Using Text Replacement" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om de inhoud van een PDF-document te herschikken door tekstvervanging uit te voeren. De tutorial biedt een stapsgewijze handleiding en C#-broncode om u te helpen een PDF te laden, te zoeken naar specifieke tekstfragmenten, de tekst te vervangen en de gewijzigde PDF op te slaan.

#### V: Waarom zou ik de inhoud van een PDF-document opnieuw willen ordenen?

A: Het herschikken van inhoud in een PDF-document kan nuttig zijn voor verschillende doeleinden, zoals het bijwerken van tekst, het opnieuw formatteren van de lay-out of het aanbrengen van correcties. Met deze techniek kunt u de inhoud van een PDF dynamisch wijzigen terwijl de structuur en het uiterlijk behouden blijven.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-bestanden zich bevinden.

#### V: Hoe voer ik tekstvervanging uit in een PDF-document?

 A: De tutorial begeleidt u door het proces van het zoeken naar specifieke tekstfragmenten in een PDF met behulp van de`TextFragmentAbsorber`klasse. Het laat zien hoe u het uiterlijk van de tekstfragmenten kunt aanpassen en hun inhoud kunt vervangen.

#### V: Kan ik het lettertype, de grootte en de kleur van de vervangen tekst aanpassen?

 A: Ja, u kunt het lettertype, de grootte en de kleur van de vervangen tekst aanpassen door de`TextState` eigenschappen van de`TextFragment` object. De tutorial geeft een voorbeeld van hoe u het lettertype, de lettergrootte en de voorgrondkleur van de tekst instelt.

#### V: Hoe kan ik het gewijzigde PDF-document opslaan?

 A: Nadat u tekst hebt vervangen en de tekstfragmenten hebt aangepast, kunt u het gewijzigde PDF-document opslaan met behulp van de`Save` methode van de`Document` klasse. Geef het gewenste pad naar het uitvoerbestand als argument voor de`Save` methode.

#### V: Wat is het verwachte resultaat van deze tutorial?

A: Wanneer u de tutorial volgt en de meegeleverde C#-code uitvoert, genereert u een aangepast PDF-document waarin specifieke tekstfragmenten zijn vervangen en aangepast volgens uw specificaties.

#### V: Kan ik verschillende reguliere expressies gebruiken voor tekst zoeken?

 A: Ja, u kunt verschillende reguliere expressies gebruiken om te zoeken naar specifieke tekstfragmenten in het PDF-document. Het voorbeeld in de tutorial laat zien hoe u een`TextFragmentAbsorber`object met een specifieke reguliere expressie om naar tekst te zoeken en deze te vervangen.

#### V: Is een geldige Aspose-licentie vereist voor deze tutorial?

A: Ja, een geldige Aspose-licentie is vereist om deze tutorial correct te laten werken. U kunt een volledige licentie kopen of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.