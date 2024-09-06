---
title: Bepaal regelafbreking in PDF-bestand
linktitle: Bepaal regelafbreking in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u regeleinden in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-text/determine-line-break/
---
Deze tutorial begeleidt u door het proces van het bepalen van regeleinden in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waar u regeleinden wilt bepalen, het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw Document-exemplaar
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages`verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 6: Voeg tekstfragmenten toe met regelafbrekingen
Maak een lus om meerdere tekstfragmenten aan de pagina toe te voegen, elk met een alinea met regeleinden.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Stap 7: Sla het PDF-document op en extraheer de regelafbrekingsinformatie
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` object. Haal vervolgens de regelafbrekingsinformatie op met behulp van de`GetNotifications` methode van de gewenste pagina.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Voorbeeldbroncode voor regelafbreking bepalen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Conclusie
U hebt met succes regeleinden in een PDF-document bepaald met Aspose.PDF voor .NET. De regeleindinformatie is geëxtraheerd en opgeslagen in een tekstbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich vooral?

A: Deze tutorial is gericht op het begeleiden van u door het proces van het bepalen van regeleinden in een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de benodigde stappen om dit te bereiken.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waar u regeleinden wilt bepalen:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een nieuw Document-exemplaar?

 A: In stap 4 maakt u een nieuwe`Document` object met behulp van de verstrekte code.

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling.

#### V: Hoe voeg ik tekstfragmenten met regelafbrekingen toe?

A: In stap 6 maakt u een lus om meerdere tekstfragmenten aan de pagina toe te voegen, elk met een alinea met regeleinden.

#### V: Hoe kan ik het PDF-document opslaan en informatie over regeleinden extraheren?

 A: In stap 7 slaat u het PDF-document op met behulp van de`Save` methode van de`Document` object. Vervolgens extraheert u de regelafbrekingsinformatie met behulp van de`GetNotifications`methode van de gewenste pagina en sla deze op in een tekstbestand.

#### V: Wat is het doel van de geëxtraheerde regelovergangsinformatie?

A: De geëxtraheerde regelafbrekingsinformatie biedt details over de regelafbrekingen en meldingen die aanwezig zijn in het PDF-document. Dit kan handig zijn voor het analyseren en begrijpen van hoe tekst en alinea's in het document zijn gestructureerd.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u regelafbrekingen in een PDF-document kunt bepalen met Aspose.PDF voor .NET. U kunt deze kennis gebruiken om regelafbrekingsinformatie programmatisch uit PDF-bestanden te halen en analyseren.