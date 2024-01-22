---
title: Ontvang alle bijlagen in PDF-bestand
linktitle: Ontvang alle bijlagen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u alle bijlagen in PDF-bestanden kunt krijgen met Aspose.PDF voor .NET. Stap-voor-stap handleiding voor eenvoudig gebruik.
type: docs
weight: 40
url: /nl/net/programming-with-attachments/get-all-the-attachments/
---
In deze zelfstudie leiden we u stap voor stap door de volgende C#-broncode om alle bijlagen in een PDF-bestand te krijgen met Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Daarnaast heb je basiskennis van programmeren in C#.

### Stap 1: Documentmap instellen

In de meegeleverde broncode moet u de map opgeven waar het PDF-bestand zich bevindt waarvan u de bijlagen wilt ophalen. Wijzig de variabele "dataDir" in de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Stap 2: Open het bestaande PDF-document

We openen het bestaande PDF-document via het opgegeven pad.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Stap 3: De bijlagenverzameling verkrijgen

We halen de verzameling bijlagen uit het document.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Stap 4: Bijlagen ophalen

We doorlopen de collectie om alle bijlagen op te halen en hun informatie weer te geven. Bijlagen bewaren wij ook in individuele bestanden.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Controleer of objectparameters aanvullende informatie bevatten
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Haal de bijlage op en sla deze op in een bestand
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Voorbeeldbroncode voor het ophalen van alle bijlagen met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Ontvang een verzameling ingebedde bestanden
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Get telling van de ingebedde bestanden
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Loop door de collectie om alle bijlagen te krijgen
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//Controleer of het parameterobject de parameters bevat
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// Haal de bijlage op en schrijf naar bestand of stream
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusie

In deze tutorial hebben we uitgelegd hoe je alle bijlagen uit een PDF-bestand kunt halen met Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om bijlagen uit uw PDF-bestanden te extraheren en te manipuleren.

## Veelgestelde vragen over het verkrijgen van alle bijlagen in een PDF-bestand

#### Vraag: Waarom zou ik alle bijlagen uit een PDF-document moeten ophalen?

A: Door bijlagen op te halen, kunt u extra bestanden die in een PDF zijn ingesloten, openen en manipuleren, wat handig kan zijn voor archivering, delen of verdere verwerking.

#### Vraag: Welke soorten bestanden kunnen aan een PDF-document worden toegevoegd?

A: PDF-documenten kunnen een breed scala aan bijgevoegde bestanden bevatten, waaronder afbeeldingen, documenten, spreadsheets, audiobestanden en meer.

#### Vraag: Hoe helpt deze tutorial mij bij het ophalen van bijlagen uit een PDF met Aspose.PDF voor .NET?

A: Deze tutorial biedt stapsgewijze instructies en C#-broncode voor het openen en ophalen van alle bijlagen in een PDF-document.

#### Vraag: Kan ik met deze tutorial specifieke bijlagen ophalen in plaats van alle bijlagen?

A: Ja, u kunt de verstrekte code wijzigen om bijlagen selectief op te halen op basis van uw vereisten.

#### Vraag: Welke informatie over elke bijlage kan ik verkrijgen met behulp van deze tutorial?

A: Deze tutorial laat zien hoe u details kunt ophalen en weergeven, zoals de naam van de bijlage, de beschrijving, het MIME-type, de aanmaakdatum, de wijzigingsdatum en de grootte.

#### Vraag: Hoe worden de opgehaalde bijlagen opgeslagen met behulp van deze tutorial?

A: De tutorial begeleidt u bij het opslaan van elke opgehaalde bijlage als een afzonderlijk bestand in de opgegeven map.

#### Vraag: Kan ik deze kennis gebruiken om bijlagen uit met een wachtwoord beveiligde PDF-bestanden te extraheren?

A: Ja, u kunt vergelijkbare principes toepassen om bijlagen op te halen uit met een wachtwoord beveiligde PDF-bestanden met behulp van Aspose.PDF voor .NET.

#### Vraag: Hoe vergemakkelijkt Aspose.PDF voor .NET het ophalen van bijlagen?

A: Aspose.PDF voor .NET biedt een intuïtieve API waarmee u bijlagen in PDF-documenten eenvoudig kunt openen en manipuleren.

#### Vraag: Zijn er specifieke scenario's waarin het ophalen van bijlagen wordt aanbevolen?

A: Het ophalen van bijlagen is handig als u toegang wilt krijgen tot bestanden die zijn ingesloten in een PDF, zoals het extraheren van afbeeldingen, audiobestanden of aanvullende documenten.