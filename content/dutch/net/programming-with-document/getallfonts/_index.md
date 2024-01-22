---
title: Krijg alle lettertypen in PDF-bestand
linktitle: Krijg alle lettertypen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om alle lettertypen die in een PDF-bestand worden gebruikt programmatisch te verkrijgen met deze stapsgewijze handleiding en voorbeeldcode.
type: docs
weight: 160
url: /nl/net/programming-with-document/getallfonts/
---
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PDF-bestanden kunnen werken. Een van de functies die het biedt, is de mogelijkheid om alle lettertypen te verkrijgen die in een PDF-bestand worden gebruikt. Dit kan handig zijn als u de lettertypen in een PDF-bestand programmatisch moet analyseren of manipuleren.

In deze zelfstudie bespreken we hoe u Aspose.PDF voor .NET kunt gebruiken om alle lettertypen te verkrijgen die in een PDF-document worden gebruikt. We zullen een stapsgewijze handleiding geven over hoe u dit kunt doen, samen met voorbeeldbroncode.

## Stap 1: Maak een nieuwe C#-consoletoepassing
Maak om te beginnen een nieuwe C#-consoletoepassing in Visual Studio. Je kunt het noemen zoals je wilt. Nadat het project is gemaakt, moet u een verwijzing toevoegen naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de Aspose.PDF-naamruimte
Voeg de volgende regel code toe bovenaan uw C#-bestand om de Aspose.PDF-naamruimte te importeren:

```csharp
using Aspose.Pdf;
```

## Stap 3: Laad het PDF-document
Laad het PDF-document waarvan u de lettertypen wilt ophalen:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 4: Verkrijg alle lettertypen
Haal alle lettertypen op die in het PDF-document worden gebruikt:

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

## Stap 5: Druk alle lettertypen af
Druk alle lettertypen af die in het PDF-document worden gebruikt:

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
In deze zelfstudie hebben we besproken hoe u alle lettertypen kunt verkrijgen die in een PDF-document worden gebruikt met behulp van Aspose.PDF voor .NET. Het kan handig zijn om alle lettertypen te verkrijgen die in een PDF-document worden gebruikt als u de lettertypen in een PDF-document programmatisch moet analyseren of manipuleren. Aspose.PDF voor .NET biedt een eenvoudige en gebruiksvriendelijke API om met PDF-documenten te werken, inclusief het ophalen van alle lettertypen die in een PDF-document worden gebruikt.

### Veelgestelde vragen

#### Vraag: Waarom zou ik alle lettertypen nodig hebben die in een PDF-document worden gebruikt?

A: Het kan handig zijn om alle lettertypen te verkrijgen die in een PDF-document worden gebruikt als u de lettertypen programmatisch moet analyseren of manipuleren voor verschillende doeleinden, zoals het vervangen van lettertypen of het aanpassen van lettertypen.

#### Vraag: Hoe kan ik alle lettertypen verkrijgen die in een PDF-document worden gebruikt met Aspose.PDF voor .NET?

 A: U kunt alle lettertypen die in een PDF-document worden gebruikt, verkrijgen met Aspose.PDF voor .NET door de`GetAllFonts` werkwijze van de`FontUtilities` klas. Deze methode retourneert een array van`Aspose.Pdf.Text.Font` objecten, die de lettertypen vertegenwoordigen die in het PDF-document worden gebruikt.

#### Vraag: Kan ik lettertypen filteren op basis van bepaalde criteria?

A: Ja, u kunt lettertypen filteren op basis van bepaalde criteria met behulp van Aspose.PDF voor .NET. Nadat u alle lettertypen heeft opgehaald, kunt u de lettertypen programmatisch analyseren en indien nodig filterlogica toepassen.

#### Vraag: Is Aspose.PDF voor .NET compatibel met verschillende lettertypeformaten?

A: Ja, Aspose.PDF voor .NET is compatibel met verschillende lettertypeformaten, waaronder TrueType-, OpenType- en Type 1-lettertypen. Het kan met verschillende lettertypeformaten werken en deze verwerken tijdens het manipuleren van PDF-documenten.