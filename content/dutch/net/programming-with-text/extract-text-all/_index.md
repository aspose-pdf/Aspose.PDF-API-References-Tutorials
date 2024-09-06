---
title: Alle tekst uit PDF-bestand extraheren
linktitle: Tekst extraheren in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alle tekst uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-text/extract-text-all/
---
Deze tutorial begeleidt u door het proces van het extraheren van alle tekst in een PDF-bestand met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waaruit u tekst wilt extraheren het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand doorgeven.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Stap 5: Alle tekst extraheren
 Maak een`TextAbsorber`object om tekst uit het document te halen. Accepteer vervolgens de absorber voor alle pagina's.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Stap 6: De geëxtraheerde tekst ophalen
 Krijg toegang tot de geëxtraheerde tekst van de`TextAbsorber` voorwerp.

```csharp
string extractedText = textAbsorber.Text;
```

## Stap 7: Sla de geëxtraheerde tekst op
 Maak een`TextWriter` en open het bestand waar u de geëxtraheerde tekst wilt opslaan. Schrijf de geëxtraheerde tekst naar het bestand en sluit de stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Voorbeeldbroncode voor Extract Text All met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Maak een TextAbsorber-object om tekst te extraheren
TextAbsorber textAbsorber = new TextAbsorber();
// Accepteer de absorber voor alle pagina's
pdfDocument.Pages.Accept(textAbsorber);
// Haal de geëxtraheerde tekst op
string extractedText = textAbsorber.Text;
// Maak een schrijver en open het bestand
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Schrijf een tekstregel naar het bestand
tw.WriteLine(extractedText);
// Sluit de stroom
tw.Close();
```

## Conclusie
U hebt met succes alle tekst uit een PDF-document geëxtraheerd met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial dient als een gids om u te helpen alle tekst uit een PDF-bestand te halen met Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt stapsgewijze instructies om deze taak uit te voeren.

#### V: Welke naamruimten moet ik importeren?

A: In het codebestand waaruit u tekst wilt extraheren, voegt u de volgende richtlijnen toe aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand opgeven.

#### V: Hoe haal ik alle tekst uit het document?

 A: Stap 5 omvat het maken van een`TextAbsorber` object om tekst uit het PDF-document te halen. Vervolgens accepteert u de absorber voor alle pagina's.

#### V: Hoe krijg ik toegang tot de geëxtraheerde tekst?

 A: Stap 6 begeleidt u bij het openen van de geëxtraheerde tekst uit de`TextAbsorber` voorwerp.

#### V: Hoe kan ik de geëxtraheerde tekst opslaan in een bestand?

 A: In stap 7 maak je een`TextWriter`, open het bestand waarin u de geëxtraheerde tekst wilt opslaan, schrijf de geëxtraheerde tekst naar het bestand en sluit vervolgens de stream.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u alle tekst uit een PDF-document kunt extraheren met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in een opgegeven uitvoerbestand, zodat u de tekstuele inhoud van het document kunt analyseren en manipuleren.