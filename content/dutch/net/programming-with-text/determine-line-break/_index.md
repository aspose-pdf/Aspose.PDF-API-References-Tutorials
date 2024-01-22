---
title: Regeleinde in PDF-bestand bepalen
linktitle: Regeleinde in PDF-bestand bepalen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u regeleinden in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-text/determine-line-break/
---
Deze tutorial leidt u door het proces van het bepalen van regeleinden in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
In het codebestand waarin u regeleinden wilt bepalen, voegt u het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw documentexemplaar
 Instantieer een nieuwe`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` werkwijze van de`Pages`verzameling. In de opgegeven code wordt de nieuwe pagina aan de variabele toegewezen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 6: Voeg tekstfragmenten toe met regeleinden
Maak een lus om meerdere tekstfragmenten aan de pagina toe te voegen, die elk een alinea met regeleinden bevatten.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## Stap 7: Sla het PDF-document op en extraheer de regeleinde-informatie
 Sla het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Extraheer vervolgens de regeleinde-informatie met behulp van de`GetNotifications` methode van de gewenste pagina.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Voorbeeldbroncode voor Regeleinde bepalen met Aspose.PDF voor .NET 
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
U hebt met succes regeleinden in een PDF-document bepaald met Aspose.PDF voor .NET. De regeleinde-informatie is geëxtraheerd en opgeslagen in een tekstbestand.

### Veelgestelde vragen

#### Vraag: Wat is de belangrijkste focus van deze tutorial?

A: Deze tutorial is erop gericht u te begeleiden bij het bepalen van regeleinden in een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen om dit te bereiken.

#### Vraag: Welke naamruimten moet ik importeren voor deze zelfstudie?

A: In het codebestand waarin u regeleinden wilt bepalen, importeert u de volgende naamruimten aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de regel in de code`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe maak ik een nieuw documentexemplaar?

 A: In stap 4 maakt u een nieuw bestand`Document` object met behulp van de opgegeven code.

#### Vraag: Hoe voeg ik een pagina toe aan het document?

 A: In stap 5 voegt u een nieuwe pagina aan het document toe met behulp van de`Add` werkwijze van de`Pages` verzameling.

#### Vraag: Hoe voeg ik tekstfragmenten met regeleinden toe?

A: In stap 6 maakt u een lus om meerdere tekstfragmenten aan de pagina toe te voegen, die elk een alinea met regeleinden bevatten.

#### Vraag: Hoe kan ik het PDF-document opslaan en informatie over regeleinden extraheren?

 A: In stap 7 slaat u het PDF-document op met behulp van de`Save` werkwijze van de`Document` voorwerp. Vervolgens extraheert u de regeleinde-informatie met behulp van de`GetNotifications` methode van de gewenste pagina en sla deze op in een tekstbestand.

#### Vraag: Wat is het doel van de geëxtraheerde regeleinde-informatie?

A: De geëxtraheerde informatie over regeleinden biedt details over de regeleinden en meldingen in het PDF-document. Dit kan handig zijn voor het analyseren en begrijpen van de manier waarop tekst en alinea's in het document zijn gestructureerd.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u geleerd hoe u regeleinden in een PDF-document kunt bepalen met behulp van Aspose.PDF voor .NET. U kunt deze kennis gebruiken om regeleindinformatie programmatisch uit PDF-bestanden te extraheren en te analyseren.