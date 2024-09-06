---
title: Tekst extraheren met behulp van een tekstapparaat
linktitle: Tekst extraheren met behulp van een tekstapparaat
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst uit een PDF-document kunt extraheren met behulp van het tekstapparaat in Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-text/extract-text-using-text-device/
---
Deze tutorial begeleidt u door het proces van het extraheren van tekst uit een PDF-document met behulp van het Text Device in Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Open het PDF-document
 Open een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand doorgeven.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Stap 5: Tekst extraheren met behulp van het tekstapparaat
 Maak een`StringBuilder` object om de geëxtraheerde tekst vast te houden. Loop door elke pagina van het document en gebruik een`TextDevice` om de tekst van elke pagina te extraheren.

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
 Geef het pad van het uitvoerbestand op en sla de geëxtraheerde tekst op in een tekstbestand met behulp van de`File.WriteAllText` methode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Voorbeeldbroncode voor Extract Text Using Text Device met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//String om geëxtraheerde tekst vast te houden
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Tekstapparaat maken
		TextDevice textDevice = new TextDevice();
		// Opties voor tekstextractie instellen - tekstextractiemodus instellen (Raw of Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Converteer een bepaalde pagina en sla tekst op in de stream
		textDevice.Process(pdfPage, textStream);
		// Converteer een bepaalde pagina en sla tekst op in de stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Sluit geheugenstroom
		textStream.Close();
		// Tekst uit geheugenstroom halen
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
U hebt succesvol tekst uit een PDF-document geëxtraheerd met behulp van het Text Device in Aspose.PDF voor .NET. De geëxtraheerde tekst is opgeslagen in het opgegeven uitvoerbestand.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial biedt begeleiding bij het extraheren van tekst uit een PDF-document met behulp van de Text Device-functie in Aspose.PDF voor .NET. De bijbehorende C#-broncode demonstreert de benodigde stappen om deze taak uit te voeren.

#### V: Welke naamruimten moet ik importeren?

A: In het codebestand waaruit u tekst wilt extraheren, voegt u de volgende richtlijnen toe aan het begin van het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel die zegt`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe open ik een bestaand PDF-document?

 A: In stap 4 opent u een bestaand PDF-document met behulp van de`Document` constructor en het pad naar het PDF-invoerbestand opgeven.

#### V: Hoe kan ik tekst extraheren met het tekstapparaat?

 A: Stap 5 omvat het maken van een`StringBuilder` object om de geëxtraheerde tekst vast te houden. Vervolgens itereert u door elke pagina van het document en gebruikt u een`TextDevice` samen met`TextExtractionOptions` om tekst uit elke pagina te halen.

#### V: Hoe kan ik de geëxtraheerde tekst opslaan in een bestand?

 A: In stap 6 geeft u het pad naar het uitvoerbestand op en gebruikt u de`File.WriteAllText`Methode om de geëxtraheerde tekst op te slaan in een tekstbestand.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u de Text Device-functie in Aspose.PDF voor .NET kunt gebruiken om tekst uit een PDF-document te extraheren. De geëxtraheerde tekst is opgeslagen in een opgegeven uitvoerbestand, zodat u de geëxtraheerde inhoud naar behoefte kunt bewerken en gebruiken.