---
title: Afbeelding toevoegen aan een tabelcel
linktitle: Afbeelding toevoegen aan een tabelcel
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg een afbeelding toe aan een tabelcel met Aspose.PDF voor .NET een stapsgewijze handleiding voor het nauwkeurig bewerken van afbeeldingen in PDF-documenten.
type: docs
weight: 10
url: /nl/net/programming-with-tables/add-image-in-a-table-cell/
---
In deze tutorial begeleiden we u door het proces van het toevoegen van een afbeelding aan een tabelcel met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode laat zien hoe u deze functionaliteit kunt bereiken. Door de onderstaande stappen te volgen, kunt u afbeeldingen effectief in uw tabelcellen opnemen.

Voordat we in de code duiken, moet u ervoor zorgen dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd en dat er in uw project naar wordt verwezen.

## Stap 1: Het document instellen

 Om te beginnen moeten we een nieuw exemplaar van de`Document` klasse uit de Aspose.Pdf-naamruimte. Deze klasse vertegenwoordigt een PDF-document.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een Document-object instantiëren
Document pdfDocument = new Document();
```

## Stap 2: Een pagina maken

Vervolgens moeten we een pagina toevoegen aan het PDF-document. Een pagina dient als een container voor de tabel en andere elementen.

```csharp
// Maak een pagina in het pdf-document
Page sec1 = pdfDocument.Pages.Add();
```

## Stap 3: Een tabel toevoegen

 In deze stap maken we een tabel door de`Table` klasse uit de Aspose.Pdf-naamruimte.

```csharp
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Stap 4: Standaard celrand instellen

 Om consistentie te garanderen, kunnen we een standaard celrand instellen met behulp van de`DefaultCellBorder`eigenschap van de tabel`BorderInfo` voorwerp.

```csharp
// Standaard celrand instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Stap 5: Kolombreedtes instellen

 Om de breedte van elke kolom in de tabel te definiëren, kunnen we de`ColumnWidths` eigenschap. Geef de breedtes op als een tekenreeks met door spaties gescheiden waarden.

```csharp
// Instellen met kolombreedtes van de tabel
tab1.ColumnWidths = "100 100 120";
```

## Stap 6: Een afbeelding toevoegen aan een tabelcel

Nu komt het spannende gedeelte, het toevoegen van een afbeelding aan een tabelcel. Om dit te doen, volgen we deze substappen:

## Stap 6.1: Een afbeeldingsobject maken

 Maak een exemplaar van de`Image` klasse uit de Aspose.Pdf-naamruimte. Stel de`File` eigenschap toe aan het pad van het afbeeldingsbestand dat u wilt toevoegen.

```csharp
// Een afbeeldingsobject maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Stap 6.2: Een rij en cellen maken

Om de afbeelding aan de tabel toe te voegen, moeten we eerst een rij en de benodigde cellen aanmaken.

```csharp
// Maak een rij in de tabel
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Voeg een tekstcel toe aan de rij
row1.Cells.Add("Sample text in cell");

// Voeg de cel toe die de afbeelding bevat
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Stap 6.3: De afbeelding toevoegen aan de tabelcel

Ten slotte kunnen we de afbeelding aan de tabelcel toevoegen door deze als een alinea in de cel te plaatsen.

```csharp
// Voeg de afbeelding toe aan de tabelcel
cell2.Paragraphs.Add(img);
```

## Stap 6.4: Extra cellen toevoegen

Nadat u de afbeeldingscel hebt toegevoegd, kunt u indien nodig meer cellen aan de rij toevoegen.

```csharp
//Voeg een andere cel toe aan de rij
row1.Cells.Add("Previous cell with image");

// Pas de verticale uitlijning van de derde cel aan
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Stap 7: Het document opslaan

 Ten slotte kunnen we het gewijzigde document opslaan op een opgegeven locatie met behulp van de`Save` methode.

```csharp
// Document opslaan
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Gefeliciteerd! U hebt succesvol geleerd hoe u een afbeelding aan een tabelcel toevoegt met Aspose.PDF voor .NET. U kunt gerust verdere aanpassingsopties verkennen en deze functionaliteit integreren in uw projecten.

### Voorbeeldbroncode voor het toevoegen van een afbeelding in een tabelcel met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een Document-object instantiëren
Document pdfDocument = new Document();
// Maak een pagina in het pdf-document
Page sec1 = pdfDocument.Pages.Add();
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Voeg de tabel toe in de alineaverzameling van de gewenste pagina
sec1.Paragraphs.Add(tab1);
// Standaard celrand instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Instellen met kolombreedtes van de tabel
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Voeg de cel toe die de afbeelding bevat
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Voeg de afbeelding toe aan de tabelcel
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Document opslaan
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Conclusie

In deze tutorial hebben we een stapsgewijze handleiding gegeven over hoe u een afbeelding toevoegt aan een tabelcel met Aspose.PDF voor .NET. We begonnen met het instellen van het document, het maken van een pagina en het toevoegen van een tabel. Vervolgens stelden we de standaard celrand en kolombreedtes in. We lieten zien hoe u een afbeelding toevoegt aan een tabelcel en de verticale uitlijning van de cel aanpast. Tot slot hebben we het gewijzigde document opgeslagen. Door deze stappen te volgen, kunt u uw PDF-documenten efficiënt verbeteren met afbeeldingen in tabelcellen.

### Veelgestelde vragen

#### V: Kan ik meerdere afbeeldingen aan verschillende cellen in dezelfde tabel toevoegen met Aspose.PDF voor .NET?

A: Ja, u kunt meerdere afbeeldingen toevoegen aan verschillende cellen binnen dezelfde tabel met Aspose.PDF voor .NET. Volg gewoon hetzelfde proces dat in de tutorial wordt gedemonstreerd voor elke afbeelding die u aan de tabel wilt toevoegen.

#### V: Kan ik de afbeeldingsgrootte en -positie binnen de tabelcel aanpassen?

 A: Ja, u kunt de afbeeldingsgrootte en -positie binnen de tabelcel aanpassen door de eigenschappen van de afbeelding aan te passen.`Image`object. U kunt de breedte en hoogte van de afbeelding instellen, evenals de uitlijning binnen de cel.

#### V: Kan ik afbeeldingen toevoegen aan een tabel met een dynamisch aantal rijen en kolommen?

A: Ja, u kunt afbeeldingen toevoegen aan een tabel met een dynamisch aantal rijen en kolommen. Aspose.PDF voor .NET biedt flexibiliteit bij het maken van tabellen met verschillende afmetingen. U kunt rijen en cellen toevoegen zoals nodig is en vervolgens afbeeldingen toevoegen aan specifieke cellen.

#### V: Welke afbeeldingsformaten worden door Aspose.PDF voor .NET ondersteund voor het toevoegen van afbeeldingen aan tabelcellen?

A: Aspose.PDF voor .NET ondersteunt een breed scala aan afbeeldingsformaten, waaronder JPEG, PNG, GIF, BMP en TIFF. U kunt afbeeldingen van elk van deze formaten gebruiken om ze toe te voegen aan tabelcellen.

#### V: Kan ik afbeeldingen toevoegen aan tabellen in een bestaand PDF-document?

A: Ja, u kunt afbeeldingen toevoegen aan tabellen in een bestaand PDF-document met Aspose.PDF voor .NET. Laad gewoon het bestaande document en volg dezelfde stappen om afbeeldingen toe te voegen aan de tabel zoals gedemonstreerd in de tutorial.