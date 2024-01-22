---
title: Verborgen tekstblok in PDF-bestand
linktitle: Verborgen tekstblok in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u verborgen tekstblokken in een PDF-bestand kunt maken met Aspose.PDF voor .NET.
type: docs
weight: 230
url: /nl/net/programming-with-text/hidden-text-block/
---
In deze zelfstudie leggen we uit hoe u een verborgen tekstblok in een PDF-bestand kunt maken met behulp van de Aspose.PDF-bibliotheek voor .NET. Een verborgen tekstblok is een zwevende tekst die zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. We zullen het stapsgewijze proces doorlopen voor het maken van het verborgen tekstblok met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waarin u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir`variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een voorbeelddocument

In deze stap maken we een voorbeeld-PDF-document en voegen er een tekstfragment aan toe. Het tekstfragment zal dienen als trigger voor het weergeven van het verborgen tekstblok.

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

 Wij gebruiken een`TextFragmentAbsorber` object om het tekstfragment te vinden dat de weergave van het verborgen tekstblok activeert. In dit geval zoeken we naar de exacte tekst "Beweeg de muiscursor hierheen om zwevende tekst weer te geven".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## Stap 5: Maak het verborgen tekstveld

 Wij creëren een`TextBoxField` object dat het verborgen tekstveld vertegenwoordigt. Dit veld bevat de tekst die zichtbaar wordt wanneer de muiscursor over de triggertekst beweegt.

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

## Stap 7: Maak de onzichtbare knop

We creëren een onzichtbaar knoppenveld dat bovenop het triggertekstfragment wordt geplaatst. Dit knopveld bevat acties die verband houden met muisinvoer- en -uitstapgebeurtenissen.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## Stap 8: Bewaar het document

Ten slotte slaan we het gewijzigde document op met het verborgen tekstblok.

```csharp
document. Save(outputFile);
```

### Voorbeeldbroncode voor verborgen tekstblok met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Maak een voorbeelddocument met tekst
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Document met tekst openen
Document document = new Document(outputFile);
// Maak een TextAbsorber-object om alle zinnen te vinden die overeenkomen met de reguliere expressie
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Accepteer het absorber voor de documentpagina's
document.Pages.Accept(absorber);
// Haal het eerste geëxtraheerde tekstfragment op
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
// Maak een verborgen tekstveld voor zwevende tekst in de opgegeven rechthoek van de pagina
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Stel in dat tekst moet worden weergegeven als veldwaarde
floatingField.Value = "This is the \"floating text field\".";
// We raden aan om het veld voor dit scenario 'alleen-lezen' te maken
floatingField.ReadOnly = true;
// Stel de 'verborgen' vlag in om het veld onzichtbaar te maken bij het openen van het document
floatingField.Flags |= AnnotationFlags.Hidden;
// Het instellen van een unieke veldnaam is niet nodig maar wel toegestaan
floatingField.PartialName = "FloatingField_1";
// Het instellen van karakteristieken voor het uiterlijk van het veld is niet nodig, maar maakt het wel beter
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Voeg een tekstveld toe aan het document
document.Form.Add(floatingField);
// Maak een onzichtbare knop op de positie van het tekstfragment
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Maak een nieuwe verbergactie voor het opgegeven veld (annotatie) en de onzichtbaarheidsvlag.
//(U kunt ook naar een zwevend veld verwijzen met de naam als u deze hierboven heeft opgegeven.)
// Voeg acties toe bij het invoeren/afsluiten van de muis in het onzichtbare knoppenveld
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Knopveld toevoegen aan het document
document.Form.Add(buttonField);
// Bewaar document
document.Save(outputFile);
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een verborgen tekstblok maakt met behulp van de Aspose.PDF voor .NET-bibliotheek. Door de stapsgewijze handleiding te volgen, kunt u een PDF-document genereren met een verborgen tekstveld dat zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. U kunt het uiterlijk en het gedrag van het verborgen tekstblok aanpassen aan uw wensen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Verborgen tekstblok in PDF-bestand"?

A: In de tutorial "Verborgen tekstblok in PDF-bestand" wordt uitgelegd hoe u een verborgen tekstblok in een PDF-bestand kunt maken met behulp van de Aspose.PDF-bibliotheek voor .NET. Een verborgen tekstblok is een zwevende tekst die zichtbaar wordt wanneer de muiscursor over een specifiek gebied beweegt. Deze zelfstudie biedt een stapsgewijze handleiding voor het gebruik van C#-broncode.

#### Vraag: Waarom zou ik een verborgen tekstblok in een PDF-bestand willen maken?

A: Het maken van een verborgen tekstblok kan handig zijn voor interactieve PDF-documenten waarbij u aanvullende informatie of context wilt verstrekken die alleen zichtbaar wordt wanneer een gebruiker de muiscursor over een aangewezen gebied beweegt.

#### Vraag: Hoe stel ik de documentmap in?

A: Om de documentmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waarin u het gegenereerde PDF-bestand wilt opslaan.

#### Vraag: Hoe maak ik een voorbeelddocument en voeg ik er een tekstfragment aan toe?

A: In de tutorial gebruik je de`Document` class om een voorbeeld-PDF-document te maken en een tekstfragment toe te voegen. Dit tekstfragment dient als trigger voor het weergeven van het verborgen tekstblok.

#### Vraag: Hoe vind ik het tekstfragment dat het verborgen tekstblok activeert?

 A: In de tutorial wordt gedemonstreerd hoe u een`TextFragmentAbsorber` object om het tekstfragment te vinden dat de weergave van het verborgen tekstblok activeert. Er wordt gezocht naar een specifieke tekstreeks in het PDF-document.

#### Vraag: Hoe kan ik het verborgen tekstveld maken en aanpassen?

 A: Je maakt een`TextBoxField` object dat het verborgen tekstveld vertegenwoordigt. De tutorial biedt code om verschillende eigenschappen in te stellen, zoals positie, waarde, uiterlijk en gedrag van het verborgen tekstveld.

#### Vraag: Hoe maak ik een onzichtbare knop die aan het verborgen tekstblok is gekoppeld?

 A: Er wordt een onzichtbaar knoppenveld gemaakt met behulp van de`ButtonField` klas. Dit knopveld bevindt zich bovenop het triggertekstfragment en bevat acties die verband houden met muisinvoer- en -uitstapgebeurtenissen. Deze acties bepalen de zichtbaarheid van het verborgen tekstblok.

#### Vraag: Kan ik het uiterlijk van het verborgen tekstblok en het triggergebied aanpassen?

A: Ja, u kunt verschillende eigenschappen van zowel het verborgen tekstveld als de onzichtbare knop aanpassen, inclusief lettertype, kleur, grootte en positionering.

#### Vraag: Hoe sla ik het gewijzigde document met het verborgen tekstblok op?

 A: De tutorial laat zien hoe u het gewijzigde document kunt opslaan met behulp van de`Save` werkwijze van de`Document` klas.