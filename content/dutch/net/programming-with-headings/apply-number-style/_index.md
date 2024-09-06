---
title: Nummerstijl toepassen in PDF-bestand
linktitle: Nummerstijl toepassen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een nummeringsstijl toepast op koppen in een PDF-bestand met Aspose.PDF voor .NET. Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-headings/apply-number-style/
---
In deze tutorial leiden we u stap voor stap door de volgende C#-broncode om een nummeringsstijl toe te passen in een PDF-bestand met behulp van Aspose.PDF voor .NET.

Zorg ervoor dat u de Aspose.PDF-bibliotheek hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint. Heb ook basiskennis van C#-programmering.

### Stap 1: Documentdirectory instellen

In de meegeleverde broncode moet u de directory opgeven waar u het gegenereerde PDF-bestand wilt opslaan. Wijzig de variabele "dataDir" naar de gewenste directory.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Stap 2: Het PDF-document maken

We maken een nieuw PDF-document met de opgegeven afmetingen en marges.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Stap 3: Een pagina en een zwevende container maken

We voegen een pagina toe aan het document en maken een zwevende container om de inhoud te organiseren.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Stap 4: Voeg koppen toe met nummering

We maken headers met specifieke nummering en voegen deze toe aan de zwevende container.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Stap 5: Het PDF-document opslaan

We slaan het gegenereerde PDF-document op in de opgegeven directory.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Voorbeeldbroncode voor Toepassen van nummerstijl met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusie

In deze tutorial hebben we uitgelegd hoe u een nummeringsstijl toepast op koppen in een PDF-document met behulp van Aspose.PDF voor .NET. U kunt deze kennis nu gebruiken om PDF-documenten te maken met aangepaste nummeringen voor koppen.

### FAQ's voor het toepassen van nummerstijl in PDF-bestand

#### V: Wat is de nummeringsstijl in een PDF-document?

A: Nummeringsstijl verwijst naar het formaat waarin koppen of secties in een PDF-document worden genummerd. Het kan cijfers, letters of andere tekens bevatten om een hiërarchische structuur te bieden.

#### V: Waarom moet ik een nummeringsstijl toepassen op koppen in een PDF-document?

A: Het toepassen van nummeringstijl op koppen verbetert de leesbaarheid en organisatie van uw PDF-document. Het helpt lezers om eenvoudig te navigeren en de hiërarchische structuur van de inhoud te begrijpen.

#### V: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een bibliotheek waarmee ontwikkelaars programmatisch met PDF-bestanden kunnen werken in .NET-applicaties. Het biedt een breed scala aan functies voor het maken, bewerken, converteren en manipuleren van PDF-documenten.

#### V: Hoe importeer ik de vereiste bibliotheken voor mijn C#-project?

A: Om de benodigde bibliotheken voor uw C#-project te importeren, neemt u de volgende importrichtlijnen op:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Met deze richtlijnen krijgt u toegang tot de klassen en methoden die nodig zijn voor het werken met PDF-documenten en het toepassen van nummeringsstijlen.

#### V: Hoe geef ik de map op waarin het gegenereerde PDF-bestand moet worden opgeslagen?

A: Wijzig in de meegeleverde broncode de variabele "dataDir" om de map op te geven waar u het gegenereerde PDF-bestand wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het werkelijke directorypad.

#### V: Hoe maak ik een PDF-document met de opgegeven afmetingen en marges?

A: Om een PDF-document met de opgegeven afmetingen en marges te maken, gebruikt u de volgende code:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### V: Hoe voeg ik koppen met nummeringsstijl toe aan het PDF-document?

A: Om koppen met nummeringsstijl toe te voegen aan het PDF-document, gebruikt u de meegeleverde codevoorbeelden om koppen te maken en hun nummeringsstijlen aan te passen. Pas eigenschappen zoals tekst, nummeringsstijl, startnummer en automatische volgorde indien nodig aan.

#### V: Hoe kan ik het gegenereerde PDF-document opslaan?

 A: Om het gegenereerde PDF-document op te slaan, gebruikt u de`Save` methode van de`pdfDoc` voorwerp:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### V: Hoe kan ik bevestigen dat de nummeringsstijl is toegepast?

A: Open het gegenereerde PDF-bestand om te controleren of de opgegeven nummeringsstijl is toegepast op de koppen.

#### V: Kan ik de nummeringsstijl verder aanpassen?

 A: Ja, u kunt de nummeringsstijl verder aanpassen door de eigenschappen van de`Heading` objecten, zoals het type nummering, het startnummer en de automatische volgorde.

#### V: Kan ik verschillende nummeringsstijlen toepassen op verschillende secties van het document?

 A: Ja, u kunt verschillende nummeringsstijlen toepassen op verschillende secties van het document door meerdere nummeringsstijlen te maken.`Heading` objecten met verschillende stijlen en sequenties.