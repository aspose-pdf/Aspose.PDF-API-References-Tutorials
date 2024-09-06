---
title: Lettertypen verwijderen en PDF-bestanden optimaliseren
linktitle: Lettertypen verwijderen en PDF-bestanden optimaliseren
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET gebruikt om Unembed Fonts te krijgen en PDF-bestanden te optimaliseren. Een stapsgewijze handleiding.
type: docs
weight: 370
url: /nl/net/programming-with-document/unembedfonts/
---
Aspose.PDF voor .NET is een krachtige bibliotheek die een breed scala aan functies biedt om met PDF-documenten te werken. Een van de functies is om niet-ingebedde lettertypen uit een PDF-document te halen. Dit kan handig zijn als u lettertypen uit een PDF-document wilt extraheren en ze in andere toepassingen wilt gebruiken.

We bieden een stapsgewijze handleiding om de volgende C#-broncode van de functie 'get unembed fonts' van Aspose.PDF voor .NET uit te leggen.

## Stap 1: Stel het pad naar de documentmap in

Voordat we beginnen, moeten we het pad instellen naar de directory waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Vervang "UW DOCUMENTENMAP" door het daadwerkelijke pad naar de map waarin uw PDF-document zich bevindt.

## Stap 2: Open het PDF-document

 De eerste stap is het laden van het PDF-document dat u hiervoor wilt gebruiken, gebruik hiervoor de`Document` klasse van Aspose.PDF voor .NET. Het volgende codefragment laat zien hoe u het PDF-document laadt:

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Stap 3: Stel de optie UnembedFonts in

 Om niet-ingesloten lettertypen uit het PDF-document te halen, moet u de`UnembedFonts` optie om`true` Deze optie is beschikbaar in de`OptimizationOptions` klasse. Het volgende codefragment laat zien hoe u de`UnembedFonts` optie:

```csharp
// Optie UnembedFonts instellen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Stap 4: Optimaliseer het PDF-document

 Nadat u de`UnembedFonts` optie, kunt u het PDF-document optimaliseren met behulp van de`OptimizeResources` methode van de`Document` klasse. Het volgende codefragment laat zien hoe u het PDF-document kunt optimaliseren:

```csharp
// Optimaliseer PDF-document met OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Stap 5: Sla het bijgewerkte document op

 Zodra het PDF-document is geoptimaliseerd, kunt u het bijgewerkte document opslaan met behulp van de`Save` methode van de`Document`klasse. Het volgende codefragment laat zien hoe u het bijgewerkte document kunt opslaan:

```csharp
// Bijgewerkt document opslaan
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Stap 6: Haal het originele en verkleinde bestandsformaat op

 Ten slotte kunt u het originele en verkleinde bestandsformaat van het PDF-document verkrijgen met behulp van de`FileInfo` klasse van System.IO. Het volgende codefragment laat zien hoe u de originele en gereduceerde bestandsgrootte kunt krijgen:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Voorbeeldbroncode voor het ophalen van niet-ingebedde lettertypen met behulp van Aspose.PDF voor .NET

Hier is de volledige voorbeeldbroncode voor het ophalen van niet-ingesloten lettertypen uit een PDF-document met behulp van Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Optie UnembedFonts instellen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimaliseer PDF-document met OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Bijgewerkt document opslaan
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusie

In deze tutorial hebben we laten zien hoe u Aspose.PDF voor .NET kunt gebruiken om unembed-lettertypen uit een PDF-document te halen. Door de stapsgewijze handleiding te volgen, kunt u deze functie eenvoudig implementeren in uw C#-toepassingen. Unembedding-lettertypen kan voordelig zijn wanneer u afzonderlijk met de geëxtraheerde lettertypen moet werken of consistent lettertypegebruik op verschillende platforms moet garanderen.

## Veelgestelde vragen

#### V: Wat is het doel van het verwijderen van lettertypen uit een PDF-document?

A: Door lettertypen uit een PDF-document te verwijderen, kunt u de ingesloten lettertypen extraheren en ze in andere toepassingen gebruiken. Dit kan handig zijn om consistente lettertypeweergave te garanderen en het visuele uiterlijk van het document te behouden.

#### V: Hoe geef ik het pad naar de documentdirectory op in de C#-code?

 A: Om het pad naar de documentmap op te geven, vervangt u`"YOUR DOCUMENT DIRECTORY"` in de code het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

####  V: Wat betekent de`UnembedFonts` option do, and where is it set?

 A: De`UnembedFonts` optie, beschikbaar in de`OptimizationOptions` klasse, schakelt het verwijderen van lettertypen uit het PDF-document in of uit. Om deze optie in te stellen op`true`, gebruik de volgende code:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### V: Kan ik de wijzigingen die tijdens het optimalisatieproces zijn aangebracht, ongedaan maken?

A: Aspose.PDF voor .NET brengt geen permanente wijzigingen aan in het originele PDF-document tijdens de optimalisatie. Het optimalisatieproces wordt uitgevoerd op een kopie van het document, waarbij het origineel intact blijft.

#### V: Hoe kan ik de originele en verkleinde bestandsgrootte controleren na optimalisatie?

 A: U kunt de`FileInfo` klasse van`System.IO` om de originele en gereduceerde bestandsgrootte te krijgen. Hier is een voorbeeldcodefragment om dit te bereiken:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```