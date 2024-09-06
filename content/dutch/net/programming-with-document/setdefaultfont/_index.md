---
title: Standaardlettertype instellen in PDF-bestand
linktitle: Standaardlettertype instellen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u het standaardlettertype in een PDF-bestand instelt met Aspose.PDF voor .NET met deze stapsgewijze handleiding.
type: docs
weight: 280
url: /nl/net/programming-with-document/setdefaultfont/
---
Als u met PDF-documenten in .NET werkt, kunt u problemen tegenkomen waarbij het lettertype dat in de PDF wordt gebruikt, niet beschikbaar is op het systeem waarop het wordt bekeken of afgedrukt. Dit kan ertoe leiden dat de tekst onjuist of helemaal niet wordt weergegeven. Aspose.PDF voor .NET biedt een oplossing voor dit probleem door u toe te staan een standaardlettertype voor het document in te stellen. In dit voorbeeld wordt uitgelegd hoe u het standaardlettertype instelt met Aspose.PDF voor .NET.

## Stap 1: Stel het pad naar de documentmap in

we moeten het pad instellen naar de directory waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het PDF-document

 We beginnen met het laden van een bestaand PDF-document met ontbrekende lettertypen. In dit voorbeeld gaan we ervan uit dat het PDF-document zich in de directory bevindt die is opgegeven door de`dataDir` variabel.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // code komt hier
}
```

## Stap 3: Stel het standaardlettertype in

 Vervolgens stellen we het standaardlettertype voor het PDF-document in met behulp van`PdfSaveOptions`klasse. In dit voorbeeld stellen we het standaardlettertype in op "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Stap 4: Sla het bijgewerkte document op

Ten slotte slaan we het bijgewerkte document op in een nieuw bestand. In dit voorbeeld slaan we het bijgewerkte document op in een bestand met de naam "output_out.pdf" in dezelfde directory als het invoerbestand.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Voorbeeldbroncode voor het instellen van het standaardlettertype met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Een bestaand PDF-document laden met ontbrekend lettertype
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Standaardlettertypenaam opgeven
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusie

Het instellen van een standaardlettertype in PDF-documenten met Aspose.PDF voor .NET is een eenvoudige en effectieve manier om ervoor te zorgen dat de tekst correct wordt weergegeven, zelfs als de originele lettertypen niet beschikbaar zijn. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig het standaardlettertype instellen en PDF's maken die een consistente en betrouwbare kijkervaring bieden in verschillende omgevingen. Deze functie is met name handig in scenario's waarin de PDF's worden bekeken of afgedrukt op verschillende systemen waarop mogelijk verschillende lettertypesets zijn geïnstalleerd.

### FAQ's voor het instellen van een standaardlettertype in een PDF-bestand

#### V: Waarom is het instellen van een standaardlettertype belangrijk in PDF-documenten?

A: Het instellen van een standaardlettertype in PDF-documenten is belangrijk omdat het ervoor zorgt dat de tekst correct wordt weergegeven, zelfs als de originele lettertypen niet beschikbaar zijn op het systeem waarop de PDF wordt bekeken of afgedrukt. Het helpt problemen zoals ontbrekende of onduidelijke tekst te voorkomen en zorgt voor een consistente en betrouwbare kijkervaring.

#### V: Kan ik elk lettertype als standaardlettertype kiezen met Aspose.PDF voor .NET?

 A: Ja, u kunt elk lettertype dat beschikbaar is op het systeem kiezen als standaardlettertype met Aspose.PDF voor .NET. Geef gewoon de naam van het lettertype op in de`DefaultFontName` eigendom van de`PdfSaveOptions` klas.

#### V: Wat gebeurt er als het opgegeven standaardlettertype niet beschikbaar is op het systeem?

A: Als het opgegeven standaardlettertype niet beschikbaar is op het systeem, gebruikt de PDF-viewer een fallback-lettertype om de tekst weer te geven. Het is raadzaam om een algemeen beschikbaar lettertype te kiezen, zoals Arial of Times New Roman, om compatibiliteit op verschillende systemen te garanderen.