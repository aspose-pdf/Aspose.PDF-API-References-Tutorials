---
title: Tekstvak
linktitle: Tekstvak
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekstveld in een PDF-document maakt met Aspose.PDF voor .NET.
type: docs
weight: 290
url: /nl/net/programming-with-forms/text-box/
---
In deze handleiding leggen we stap voor stap uit hoe u de Aspose.PDF-bibliotheek voor .NET gebruikt om een tekstveld in een PDF-document te maken. We laten u zien hoe u het document opent, het tekstveld maakt, de eigenschappen ervan aanpast en de bewerkte PDF opslaat.

## Stap 1: De documentdirectory configureren

 De eerste stap is het configureren van de documentdirectory waar het PDF-bestand waar u aan wilt werken zich bevindt. U kunt de`dataDir` variabele om het pad naar de directory op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zorg ervoor dat u deze vervangt`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het PDF-document openen

 In deze stap openen we het PDF-document met behulp van de`Document` klasse van Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Controleer of het PDF-bestand zich in de opgegeven documentenmap bevindt.

## Stap 3: Het tekstveld aanmaken

 We gaan een tekstveld maken met behulp van de`TextBoxField` klasse. U kunt positiecoördinaten en veldgrootte opgeven met behulp van de`Rectangle` klas.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Pas indien nodig de coördinaten, grootte, gedeeltelijke naam en tekstveldwaarde aan.

## Stap 4: Pas de eigenschappen van het tekstveld aan

In deze stap passen we de eigenschappen van het tekstveld aan, zoals rand, kleur, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Pas de eigenschappen van het tekstveld aan volgens uw voorkeuren.

## Stap 5: Het veld toevoegen aan het document

Nu we het tekstveld hebben gemaakt en geconfigureerd, kunnen we het aan het PDF-document toevoegen.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Stap 6: De gewijzigde PDF opslaan

 Ten slotte kunnen we de gewijzigde PDF opslaan met behulp van de`Save` methode van de`Document` klas.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor de bewerkte PDF opgeeft.

### Voorbeeldbroncode voor tekstvak met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Een veld aanmaken
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = nieuwe Border(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Veld toevoegen aan het document
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Gewijzigde PDF opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusie

In deze handleiding hebben we geleerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om een tekstveld in een PDF-document te maken. Door de beschreven stappen te volgen, kunt u de eigenschappen van het tekstveld aanpassen en het indien nodig aan het document toevoegen. U kunt de functies van Aspose.PDF voor .NET verder verkennen om de mogelijkheden voor het manipuleren van PDF-bestanden uit te breiden.

### Veelgestelde vragen

#### V: Kan ik Aspose.PDF voor .NET gebruiken om meerdere tekstvelden in één PDF-document te maken?

A: Ja, u kunt meerdere tekstvelden in één PDF-document maken met Aspose.PDF voor .NET. Herhaal gewoon het proces van het maken en aanpassen van tekstvelden voor elke gewenste locatie in het document.

#### V: Hoe kan ik het uiterlijk van het tekstveld aanpassen, zoals de lettergrootte en kleur?

A: U kunt het uiterlijk van het tekstveld aanpassen door de eigenschappen ervan aan te passen, zoals lettergrootte, lettertype, kleur, randstijl, achtergrondkleur en meer. In de meegeleverde voorbeeldbroncode worden de randbreedte, het randstreeppatroon en de tekstkleur aangepast.

#### V: Is het mogelijk om de door de gebruiker ingevoerde tekst uit het gemaakte tekstveld te halen?

A: Ja, u kunt de door de gebruiker ingevoerde tekst uit het gemaakte tekstveld halen. Nadat gebruikers het tekstveld in het PDF-document hebben ingevuld, kunt u de veldwaarde programmatisch ophalen met Aspose.PDF voor .NET.

#### V: Kan ik tekstvelden toevoegen aan een bestaand PDF-document zonder een nieuw document te maken?

A: Ja, u kunt tekstvelden toevoegen aan een bestaand PDF-document zonder een nieuw document te maken. Aspose.PDF voor .NET biedt de mogelijkheid om bestaande PDF-documenten te wijzigen, inclusief het toevoegen van tekstvelden, selectievakjes en andere formulierelementen.

#### V: Ondersteunt Aspose.PDF voor .NET andere typen formuliervelden, zoals selectievakjes en keuzerondjes?

A: Ja, Aspose.PDF voor .NET ondersteunt verschillende typen formuliervelden, waaronder selectievakjes, keuzerondjes, vervolgkeuzelijsten en meer. U kunt de bibliotheek gebruiken om met verschillende typen formulierelementen in PDF-documenten te werken.