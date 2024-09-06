---
title: Lettertypen in PDF-bestand vervangen
linktitle: Lettertypen in PDF-bestand vervangen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u lettertypen in een PDF-bestand kunt vervangen met Aspose.PDF voor .NET.
type: docs
weight: 340
url: /nl/net/programming-with-text/replace-fonts/
---
In deze tutorial leggen we uit hoe u specifieke lettertypen in een PDF-bestand vervangt met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het laden van een PDF-document, het zoeken naar tekstfragmenten, het identificeren van de te vervangen lettertypen, het vervangen van de lettertypen en het opslaan van de gewijzigde PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar u het PDF-invoerbestand hebt. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar uw PDF-bestand.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Het PDF-document laden

 Vervolgens laden we het PDF-document met behulp van de`Document` klas uit de Aspose.PDF bibliotheek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Stap 3: Lettertypen zoeken en vervangen

 Wij creëren een`TextFragmentAbsorber`object en stel de bewerkingsoptie in om ongebruikte lettertypen te verwijderen. Vervolgens accepteren we de absorber voor alle pagina's van het PDF-document om te zoeken naar tekstfragmenten.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Stap 4: Lettertypen vervangen

We doorlopen alle tekstfragmenten die door de absorber zijn geïdentificeerd. Als de lettertypenaam van een tekstfragment overeenkomt met het gewenste lettertype om te vervangen, vervangen we het met het nieuwe lettertype.

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

### Voorbeeldbroncode voor Vervang lettertypen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Bron PDF-bestand laden
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Zoek tekstfragmenten en stel de bewerkingsoptie in als het verwijderen van ongebruikte lettertypen
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Accepteer de absorber voor alle pagina's
	pdfDocument.Pages.Accept(absorber);
	// Doorloop alle TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Als de lettertypenaam ArialMT is, vervangt u de lettertypenaam door Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Bijgewerkt document opslaan
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusie

In deze tutorial hebt u geleerd hoe u specifieke lettertypen in een PDF-document vervangt met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF-document laden, zoeken naar tekstfragmenten, specifieke lettertypen identificeren en vervangen en de gewijzigde PDF opslaan.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Lettertypen in PDF-bestand vervangen'?

A: De tutorial "Lettertypen in PDF-bestand vervangen" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om specifieke lettertypen in een PDF-document te vervangen. Het biedt een stapsgewijze handleiding over hoe u een PDF-document kunt laden, tekstfragmenten kunt zoeken, lettertypen kunt identificeren om te vervangen, de lettertypen kunt vervangen en de gewijzigde PDF kunt opslaan.

#### V: Waarom zou ik lettertypen in een PDF-document willen vervangen?

A: Het vervangen van lettertypen in een PDF-document kan nodig zijn als u het uiterlijk van de tekst wilt standaardiseren of de compatibiliteit van het document op verschillende apparaten en platforms wilt verbeteren. Hiermee kunt u consistente typografie en opmaak garanderen.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar uw PDF-invoerbestand zich bevindt.

#### V: Hoe vervang ik specifieke lettertypen in een PDF-document?

A: De tutorial begeleidt u stap voor stap door het proces:

1.  Laad het PDF-document met behulp van de`Document` klas.
2.  Maak een`TextFragmentAbsorber` object en stel de bewerkingsoptie in om ongebruikte lettertypen te verwijderen. Accepteer de absorber voor alle pagina's om te zoeken naar tekstfragmenten.
3. Doorloop de geïdentificeerde tekstfragmenten. Als de lettertypenaam van een tekstfragment overeenkomt met het lettertype dat u wilt vervangen, vervangt u het met het nieuwe lettertype.

####  V: Wat is het doel van het gebruik van`TextFragmentAbsorber` with font replacement options?

 A: De`TextFragmentAbsorber` met lettertypevervangingsopties kunt u tekstfragmenten lokaliseren en tegelijkertijd ongebruikte lettertypen verwijderen. Dit is belangrijk om ervoor te zorgen dat de vervangen lettertypen niet als extra bronnen in de PDF worden toegevoegd.

#### V: Hoe kan ik bepalen welke specifieke lettertypen ik moet vervangen?

A: Door de tekstfragmenten te doorlopen die door de absorber zijn geïdentificeerd, kunt u de lettertype-informatie voor elk tekstfragment raadplegen. Als de lettertypenaam overeenkomt met het lettertype dat u wilt vervangen, kunt u de vervanging uitvoeren.

#### V: Wat gebeurt er als het te vervangen lettertype niet in een tekstfragment wordt gevonden?

A: Als het te vervangen lettertype niet in een tekstfragment wordt gevonden, blijft het lettertype van het tekstfragment ongewijzigd. De vervanging vindt alleen plaats als de lettertypenaam overeenkomt.

#### V: Zijn er beperkingen aan het vervangen van lettertypen in deze tutorial?

A: Deze tutorial richt zich op het vervangen van specifieke lettertypen in tekstfragmenten. Als u lettertypen in andere contexten moet vervangen, zoals annotaties of formuliervelden, moet u de aanpak dienovereenkomstig uitbreiden.

#### V: Wat is het verwachte resultaat van het uitvoeren van de verstrekte code?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, vervangt u specifieke lettertypen in het PDF-document. De lettertypen die zijn geïdentificeerd door de criteria die u instelt, worden vervangen door het nieuwe lettertype dat u opgeeft.

#### V: Kan ik deze aanpak gebruiken om lettertypen in het hele PDF-document te vervangen?

A: Ja, u kunt de code aanpassen om lettertypen in het gehele PDF-document te vervangen door alle tekstfragmenten te doorlopen en de logica voor het vervangen van lettertypen toe te passen.