---
title: Extraheer tekst met behulp van een tekstapparaat
linktitle: Extraheer tekst met behulp van een tekstapparaat
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uit een PDF-document kunt extraheren met behulp van het tekstapparaat in Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-text/extract-text-using-text-device/
---
Deze tutorial leidt u door het proces van het extraheren van tekst uit een PDF-document met behulp van het Text Device in Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de noodzakelijke stappen.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Stap 3: Stel de documentmap in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document`constructor en geef het pad door aan het invoer-PDF-bestand.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Stap 5: Extraheer tekst met behulp van Text Device
 Maak een`StringBuilder` object om de geëxtraheerde tekst vast te houden. Blader door elke pagina van het document en gebruik een`TextDevice` om de tekst van elke pagina te extraheren.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Stap 6: Sla de geëxtraheerde tekst op
 Geef het pad voor het uitvoerbestand op en sla de geëxtraheerde tekst op in een tekstbestand met behulp van de`File.WriteAllText` methode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Voorbeeldbroncode voor het extraheren van tekst met behulp van een tekstapparaat met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Tekenreeks om geëxtraheerde tekst vast te houden
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Maak een tekstapparaat
		TextDevice textDevice = new TextDevice();
		// Opties voor tekstextractie instellen - tekstextractiemodus instellen (Raw of Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converteer een bepaalde pagina en sla tekst op in de stream
		textDevice.Process(pdfPage, textStream);
		// Converteer een bepaalde pagina en sla tekst op in de stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Sluit de geheugenstroom
		textStream.Close();
		// Haal tekst op uit de geheugenstroom
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Sla de geëxtraheerde tekst op in een tekstbestand
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Conclusie
U hebt met succes tekst uit een PDF-document geëxtraheerd met behulp van het tekstapparaat in Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial biedt richtlijnen voor het extraheren van tekst uit een PDF-document met behulp van de functie Tekstapparaat in Aspose.PDF voor .NET. De begeleidende C#-broncode demonstreert de noodzakelijke stappen om deze taak te volbrengen.

#### Vraag: Welke naamruimten moet ik importeren?

A: In het codebestand waarin u tekst wilt extraheren, neemt u de volgende gebruiksinstructies op aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Vraag: Hoe geef ik de documentmap op?

 A: Zoek in de code de regel die zegt`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

#### Vraag: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het invoer-PDF-bestand opgeven.

#### Vraag: Hoe extraheer ik tekst met het tekstapparaat?

 A: Stap 5 omvat het maken van een`StringBuilder` object om de geëxtraheerde tekst vast te houden. Vervolgens doorloopt u elke pagina van het document en gebruikt u a`TextDevice` samen met`TextExtractionOptions` om tekst uit elke pagina te extraheren.

#### Vraag: Hoe sla ik de geëxtraheerde tekst op in een bestand?

 A: In stap 6 specificeert u het pad van het uitvoerbestand en gebruikt u de`File.WriteAllText`methode om de geëxtraheerde tekst in een tekstbestand op te slaan.

#### Vraag: Wat is de belangrijkste conclusie uit deze tutorial?

A: Door deze tutorial te volgen, heeft u geleerd hoe u de functie Tekstapparaat in Aspose.PDF voor .NET kunt gebruiken om tekst uit een PDF-document te extraheren. De geëxtraheerde tekst is opgeslagen in een gespecificeerd uitvoerbestand, zodat u de geëxtraheerde inhoud naar behoefte kunt manipuleren en gebruiken.