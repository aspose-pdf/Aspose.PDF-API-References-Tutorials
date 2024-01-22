---
title: Tekstvak
linktitle: Tekstvak
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tekstveld in een PDF-document maakt met Aspose.PDF voor .NET.
type: docs
weight: 290
url: /nl/net/programming-with-forms/text-box/
---
In deze handleiding leggen we stap voor stap uit hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om een tekstveld in een PDF-document te maken. We laten u zien hoe u het document opent, het tekstveld maakt, de eigenschappen ervan aanpast en de bewerkte PDF opslaat.

## Stap 1: De documentmap configureren

 De eerste stap is het configureren van de documentmap waarin het PDF-bestand staat waaraan u wilt werken. U kunt gebruik maken van de`dataDir` variabele om het mappad op te geven.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Het PDF-document openen

In deze stap openen we het PDF-document met behulp van de`Document` klasse van Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Zorg ervoor dat het PDF-bestand aanwezig is in de opgegeven documentenmap.

## Stap 3: Het tekstveld maken

 We zullen een tekstveld maken met behulp van de`TextBoxField` klas. U kunt positiecoördinaten en veldgrootte opgeven met behulp van de`Rectangle` klas.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Pas indien nodig de coördinaten, grootte, gedeeltelijke naam en tekstveldwaarde aan.

## Stap 4: Pas de eigenschappen van tekstvelden aan

In deze stap passen we de eigenschappen van het tekstveld aan, zoals rand, kleur, enz.

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

 Ten slotte kunnen we de gewijzigde PDF opslaan met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Zorg ervoor dat u het volledige pad en de bestandsnaam voor de bewerkte PDF opgeeft.

### Voorbeeldbroncode voor tekstvak met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Maak een veld
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = nieuwe rand(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Voeg een veld toe aan het document
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Bewaar gewijzigde PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusie

In deze handleiding hebben we geleerd hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om een tekstveld in een PDF-document te maken. Door de beschreven stappen te volgen, kunt u de eigenschappen van het tekstveld aanpassen en indien nodig aan het document toevoegen. Voel je vrij om de functies van Aspose.PDF voor .NET verder te verkennen om de mogelijkheden voor het manipuleren van PDF-bestanden uit te breiden.

### Veelgestelde vragen

#### Vraag: Kan ik Aspose.PDF voor .NET gebruiken om meerdere tekstvelden in één PDF-document te maken?

A: Ja, u kunt meerdere tekstvelden in één PDF-document maken met Aspose.PDF voor .NET. Herhaal eenvoudigweg het proces van het maken en aanpassen van tekstvelden voor elke gewenste locatie in het document.

#### Vraag: Hoe kan ik het uiterlijk van het tekstveld aanpassen, zoals lettergrootte en kleur?

A: U kunt het uiterlijk van het tekstveld aanpassen door de eigenschappen ervan aan te passen, zoals lettergrootte, letterstijl, kleur, randstijl, achtergrondkleur en meer. In de meegeleverde voorbeeldbroncode zijn de randbreedte, het randstreepjespatroon en de tekstkleur aangepast.

#### Vraag: Is het mogelijk om de door de gebruiker ingevoerde tekst uit het gemaakte tekstveld te extraheren?

A: Ja, u kunt de door de gebruiker ingevoerde tekst uit het gemaakte tekstveld halen. Nadat gebruikers het tekstveld in het PDF-document hebben ingevuld, kunt u de veldwaarde programmatisch ophalen met Aspose.PDF voor .NET.

#### Vraag: Kan ik tekstvelden aan een bestaand PDF-document toevoegen zonder een nieuw document te maken?

A: Ja, u kunt tekstvelden aan een bestaand PDF-document toevoegen zonder een nieuw document te maken. Aspose.PDF voor .NET biedt de mogelijkheid om bestaande PDF-documenten te wijzigen, inclusief het toevoegen van tekstvelden, selectievakjes en andere formulierelementen.

#### Vraag: Ondersteunt Aspose.PDF voor .NET andere typen formuliervelden, zoals selectievakjes en keuzerondjes?

A: Ja, Aspose.PDF voor .NET ondersteunt verschillende soorten formuliervelden, waaronder selectievakjes, keuzerondjes, vervolgkeuzelijsten en meer. U kunt de bibliotheek gebruiken om met verschillende soorten formulierelementen in PDF-documenten te werken.