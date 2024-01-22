---
title: Herschik de inhoud met behulp van tekstvervanging
linktitle: Herschik de inhoud met behulp van tekstvervanging
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de inhoud van een PDF-document kunt herschikken met behulp van tekstvervanging met Aspose.PDF voor .NET.
type: docs
weight: 270
url: /nl/net/programming-with-text/rearrange-contents-using-text-replacement/
---
In deze zelfstudie leggen we uit hoe u de inhoud van een PDF-document kunt herschikken door tekstvervanging te gebruiken met de Aspose.PDF-bibliotheek voor .NET. We doorlopen stapsgewijs het proces van het laden van een PDF, het zoeken naar specifieke tekstfragmenten, het vervangen van de tekst en het opslaan van de gewijzigde PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waar uw PDF-bestanden zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestanden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad de bron-PDF

 Vervolgens laden we het bron-PDF-document met behulp van de`Document` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Stap 3: Tekstfragmenten zoeken en vervangen

 Wij creëren een`TextFragmentAbsorber` object met een reguliere expressie om naar specifieke tekstfragmenten te zoeken. Vervolgens doorlopen we de tekstfragmenten, passen het lettertype, de grootte en de kleur aan en vervangen we de tekst.

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

### Voorbeeldbroncode voor het herschikken van inhoud met behulp van tekstvervanging met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bron-PDF-bestand laden
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	// Maak een TextFragment Absorber-object met reguliere expressie
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Vervang elk tekstfragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Stel het lettertype in van het tekstfragment dat wordt vervangen
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Lettergrootte instellen
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Vervang de tekst door een grotere tekenreeks dan de tijdelijke aanduiding
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Bewaar de resulterende PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u de inhoud van een PDF-document kunt herschikken door tekstvervanging te gebruiken met de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u naar specifieke tekstfragmenten zoeken, het uiterlijk ervan aanpassen en de tekst in een PDF-document vervangen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Inhoud herschikken met behulp van tekstvervanging"?

A: In de tutorial "Inhoud herschikken met tekstvervanging" wordt gedemonstreerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om de inhoud in een PDF-document te herschikken door tekstvervanging uit te voeren. De tutorial biedt een stapsgewijze handleiding en C#-broncode waarmee u een PDF kunt laden, naar specifieke tekstfragmenten kunt zoeken, de tekst kunt vervangen en de gewijzigde PDF kunt opslaan.

#### Vraag: Waarom zou ik de inhoud van een PDF-document opnieuw willen rangschikken?

A: Het herschikken van de inhoud in een PDF-document kan voor verschillende doeleinden nuttig zijn, zoals het bijwerken van tekst, het opnieuw opmaken van de lay-out of het aanbrengen van correcties. Met deze techniek kunt u de inhoud van een PDF dynamisch wijzigen terwijl de structuur en het uiterlijk ervan behouden blijven.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-bestanden zich bevinden.

#### Vraag: Hoe voer ik tekstvervanging uit in een PDF-document?

 A: De tutorial begeleidt u bij het zoeken naar specifieke tekstfragmenten in een PDF met behulp van de`TextFragmentAbsorber`klas. Het laat zien hoe u het uiterlijk van de tekstfragmenten kunt aanpassen en hun inhoud kunt vervangen.

#### Vraag: Kan ik het lettertype, de grootte en de kleur van de vervangen tekst aanpassen?

 A: Ja, u kunt het lettertype, de grootte en de kleur van de vervangen tekst aanpassen door de`TextState` eigenschappen van de`TextFragment` voorwerp. De tutorial geeft een voorbeeld van hoe u het lettertype, de lettergrootte en de voorgrondkleur van de tekst kunt instellen.

#### Vraag: Hoe bewaar ik het gewijzigde PDF-document?

 A: Nadat u tekstvervanging heeft uitgevoerd en de tekstfragmenten heeft aangepast, kunt u het gewijzigde PDF-document opslaan met behulp van de`Save` werkwijze van de`Document` klas. Geef het gewenste uitvoerbestandspad op als argument voor het`Save` methode.

#### Vraag: Wat is de verwachte uitkomst van deze tutorial?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, genereert u een aangepast PDF-document waarin specifieke tekstfragmenten zijn vervangen en aangepast volgens uw specificaties.

#### Vraag: Kan ik verschillende reguliere expressies gebruiken voor tekstzoekopdrachten?

 A: Ja, u kunt verschillende reguliere expressies gebruiken om naar specifieke tekstfragmenten in het PDF-document te zoeken. Het voorbeeld in de zelfstudie laat zien hoe u een`TextFragmentAbsorber`object met een specifieke reguliere expressie om tekst te zoeken en te vervangen.

#### Vraag: Is een geldige Aspose-licentie vereist voor deze zelfstudie?

A: Ja, een geldige Aspose-licentie is vereist om deze tutorial correct te laten werken. U kunt een volledige licentie kopen of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.