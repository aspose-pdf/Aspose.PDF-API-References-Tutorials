---
title: Extraheer tekst allemaal in PDF-bestand
linktitle: Tekst AllIn PDF-bestand uitpakken
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alle tekst uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-text/extract-text-all/
---
Deze tutorial begeleidt u bij het extraheren van alle tekst in een PDF-bestand met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waarin u tekst wilt extraheren het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document`constructor en geef het pad door aan het invoer-PDF-bestand.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Stap 5: Extraheer alle tekst
 Maak een`TextAbsorber`object om tekst uit het document te extraheren. Accepteer vervolgens de absorber voor alle pagina's.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Stap 6: Haal de geëxtraheerde tekst op
 Toegang tot de geëxtraheerde tekst uit het`TextAbsorber` voorwerp.

```csharp
string extractedText = textAbsorber.Text;
```

## Stap 7: Sla de geëxtraheerde tekst op
 Maak een`TextWriter` en open het bestand waarin u de geëxtraheerde tekst wilt opslaan. Schrijf de geëxtraheerde tekst naar het bestand en sluit de stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Voorbeeldbroncode voor Extract Text All met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Maak een TextAbsorber-object om tekst te extraheren
TextAbsorber textAbsorber = new TextAbsorber();
// Accepteer het absorber voor alle pagina's
pdfDocument.Pages.Accept(textAbsorber);
// Haal de geëxtraheerde tekst op
string extractedText = textAbsorber.Text;
// Maak een schrijver en open het bestand
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Schrijf een regel tekst naar het bestand
tw.WriteLine(extractedText);
// Sluit de stroom
tw.Close();
```

## Conclusie
U hebt met succes alle tekst uit een PDF-document geëxtraheerd met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial dient als leidraad om u te helpen alle tekst uit een PDF-bestand te extraheren met Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt stapsgewijze instructies om deze taak te volbrengen.

#### Vraag: Welke naamruimten moet ik importeren?

A: In het codebestand waarin u tekst wilt extraheren, neemt u de volgende gebruiksinstructies op aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het invoer-PDF-bestand opgeven.

#### Vraag: Hoe extraheer ik alle tekst uit het document?

 A: Stap 5 omvat het maken van een`TextAbsorber` object om tekst uit het PDF-document te extraheren. Vervolgens accepteert u de absorber voor alle pagina's.

#### Vraag: Hoe krijg ik toegang tot de geëxtraheerde tekst?

 A: Stap 6 begeleidt u bij het openen van de geëxtraheerde tekst uit het`TextAbsorber` voorwerp.

#### Vraag: Hoe sla ik de geëxtraheerde tekst op in een bestand?

 A: In stap 7 maakt u een`TextWriter`, open het bestand waarin u de geëxtraheerde tekst wilt opslaan, schrijf de geëxtraheerde tekst naar het bestand en sluit vervolgens de stream.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, hebt u geleerd hoe u alle tekst uit een PDF-document kunt extraheren met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in een gespecificeerd uitvoerbestand, zodat u de tekstuele inhoud van het document kunt analyseren en manipuleren.