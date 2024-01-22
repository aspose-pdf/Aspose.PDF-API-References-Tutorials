---
title: Stel het standaardlettertype in in een PDF-bestand
linktitle: Stel het standaardlettertype in in een PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer met deze stapsgewijze handleiding hoe u het standaardlettertype in een PDF-bestand instelt met Aspose.PDF voor .NET.
type: docs
weight: 280
url: /nl/net/programming-with-document/setdefaultfont/
---
Als u in .NET met PDF-documenten werkt, kunt u problemen tegenkomen waarbij het lettertype dat in de PDF wordt gebruikt, niet beschikbaar is op het systeem waarop de PDF wordt bekeken of afgedrukt. Dit kan ertoe leiden dat de tekst onjuist of helemaal niet verschijnt. Aspose.PDF voor .NET biedt een oplossing voor dit probleem doordat u een standaardlettertype voor het document kunt instellen. In dit voorbeeld ziet u hoe u het standaardlettertype instelt met Aspose.PDF voor .NET.

## Stap 1: Stel het pad naar de documentmap in

we moeten het pad instellen naar de map waar ons PDF-document zich bevindt. We slaan dit pad op in een variabele genaamd "dataDir".

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het PDF-document

 We beginnen met het laden van een bestaand PDF-document waarin lettertypen ontbreken. In dit voorbeeld gaan we ervan uit dat het PDF-document zich in de map bevindt die is opgegeven door de`dataDir` variabel.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // code komt hier
}
```

## Stap 3: Stel het standaardlettertype in

 Vervolgens stellen we het standaardlettertype voor het PDF-document in met behulp van de`PdfSaveOptions` klas. In dit voorbeeld stellen we het standaardlettertype in op ‘Arial’.

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Stap 4: Sla het bijgewerkte document op

Ten slotte slaan we het bijgewerkte document op in een nieuw bestand. In dit voorbeeld slaan we het bijgewerkte document op in een bestand met de naam "output_out.pdf" in dezelfde map als het invoerbestand.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Voorbeeldbroncode voor het instellen van het standaardlettertype met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laad een bestaand PDF-document met ontbrekend lettertype
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Geef de standaardlettertypenaam op
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Conclusie

Het instellen van een standaardlettertype in PDF-documenten met Aspose.PDF voor .NET is een eenvoudige en effectieve manier om ervoor te zorgen dat de tekst correct wordt weergegeven, zelfs als de originele lettertypen niet beschikbaar zijn. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-broncode te gebruiken, kunnen ontwikkelaars eenvoudig het standaardlettertype instellen en PDF's maken die een consistente en betrouwbare kijkervaring bieden in verschillende omgevingen. Deze functie is met name handig in scenario's waarin de PDF's worden bekeken of afgedrukt op verschillende systemen waarop mogelijk verschillende lettertypesets zijn geïnstalleerd.

### Veelgestelde vragen over het instellen van het standaardlettertype in een PDF-bestand

#### Vraag: Waarom is het instellen van een standaardlettertype belangrijk in PDF-documenten?

A: Het instellen van een standaardlettertype in PDF-documenten is belangrijk omdat dit ervoor zorgt dat de tekst correct wordt weergegeven, zelfs als de originele lettertypen niet beschikbaar zijn op het systeem waarop de PDF wordt bekeken of afgedrukt. Het helpt problemen zoals ontbrekende of onleesbare tekst te voorkomen, waardoor een consistente en betrouwbare kijkervaring wordt gegarandeerd.

#### Vraag: Kan ik elk lettertype als standaardlettertype kiezen met Aspose.PDF voor .NET?

 A: Ja, u kunt elk lettertype dat beschikbaar is op het systeem als standaardlettertype kiezen met Aspose.PDF voor .NET. Geef eenvoudigweg de naam van het lettertype op in het`DefaultFontName` eigendom van de`PdfSaveOptions` klas.

#### Vraag: Wat gebeurt er als het opgegeven standaardlettertype niet beschikbaar is op het systeem?

A: Als het opgegeven standaardlettertype niet beschikbaar is op het systeem, gebruikt de PDF-viewer een reservelettertype om de tekst weer te geven. Het is raadzaam om een algemeen verkrijgbaar lettertype zoals Arial of Times New Roman te kiezen om compatibiliteit tussen verschillende systemen te garanderen.