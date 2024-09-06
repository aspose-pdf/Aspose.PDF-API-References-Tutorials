---
title: Verborgen tekstblok in PDF-bestand
linktitle: Verborgen tekstblok in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u verborgen tekstblokken in een PDF-bestand kunt maken met Aspose.PDF voor .NET.
type: docs
weight: 230
url: /nl/net/programming-with-text/hidden-text-block/
---
In deze tutorial leggen we uit hoe u een verborgen tekstblok in een PDF-bestand kunt maken met behulp van de Aspose.PDF-bibliotheek voor .NET. Een verborgen tekstblok is een zwevende tekst die zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. We doorlopen het stapsgewijze proces van het maken van het verborgen tekstblok met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een voorbeelddocument

In deze stap maken we een voorbeeld-PDF-document en voegen er een tekstfragment aan toe. Het tekstfragment dient als trigger voor het weergeven van het verborgen tekstblok.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## Stap 3: Open het document

 Nu openen we het eerder gemaakte document met behulp van de`Document` klas.

```csharp
Document document = new Document(outputFile);
```

## Stap 4: Zoek het tekstfragment

 Wij gebruiken een`TextFragmentAbsorber`object om het tekstfragment te vinden dat de weergave van het verborgen tekstblok zal activeren. In dit geval zoeken we naar de exacte tekst "Beweeg de muiscursor hierheen om zwevende tekst weer te geven".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Stap 5: Het verborgen tekstveld maken

 Wij creëren een`TextBoxField` object om het verborgen tekstveld weer te geven. Dit veld bevat de tekst die zichtbaar wordt wanneer de muiscursor over de triggertekst beweegt.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## Stap 6: Voeg het verborgen tekstveld toe aan het document

We voegen het verborgen tekstveld toe aan de formulierverzameling van het document.

```csharp
document.Form.Add(floatingField);
```

## Stap 7: De onzichtbare knop maken

We maken een onzichtbaar knopveld dat boven op het triggertekstfragment wordt geplaatst. Dit knopveld heeft acties die zijn gekoppeld aan muis-invoer- en uitvoergebeurtenissen.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Stap 8: Sla het document op

Tot slot slaan we het gewijzigde document op met het verborgen tekstblok.

```csharp
document. Save(outputFile);
```

### Voorbeeldbroncode voor verborgen tekstblok met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Voorbeelddocument met tekst maken
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Open document met tekst
Document document = new Document(outputFile);
// Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accepteer de absorber voor de documentpagina's
document.Pages.Accept(absorber);
// Ontvang het eerste geëxtraheerde tekstfragment
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Maak een verborgen tekstveld voor zwevende tekst in de opgegeven rechthoek van de pagina
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Stel de tekst in die als veldwaarde moet worden weergegeven
floatingField.Value = "This is the \"floating text field\".";
// Voor dit scenario raden wij aan om het veld 'alleen-lezen' te maken
floatingField.ReadOnly = true;
// Stel de vlag 'verborgen' in om het veld onzichtbaar te maken bij het openen van het document
floatingField.Flags |= AnnotationFlags.Hidden;
// Het instellen van een unieke veldnaam is niet noodzakelijk, maar wel toegestaan
floatingField.PartialName = "FloatingField_1";
// Het instellen van de kenmerken van het velduiterlijk is niet noodzakelijk, maar maakt het beter
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Tekstveld toevoegen aan het document
document.Form.Add(floatingField);
// Maak een onzichtbare knop op de positie van het tekstfragment
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Maak een nieuwe verbergactie voor het opgegeven veld (annotatie) en de onzichtbaarheidsvlag.
// (U kunt ook naar een zwevend veld verwijzen met de naam als u die hierboven hebt opgegeven.)
// Voeg acties toe bij het in- en uitstappen van de muis in het onzichtbare knopveld
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Knopveld toevoegen aan het document
document.Form.Add(buttonField);
// Document opslaan
document.Save(outputFile);
```

## Conclusie

In deze tutorial hebt u geleerd hoe u een verborgen tekstblok maakt met behulp van de Aspose.PDF voor .NET-bibliotheek. Door de stapsgewijze handleiding te volgen, kunt u een PDF-document genereren met een verborgen tekstveld dat zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. U kunt het uiterlijk en gedrag van het verborgen tekstblok aanpassen aan uw vereisten.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial "Verborgen tekstblok in PDF-bestand"?

A: De tutorial "Verborgen tekstblok in PDF-bestand" legt uit hoe u een verborgen tekstblok in een PDF-bestand kunt maken met behulp van de Aspose.PDF-bibliotheek voor .NET. Een verborgen tekstblok is een zwevende tekst die zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. Deze tutorial biedt een stapsgewijze handleiding met behulp van C#-broncode.

#### V: Waarom zou ik een verborgen tekstblok in een PDF-bestand willen maken?

A: Het maken van een verborgen tekstblok kan handig zijn voor interactieve PDF-documenten waarin u aanvullende informatie of context wilt bieden die alleen zichtbaar wordt wanneer een gebruiker de muiscursor over een bepaald gebied beweegt.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar u het gegenereerde PDF-bestand wilt opslaan.

#### V: Hoe maak ik een voorbeelddocument en voeg ik er een tekstfragment aan toe?

 A: In de tutorial gebruik je de`Document` klasse om een voorbeeld-PDF-document te maken en een tekstfragment toe te voegen. Dit tekstfragment dient als trigger voor het weergeven van het verborgen tekstblok.

#### V: Hoe vind ik het tekstfragment dat het verborgen tekstblok activeert?

 A: De tutorial laat zien hoe je een`TextFragmentAbsorber` object om het tekstfragment te vinden dat de weergave van het verborgen tekstblok activeert. Het zoekt naar een specifieke tekstreeks in het PDF-document.

#### V: Hoe kan ik het verborgen tekstveld maken en aanpassen?

 A: Je creëert een`TextBoxField`object om het verborgen tekstveld te representeren. De tutorial biedt code om verschillende eigenschappen in te stellen, zoals positie, waarde, uiterlijk en gedrag van het verborgen tekstveld.

#### V: Hoe maak ik een onzichtbare knop die gekoppeld is aan het verborgen tekstblok?

 A: Een onzichtbaar knopveld wordt gemaakt met behulp van de`ButtonField` klasse. Dit knopveld is boven op het triggertekstfragment geplaatst en heeft acties die zijn gekoppeld aan muis-enter- en exit-gebeurtenissen. Deze acties bepalen de zichtbaarheid van het verborgen tekstblok.

#### V: Kan ik het uiterlijk van het verborgen tekstblok en het triggergebied aanpassen?

A: Ja, u kunt verschillende eigenschappen van zowel het verborgen tekstveld als de onzichtbare knop aanpassen, waaronder lettertype, kleur, grootte en positionering.

#### V: Hoe kan ik het gewijzigde document met het verborgen tekstblok opslaan?

 A: De tutorial laat zien hoe u het gewijzigde document kunt opslaan met behulp van de`Save` methode van de`Document` klas.