---
title: Vervang lettertypen in PDF-bestand
linktitle: Vervang lettertypen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u lettertypen in een PDF-bestand vervangt met Aspose.PDF voor .NET.
type: docs
weight: 340
url: /nl/net/programming-with-text/replace-fonts/
---
In deze zelfstudie leggen we uit hoe u specifieke lettertypen in een PDF-bestand kunt vervangen met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het laden van een PDF-document, het zoeken naar tekstfragmenten, het identificeren van de lettertypen die moeten worden vervangen, het vervangen van de lettertypen en het opslaan van de gewijzigde PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waar u het invoer-PDF-bestand hebt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestand.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het PDF-document

 Vervolgens laden we het PDF-document met behulp van de`Document` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Stap 3: Lettertypen zoeken en vervangen

 Wij creëren een`TextFragmentAbsorber`object en stel de bewerkingsoptie in om ongebruikte lettertypen te verwijderen. Vervolgens accepteren we de absorber voor alle pagina's van het PDF-document om naar tekstfragmenten te zoeken.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Stap 4: Lettertypen vervangen

We doorkruisen alle tekstfragmenten die door de absorber worden geïdentificeerd. Als de lettertypenaam van een tekstfragment overeenkomt met het gewenste lettertype dat u wilt vervangen, vervangen we dit door het nieuwe lettertype.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Stap 5: Sla de gewijzigde PDF op

Ten slotte slaan we het gewijzigde PDF-document op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het vervangen van lettertypen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bron-PDF-bestand laden
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Zoek tekstfragmenten en stel de bewerkingsoptie in op het verwijderen van ongebruikte lettertypen
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Accepteer het absorber voor alle pagina's
	pdfDocument.Pages.Accept(absorber);
	// Blader door alle tekstfragmenten
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Als de lettertypenaam ArialMT is, vervangt u de lettertypenaam door Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Bewaar het bijgewerkte document
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u specifieke lettertypen in een PDF-document kunt vervangen met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF-document laden, naar tekstfragmenten zoeken, specifieke lettertypen identificeren en vervangen, en de gewijzigde PDF opslaan.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Lettertypen vervangen in PDF-bestand"?

A: In de tutorial "Lettertypen vervangen in PDF-bestand" wordt gedemonstreerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om specifieke lettertypen in een PDF-document te vervangen. Het biedt een stapsgewijze handleiding voor het laden van een PDF-document, het zoeken naar tekstfragmenten, het identificeren van lettertypen die u wilt vervangen, het vervangen van de lettertypen en het opslaan van de gewijzigde PDF.

#### Vraag: Waarom zou ik lettertypen in een PDF-document willen vervangen?

A: Het vervangen van lettertypen in een PDF-document kan nodig zijn als u de weergave van de tekst wilt standaardiseren of de compatibiliteit van het document op verschillende apparaten en platforms wilt verbeteren. Hiermee kunt u consistente typografie en opmaak garanderen.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw invoer-PDF-bestand zich bevindt.

#### Vraag: Hoe vervang ik specifieke lettertypen in een PDF-document?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Laad het PDF-document met behulp van de`Document` klas.
2.  Maak een`TextFragmentAbsorber` object en stel de bewerkingsoptie in om ongebruikte lettertypen te verwijderen. Accepteer de absorber voor alle pagina's om naar tekstfragmenten te zoeken.
3. Blader door de geïdentificeerde tekstfragmenten. Als de lettertypenaam van een tekstfragment overeenkomt met het lettertype dat u wilt vervangen, vervangt u deze door het nieuwe lettertype.

####  Vraag: Wat is het doel van het gebruik`TextFragmentAbsorber` with font replacement options?

 EEN: De`TextFragmentAbsorber` Met opties voor het vervangen van lettertypen kunt u tekstfragmenten lokaliseren en tegelijkertijd ongebruikte lettertypen verwijderen. Dit is belangrijk om ervoor te zorgen dat de vervangen lettertypen niet als extra bronnen in de PDF worden toegevoegd.

#### Vraag: Hoe identificeer ik specifieke lettertypen die moeten worden vervangen?

A: Door de tekstfragmenten te doorlopen die door de absorber zijn geïdentificeerd, kunt u toegang krijgen tot de lettertype-informatie voor elk tekstfragment. Als de lettertypenaam overeenkomt met het lettertype dat u wilt vervangen, kunt u de vervanging uitvoeren.

#### Vraag: Wat gebeurt er als het te vervangen lettertype niet in een tekstfragment wordt gevonden?

A: Als het te vervangen lettertype niet in een tekstfragment wordt aangetroffen, blijft het lettertype van het tekstfragment ongewijzigd. De vervanging vindt alleen plaats als de lettertypenaam overeenkomt.

#### Vraag: Is er een beperking voor het vervangen van lettertypen in deze zelfstudie?

A: Deze tutorial richt zich op het vervangen van specifieke lettertypen in tekstfragmenten. Als u lettertypen in andere contexten moet vervangen, zoals annotaties of formuliervelden, moet u de aanpak dienovereenkomstig uitbreiden.

#### Vraag: Wat is het verwachte resultaat van het uitvoeren van de opgegeven code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, vervangt u specifieke lettertypen in het PDF-document. De lettertypen die worden geïdentificeerd door de criteria die u instelt, worden vervangen door het nieuwe lettertype dat u opgeeft.

#### Vraag: Kan ik deze aanpak gebruiken om lettertypen in het hele PDF-document te vervangen?

A: Ja, u kunt de code aanpassen om lettertypen in het gehele PDF-document te vervangen door alle tekstfragmenten te doorlopen en de logica voor het vervangen van lettertypen toe te passen.