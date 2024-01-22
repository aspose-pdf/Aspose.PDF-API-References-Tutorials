---
title: Kolommentekst extraheren in PDF-bestand
linktitle: Kolommentekst extraheren in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u kolomtekst uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-text/extract-columns-text/
---
Deze tutorial leidt u door het proces van het extraheren van kolomtekst in een PDF-bestand met Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. Je kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Zet het project op
1. Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waarin u de kolommentekst wilt extraheren het volgende toe met behulp van richtlijnen bovenaan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document`constructor en geef het pad door aan het invoer-PDF-bestand.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Stap 5: Pas de lettergrootte aan
Verklein de lettergrootte van de tekstfragmenten met een factor 0,7 om de leesbaarheid te verbeteren en de kolomtekst beter weer te geven.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Stap 6: Extraheer tekst uit kolommen
 Sla het gewijzigde PDF-document op in een geheugenstroom en laad het opnieuw als een nieuw document. Gebruik dan de`TextAbsorber` klasse om tekst uit de kolommen te extraheren.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Stap 7: Sla de geëxtraheerde tekst op
Sla de geëxtraheerde tekst op in een tekstbestand op het opgegeven uitvoerbestandspad.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het extraheren van kolommentekst met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Moet de lettergrootte minstens voor 70% verkleinen
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Conclusie
U hebt met succes kolomtekst uit een PDF-document geëxtraheerd met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial biedt een stapsgewijze handleiding voor het extraheren van tekstkolommen uit een PDF-bestand met Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt een praktische demonstratie van de vereiste procedures.

#### Vraag: Welke naamruimten moet ik importeren?

A: In het codebestand waarin u tekstkolommen wilt extraheren, neemt u de volgende instructies op aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het invoer-PDF-bestand opgeven.

#### Vraag: Waarom wordt de lettergrootte aangepast?

A: Stap 5 bestaat uit het verkleinen van de lettergrootte van tekstfragmenten met een factor 0,7. Deze aanpassing verbetert de leesbaarheid en geeft kolomvormige tekst nauwkeuriger weer.

#### Vraag: Hoe extraheer ik tekst uit kolommen?

 A: Stap 6 bestaat uit het opslaan van het gewijzigde PDF-document in een geheugenstroom, het opnieuw laden ervan als een nieuw document en het vervolgens gebruiken van de`TextAbsorber` klasse om tekst uit de kolommen te extraheren.

#### Vraag: Wat is het doel van het opslaan van de geëxtraheerde tekst?

A: In stap 7 slaat u de geëxtraheerde tekst op in een tekstbestand op het opgegeven uitvoerbestandspad.

#### Vraag: Waarom de lettergrootte verkleinen vóór het uitpakken?

A: Het verkleinen van de lettergrootte zorgt ervoor dat de geëxtraheerde tekst goed wordt uitgelijnd binnen de kolommen, waardoor een nauwkeurigere weergave van de oorspronkelijke lay-out ontstaat.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u de kennis en vaardigheden verworven die nodig zijn om tekstkolommen uit een PDF-document te extraheren met behulp van Aspose.PDF voor .NET. De resulterende tekst is opgeslagen in het opgegeven uitvoerbestand.