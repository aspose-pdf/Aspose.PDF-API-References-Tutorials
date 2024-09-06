---
title: Kolommentekst uit PDF-bestand extraheren
linktitle: Kolommentekst uit PDF-bestand extraheren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uit kolommen uit een PDF-bestand kunt extraheren met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-text/extract-columns-text/
---
Deze tutorial begeleidt u door het proces van het extraheren van kolomtekst in een PDF-bestand met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waaruit u de tekst uit de kolommen wilt extraheren, het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand doorgeven.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Stap 5: Pas de lettergrootte aan
Verklein de lettergrootte van de tekstfragmenten met een factor 0,7 om de leesbaarheid te verbeteren en kolomtekst beter weer te geven.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Stap 6: Tekst uit kolommen extraheren
 Sla het gewijzigde PDF-document op in een geheugenstroom en laad het opnieuw als een nieuw document. Gebruik vervolgens de`TextAbsorber` klasse om tekst uit de kolommen te extraheren.

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
Sla de geëxtraheerde tekst op in een tekstbestand op het opgegeven pad naar het uitvoerbestand.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor Extract Columns Text met behulp van Aspose.PDF voor .NET 
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
	// Het is nodig om de lettergrootte met ten minste 70% te verkleinen
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
U hebt succesvol kolomtekst uit een PDF-document geëxtraheerd met Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial biedt een stapsgewijze handleiding voor het extraheren van tekstkolommen uit een PDF-bestand met Aspose.PDF voor .NET. De bijbehorende C#-broncode biedt een praktische demonstratie van de vereiste procedures.

#### V: Welke naamruimten moet ik importeren?

A: In het codebestand waaruit u tekstkolommen wilt extraheren, voegt u de volgende richtlijnen toe aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek de lijn`string dataDir = "YOUR DOCUMENT DIRECTORY";` in de code en vervang`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand opgeven.

#### V: Waarom wordt de lettergrootte aangepast?

A: Stap 5 houdt in dat u de lettergrootte van tekstfragmenten met een factor 0,7 verkleint. Deze aanpassing verbetert de leesbaarheid en geeft kolomtekst nauwkeuriger weer.

#### V: Hoe haal ik tekst uit kolommen?

 A: Stap 6 bestaat uit het opslaan van het gewijzigde PDF-document in een geheugenstroom, het opnieuw laden als een nieuw document en vervolgens het gebruik van de`TextAbsorber` klasse om tekst uit de kolommen te extraheren.

#### V: Wat is het doel van het opslaan van de geëxtraheerde tekst?

A: In stap 7 slaat u de geëxtraheerde tekst op in een tekstbestand op het opgegeven uitvoerbestandspad.

#### V: Waarom wordt het lettertype verkleind voordat het wordt geëxtraheerd?

A: Door de lettergrootte te verkleinen, zorgt u ervoor dat de geëxtraheerde tekst correct wordt uitgelijnd binnen de kolommen. Dit zorgt voor een nauwkeurigere weergave van de oorspronkelijke lay-out.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u de kennis en vaardigheden verworven die nodig zijn om tekstkolommen uit een PDF-document te extraheren met Aspose.PDF voor .NET. De resulterende tekst is opgeslagen in het opgegeven uitvoerbestand.