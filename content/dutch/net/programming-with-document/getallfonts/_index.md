---
title: Alle lettertypen in PDF-bestand ophalen
linktitle: Alle lettertypen in PDF-bestand ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om alle lettertypen die in een PDF-bestand worden gebruikt, programmatisch op te halen met behulp van deze stapsgewijze handleiding en voorbeeldcode.
type: docs
weight: 160
url: /nl/net/programming-with-document/getallfonts/
---
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PDF-bestanden kunnen werken. Een van de functies die het biedt, is de mogelijkheid om alle lettertypen te krijgen die in een PDF-bestand worden gebruikt. Dit kan handig zijn als u de lettertypen in een PDF-bestand programmatisch moet analyseren of manipuleren.

In deze tutorial bespreken we hoe u Aspose.PDF voor .NET kunt gebruiken om alle lettertypen te krijgen die in een PDF-document worden gebruikt. We bieden een stapsgewijze handleiding over hoe u dit kunt doen, samen met voorbeeldbroncode.

## Stap 1: Maak een nieuwe C# Console-toepassing
Om te beginnen, maak een nieuwe C# Console Application in Visual Studio. U kunt het een naam geven die u wilt. Zodra het project is gemaakt, moet u een verwijzing toevoegen naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de Aspose.PDF-naamruimte
Voeg de volgende regel code bovenaan uw C#-bestand toe om de Aspose.PDF-naamruimte te importeren:

```csharp
using Aspose.Pdf;
```

## Stap 3: Het PDF-document laden
Laad het PDF-document waaruit u de lettertypen wilt halen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 4: Verzamel alle lettertypen
Ontvang alle lettertypen die in het PDF-document worden gebruikt:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Stap 5: Alle lettertypen afdrukken
Print alle lettertypen die in het PDF-document worden gebruikt:

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

### Voorbeeldbroncode voor Get All Fonts met Aspose.PDF voor .NET
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

## Conclusie
In deze tutorial hebben we besproken hoe u alle lettertypen kunt ophalen die in een PDF-document worden gebruikt met Aspose.PDF voor .NET. Het ophalen van alle lettertypen die in een PDF-document worden gebruikt, kan handig zijn als u de lettertypen in een PDF-document programmatisch wilt analyseren of manipuleren. Aspose.PDF voor .NET biedt een eenvoudige en gebruiksvriendelijke API om met PDF-documenten te werken, inclusief het ophalen van alle lettertypen die in een PDF-document worden gebruikt.

### Veelgestelde vragen

#### V: Waarom zou ik alle lettertypen nodig hebben die in een PDF-document voorkomen?

A: Het kan handig zijn om alle lettertypen te krijgen die in een PDF-document worden gebruikt, als u de lettertypen programmatisch wilt analyseren of bewerken voor verschillende doeleinden, zoals het vervangen of aanpassen van lettertypen.

#### V: Hoe kan ik met Aspose.PDF voor .NET alle lettertypen ophalen die in een PDF-document worden gebruikt?

 A: U kunt alle lettertypen die in een PDF-document worden gebruikt, verkrijgen met Aspose.PDF voor .NET door de`GetAllFonts` methode van de`FontUtilities` klasse. Deze methode retourneert een array van`Aspose.Pdf.Text.Font` objecten, die de lettertypen voorstellen die in het PDF-document worden gebruikt.

#### V: Kan ik lettertypen filteren op basis van bepaalde criteria?

A: Ja, u kunt lettertypen filteren op basis van bepaalde criteria met Aspose.PDF voor .NET. Nadat u alle lettertypen hebt opgehaald, kunt u de lettertypen programmatisch analyseren en indien nodig filterlogica toepassen.

#### V: Is Aspose.PDF voor .NET compatibel met verschillende lettertypeformaten?

A: Ja, Aspose.PDF voor .NET is compatibel met verschillende lettertypeformaten, waaronder TrueType, OpenType en Type 1-lettertypen. Het kan met verschillende lettertypeformaten werken en deze verwerken tijdens het bewerken van PDF-documenten.