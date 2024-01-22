---
title: Javascript instellen
linktitle: Javascript instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET gebruikt om JavaScript in formuliervelden in PDF-bestanden in te stellen.
type: docs
weight: 270
url: /nl/net/programming-with-forms/set-java-script/
---
In deze handleiding gaan we stap voor stap uitleggen hoe je de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om JavaScript te definiëren in een formulierveld van een PDF-document. We laten u zien hoe u JavaScript-acties configureert om specifieke bewerkingen op het tekstveld uit te voeren.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een .NET-ontwikkelomgeving die op uw systeem is geïnstalleerd.
- De Aspose.PDF-bibliotheek voor .NET. Je kunt het downloaden van de officiële website van Aspose.

## Stap 1: De documentmap configureren

 De eerste stap is het configureren van de documentmap waarin het PDF-bestand staat waaraan u wilt werken. U kunt gebruik maken van de`dataDir` variabele om het mappad op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het invoer-PDF-bestand laden

In deze stap laden we het invoer-PDF-bestand met behulp van de`Document` klasse van Aspose.PDF.

```csharp
// Laad het invoer-PDF-bestand
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Zorg ervoor dat het invoer-PDF-bestand aanwezig is in de opgegeven documentenmap.

## Stap 3: Toegang tot het TextBox-veld

 Om JavaScript op een specifiek tekstveld toe te passen, moeten we eerst dat veld openen. In dit voorbeeld gaan we ervan uit dat het tekstveld "textbox1" heet. Gebruik de`doc.Form["textbox1"]` methode om het overeenkomstige te verkrijgen`TextBoxField` voorwerp.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Zorg ervoor dat het opgegeven tekstveld bestaat in het invoer-PDF-bestand.

## Stap 4: Configureer JavaScript-acties

 Nu we toegang hebben tot het tekstveld, kunnen we de JavaScript-acties configureren die aan dit veld zijn gekoppeld. In dit voorbeeld gebruiken we twee acties:`OnModifyCharacter` En`OnFormat` . Deze acties worden gedefinieerd met behulp van`JavascriptAction` voorwerpen.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Zorg ervoor dat u de JavaScript-acties aanpast aan uw behoeften.

## Stap 5: De initiële veldwaarde instellen

Voordat we de resulterende PDF opslaan, kunnen we een initiële waarde voor het tekstveld instellen. In dit voorbeeld stellen we de waarde "123" in voor het veld.

```csharp
field.Value = "123";
```

Pas deze waarde aan uw behoeften aan.

## Stap 6: De resulterende PDF opslaan

 Nu we klaar zijn met het instellen van het tekstveld en JavaScript-acties, kunnen we de resulterende PDF opslaan met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Sla de resulterende PDF op
doc.Save(dataDir);
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor de resulterende PDF opgeeft.


### Voorbeeldbroncode voor Java Script instellen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad het invoer-PDF-bestand
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 cijfers na punt
// Geen scheidingsteken
// Neg-stijl = min
// Geen valuta
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Stel de initiële veldwaarde in
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Bewaar de resulterende PDF
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusie

In deze handleiding hebben we geleerd hoe we de Aspose.PDF-bibliotheek voor .NET kunnen gebruiken om JavaScript in een formulierveld van een PDF-document in te stellen. Door de beschreven stappen te volgen, kunt u JavaScript-acties aanpassen om verschillende bewerkingen op tekstvelden uit te voeren. Voel je vrij om de functies van Aspose.PDF voor .NET verder te verkennen om de mogelijkheden voor het manipuleren van PDF-bestanden uit te breiden.


### Veelgestelde vragen

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om JavaScript toe te voegen aan andere formulierelementen, zoals selectievakjes en keuzerondjes?

 A: Ja, met Aspose.PDF voor .NET kunt u JavaScript toevoegen aan verschillende formulierelementen, waaronder selectievakjes, keuzerondjes en vervolgkeuzelijsten. U kunt gebruik maken van de`JavascriptAction` class om JavaScript-acties voor verschillende formulierelementen te definiëren.

#### Vraag: Is het mogelijk om gebruikersinvoer te valideren met JavaScript in formuliervelden?

 A: Ja, u kunt JavaScript gebruiken om gebruikersinvoer in formuliervelden te valideren. Door JavaScript-acties te definiëren zoals`OnBlur` of`OnKeystroke` voor een formulierveld kunt u de ingevoerde gegevens valideren en indien nodig foutmeldingen weergeven.

#### Vraag: Kan ik complexe JavaScript-functies uitvoeren met Aspose.PDF voor .NET?

 A: Ja, u kunt complexe JavaScript-functies uitvoeren met Aspose.PDF voor .NET. U heeft de flexibiliteit om aangepaste JavaScript-functies te definiëren en deze aan te roepen binnen de`JavascriptAction`.

#### Vraag: Ondersteunt Aspose.PDF voor .NET andere JavaScript-gebeurtenissen dan die genoemd in deze tutorial?

 A: Ja, Aspose.PDF voor .NET ondersteunt een breed scala aan JavaScript-gebeurtenissen, waaronder`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , En`OnMouseUp`, onder andere. U kunt deze gebeurtenissen gebruiken om JavaScript-acties te activeren op basis van gebruikersinteracties.

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om JavaScript-code uit bestaande PDF-documenten te extraheren?

 A: Aspose.PDF voor .NET biedt de mogelijkheid om JavaScript-code uit bestaande PDF-documenten te extraheren. U kunt gebruik maken van de`JavascriptAction` class en andere relevante methoden om JavaScript-acties in PDF-vorm te openen en te analyseren.