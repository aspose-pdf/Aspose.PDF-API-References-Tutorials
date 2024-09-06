---
title: Javascript instellen
linktitle: Javascript instellen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om JavaScript in formuliervelden in PDF-bestanden in te stellen.
type: docs
weight: 270
url: /nl/net/programming-with-forms/set-java-script/
---
In deze handleiding leggen we stap voor stap uit hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om JavaScript te definiëren in een formulierveld van een PDF-document. We laten u zien hoe u JavaScript-acties configureert om specifieke bewerkingen uit te voeren op het tekstveld.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een .NET-ontwikkelomgeving die op uw systeem is geïnstalleerd.
- De Aspose.PDF bibliotheek voor .NET. U kunt deze downloaden van de officiële website van Aspose.

## Stap 1: De documentdirectory configureren

 De eerste stap is het configureren van de documentdirectory waar het PDF-bestand waar u aan wilt werken zich bevindt. U kunt de`dataDir` variabele om het pad naar de directory op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zorg ervoor dat u deze vervangt`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het invoer-PDF-bestand laden

 In deze stap laden we het invoer-PDF-bestand met behulp van de`Document` klasse van Aspose.PDF.

```csharp
// Laad invoer PDF-bestand
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Zorg ervoor dat het PDF-invoerbestand zich in de opgegeven documentenmap bevindt.

## Stap 3: Toegang krijgen tot het tekstvakveld

 Om JavaScript op een specifiek tekstveld toe te passen, moeten we eerst toegang tot dat veld krijgen. In dit voorbeeld nemen we aan dat het tekstveld "textbox1" heet. Gebruik de`doc.Form["textbox1"]` methode om de overeenkomstige te krijgen`TextBoxField` voorwerp.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Zorg ervoor dat het opgegeven tekstveld bestaat in het PDF-invoerbestand.

## Stap 4: JavaScript-acties configureren

 Nu we toegang hebben tot het tekstveld, kunnen we de JavaScript-acties configureren die aan dit veld zijn gekoppeld. In dit voorbeeld gebruiken we twee acties:`OnModifyCharacter` En`OnFormat` Deze acties worden gedefinieerd met behulp van`JavascriptAction` objecten.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Zorg ervoor dat u de JavaScript-acties aanpast aan uw behoeften.

## Stap 5: De beginveldwaarde instellen

Voordat we de resulterende PDF opslaan, kunnen we een beginwaarde voor het tekstveld instellen. In dit voorbeeld stellen we de waarde "123" in voor het veld.

```csharp
field.Value = "123";
```

Pas deze waarde aan uw behoeften aan.

## Stap 6: Het resulterende PDF-bestand opslaan

 Nu we klaar zijn met het instellen van het tekstveld en de JavaScript-acties, kunnen we de resulterende PDF opslaan met behulp van de`Save` methode van de`Document` klas.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Opslaan resulterende PDF
doc.Save(dataDir);
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor het resulterende PDF-bestand opgeeft.


### Voorbeeldbroncode voor Set Java Script met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad invoer PDF-bestand
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 cijfers na punt
// Geen scheidingsteken
// Negatieve stijl = min
// Geen valuta
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Initiële veldwaarde instellen
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Resulterende PDF opslaan
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusie

In deze handleiding hebben we geleerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om JavaScript in een formulierveld van een PDF-document in te stellen. Door de beschreven stappen te volgen, kunt u JavaScript-acties aanpassen om verschillende bewerkingen op tekstvelden uit te voeren. U kunt de functies van Aspose.PDF voor .NET verder verkennen om de mogelijkheden van het manipuleren van PDF-bestanden uit te breiden.


### Veelgestelde vragen

#### V: Kan ik Aspose.PDF voor .NET gebruiken om JavaScript toe te voegen aan andere formulierelementen, zoals selectievakjes en keuzerondjes?

 A: Ja, Aspose.PDF voor .NET stelt u in staat om JavaScript toe te voegen aan verschillende formulierelementen, waaronder selectievakjes, keuzerondjes en vervolgkeuzelijsten. U kunt de`JavascriptAction` klasse om JavaScript-acties voor verschillende formulierelementen te definiëren.

#### V: Is het mogelijk om gebruikersinvoer in formuliervelden te valideren met behulp van JavaScript?

 A: Ja, u kunt JavaScript gebruiken om gebruikersinvoer in formuliervelden te valideren. Door JavaScript-acties te definiëren zoals`OnBlur` of`OnKeystroke` Voor een formulierveld kunt u de ingevoerde gegevens valideren en indien nodig foutmeldingen weergeven.

#### V: Kan ik complexe JavaScript-functies uitvoeren met Aspose.PDF voor .NET?

 A: Ja, u kunt complexe JavaScript-functies uitvoeren met Aspose.PDF voor .NET. U hebt de flexibiliteit om aangepaste JavaScript-functies te definiëren en deze binnen de`JavascriptAction`.

#### V: Ondersteunt Aspose.PDF voor .NET andere JavaScript-gebeurtenissen dan die genoemd in deze tutorial?

 A: Ja, Aspose.PDF voor .NET ondersteunt een breed scala aan JavaScript-gebeurtenissen, waaronder`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , En`OnMouseUp`, onder andere. U kunt deze gebeurtenissen gebruiken om JavaScript-acties te activeren op basis van gebruikersinteracties.

#### V: Kan ik Aspose.PDF voor .NET gebruiken om JavaScript-code uit bestaande PDF-documenten te extraheren?

 A: Aspose.PDF voor .NET biedt de mogelijkheid om JavaScript-code uit bestaande PDF-documenten te extraheren. U kunt de`JavascriptAction` klasse en andere relevante methoden om JavaScript-acties in een PDF-formulier te openen en te analyseren.