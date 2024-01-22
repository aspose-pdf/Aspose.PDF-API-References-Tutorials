---
title: Verwijder lettertypen en optimaliseer PDF-bestanden
linktitle: Verwijder lettertypen en optimaliseer PDF-bestanden
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Aspose.PDF voor .NET kunt gebruiken om niet-ingesloten lettertypen te verkrijgen en PDF-bestanden te optimaliseren. Een stapsgewijze handleiding.
type: docs
weight: 370
url: /nl/net/programming-with-document/unembedfonts/
---
Aspose.PDF voor .NET is een krachtige bibliotheek die een breed scala aan functies biedt om met PDF-documenten te werken. Een van de functies ervan is om niet-ingesloten lettertypen uit een PDF-document te halen. Dit kan handig zijn als u lettertypen uit een PDF-document wilt extraheren en deze in andere toepassingen wilt gebruiken.

we zullen een stap-voor-stap handleiding geven om de volgende C#-broncode uit te leggen van de functie Unembed Fonts van Aspose.PDF voor .NET.

## Stap 1: Stel het pad naar de documentmap in

Voordat we beginnen, moeten we het pad instellen naar de map waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Vervang "UW DOCUMENTENMAP" door het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

## Stap 2: Open het PDF-document

 De eerste stap is het laden van het PDF-document dat u hiervoor wilt gebruiken, gebruik de`Document` klasse van Aspose.PDF voor .NET. Het volgende codefragment laat zien hoe u het PDF-document laadt:

```csharp
// Document openen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Stap 3: Stel de optie UnembedFonts in

 Om de ingesloten lettertypen uit het PDF-document te verwijderen, moet u de`UnembedFonts` optie om`true` . Deze optie is beschikbaar in de`OptimizationOptions` klas. Het volgende codefragment laat zien hoe u de`UnembedFonts` keuze:

```csharp
// Stel de UnembedFonts-optie in
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Stap 4: Optimaliseer het PDF-document

 Na het instellen van de`UnembedFonts` optie kunt u het PDF-document optimaliseren met behulp van de`OptimizeResources` werkwijze van de`Document` klas. Het volgende codefragment laat zien hoe u het PDF-document kunt optimaliseren:

```csharp
// Optimaliseer een PDF-document met OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Stap 5: Sla het bijgewerkte document op

 Zodra het PDF-document is geoptimaliseerd, kunt u het bijgewerkte document opslaan met behulp van de`Save` werkwijze van de`Document`klas. Het volgende codefragment laat zien hoe u het bijgewerkte document kunt opslaan:

```csharp
// Bewaar het bijgewerkte document
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Stap 6: Verkrijg de originele en verkleinde bestandsgrootte

 Ten slotte kunt u de originele en verkleinde bestandsgrootte van het PDF-document verkrijgen met behulp van de`FileInfo` klasse van System.IO. Het volgende codefragment laat zien hoe u de originele en verkleinde bestandsgrootte kunt verkrijgen:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Voorbeeldbroncode voor het ophalen van niet-ingesloten lettertypen met Aspose.PDF voor .NET

Hier is de volledige voorbeeldbroncode voor het ophalen van niet-ingesloten lettertypen uit een PDF-document met Aspose.PDF voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Stel de UnembedFonts-optie in
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimaliseer een PDF-document met OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
// Bewaar het bijgewerkte document
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Conclusie

In deze zelfstudie hebben we gedemonstreerd hoe u Aspose.PDF voor .NET kunt gebruiken om niet-ingesloten lettertypen uit een PDF-document te halen. Door de stapsgewijze handleiding te volgen, kunt u deze functie eenvoudig in uw C#-applicaties implementeren. Het verwijderen van lettertypen kan voordelig zijn als u afzonderlijk met de geëxtraheerde lettertypen moet werken of als u consistent lettertypegebruik op verschillende platforms wilt garanderen.

## Veelgestelde vragen

#### Vraag: Wat is het doel van het verwijderen van lettertypen uit een PDF-document?

A: Door lettertypen uit een PDF-document te verwijderen, kunt u de ingesloten lettertypen extraheren en in andere toepassingen gebruiken. Dit kan handig zijn om consistente weergave van lettertypen te garanderen en de visuele uitstraling van het document te behouden.

#### Vraag: Hoe geef ik het pad naar de documentmap op in de C#-code?

 A: Om het pad naar de documentmap op te geven, vervangt u`"YOUR DOCUMENT DIRECTORY"` in de code met het daadwerkelijke pad naar de map waar uw PDF-document zich bevindt.

####  Vraag: Wat doet de`UnembedFonts` option do, and where is it set?

 EEN: De`UnembedFonts` optie, verkrijgbaar in de`OptimizationOptions` class, schakelt het insluiten van lettertypen uit het PDF-document in of uit. Om deze optie in te stellen`true`, gebruik de volgende code:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Vraag: Kan ik de wijzigingen die tijdens het optimalisatieproces zijn aangebracht, ongedaan maken?

A: Aspose.PDF voor .NET brengt tijdens de optimalisatie geen permanente wijzigingen aan in het originele PDF-document. Het optimalisatieproces wordt uitgevoerd op een kopie van het document, waarbij het origineel intact blijft.

#### Vraag: Hoe kan ik de originele en verkleinde bestandsgrootte na optimalisatie controleren?

Antwoord: U kunt de`FileInfo` klas van`System.IO` om de originele en verkleinde bestandsgrootte te krijgen. Hier is een voorbeeldcodefragment om dit te bereiken:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```