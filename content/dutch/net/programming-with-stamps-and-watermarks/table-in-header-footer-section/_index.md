---
title: Tabel in koptekst-voettekstsectie
linktitle: Tabel in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel toevoegt aan de kop-/voettekstsectie van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In deze tutorial laten we u stap voor stap zien hoe u een tabel toevoegt aan de header- of footersectie van een PDF-document met Aspose.PDF voor .NET. De meegeleverde C#-broncode laat zien hoe u een leeg PDF-document maakt, een pagina toevoegt, de headersectie configureert, een tabel maakt, rijen en cellen toevoegt aan de tabel en ten slotte het PDF-document opslaat.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het PDF-document en de pagina maken

 De eerste stap is het maken van een exemplaar van de`Document` klasse en voeg een pagina toe aan het document. Dit is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Een Document-object instantiëren
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Een pagina maken in het PDF-document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het PDF-document wilt opslaan.

## Stap 3: De headersectie configureren

 Nu gaan we de headersectie van het PDF-document configureren door een exemplaar van de`HeaderFooter` klas. Zo doe je dat:

```csharp
// Maak een headersectie voor het PDF-bestand
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definieer de headersectie voor de pagina
page. Header = header;

// De bovenmarge van de headersectie instellen
header. Margin. Top = 20;
```

## Stap 4: De tabel maken

 Nu gaan we een tabel maken met behulp van de`Table` klasse en voeg het toe aan de alineaverzameling van de kopsectie. Dit is hoe:

```csharp
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg de tabel toe aan de alineaverzameling van de koptekstsectie
header.Paragraphs.Add(tab1);

// Definieer de breedtes van de kolommen van de tabel
tab1.ColumnWidths = "60,300";
```

De bovenstaande code maakt een tabel met twee kolommen met de opgegeven breedte.

## Stap 5: Rijen en cellen toevoegen aan de tabel

 Nu gaan we rijen en cellen aan de tabel toevoegen met behulp van de`Row` klasse en de`Cell` klas. Zo doe je dat:

```csharp
// Maak een rij in de tabel en voeg cellen toe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Voeg de eerste cel van de eerste rij samen
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Maak een nieuwe rij in de tabel en voeg een cel met een afbeelding toe
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Stap 6: Het PDF-document opslaan

Zodra de tabel is toegevoegd aan de headersectie, kunnen we het PDF-document opslaan. Dit is hoe:

```csharp
// Sla het PDF-bestand op
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waarin u het PDF-document wilt opslaan.

### Voorbeeldbroncode voor Tabel in koptekst-voettekstsectie met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer Document-instantie door een lege constructor aan te roepen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Maak een pagina in het pdf-document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Maak een koptekstsectie van het PDF-bestand
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de oneven koptekst in voor het PDF-bestand
page.Header = header;

// Stel de bovenmarge voor de headersectie in
header.Margin.Top = 20;

// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg de tabel toe in de alineaverzameling van de gewenste sectie
header.Paragraphs.Add(tab1);

// Standaard celrand instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Instellen met kolombreedtes van de tabel
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Stel de rijspanwaarde voor de eerste rij in op 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Stel de achtergrondkleur in voor Rij 2
row2.BackgroundColor = Color.White;

// Voeg de cel toe die de afbeelding bevat
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Stel de afbeeldingsbreedte in op 60
img.FixWidth = 60;

// Voeg de afbeelding toe aan de tabelcel
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Stel de verticale uitlijning van de tekst in als gecentreerd
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Sla het PDF-bestand op
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een tabel toevoegt in de kop- of voettekstsectie van een PDF-document met Aspose.PDF voor .NET. U kunt nu uw kop- en voetteksten aanpassen door tabellen toe te voegen om extra informatie in uw PDF-documenten weer te geven.

### FAQ's voor tabel in koptekst-voettekstsectie

#### V: Wat is het doel van het toevoegen van een tabel in de kop- of voettekst van een PDF-document?

A: Door een tabel toe te voegen in de kop- of voettekst van een PDF-document kunt u gestructureerde en georganiseerde informatie weergeven, zoals titels, ondertitels, logo's of andere inhoud die u consistent op elke pagina van het document wilt weergeven.

#### V: Hoe kan met de meegeleverde C#-broncode een tabel worden toegevoegd aan de kop- of voettekst van een PDF-document?

A: De code demonstreert het proces van het maken van een leeg PDF-document, het toevoegen van een pagina, het configureren van de headersectie, het maken van een tabel met rijen en cellen en het uiteindelijk opslaan van het PDF-document. Het resultaat is een tabel die wordt weergegeven in de headersectie van het PDF-document.

#### V: Kan ik het uiterlijk van de tabelcellen aanpassen, zoals de randen, achtergrondkleur en tekststijl?

A: Ja, u kunt het uiterlijk van de tabelcellen aanpassen door eigenschappen als celranden, achtergrondkleur, tekststijl, lettertype, lettergrootte en meer in te stellen.

#### V: Hoe wordt de tabel toegevoegd aan de headersectie van het PDF-document?

A: De code voegt de tabel toe aan de alineaverzameling van de headersectie, wat ervoor zorgt dat de tabel in de header van elke pagina wordt weergegeven.

#### V: Kan ik indien nodig meer rijen en cellen aan de tabel toevoegen?

 A: Absoluut, u kunt meer rijen en cellen aan de tabel toevoegen door de`Rows.Add()` En`Cells.Add()` methoden. Hiermee kunt u de tabelinhoud naar wens structureren.

#### V: Is het mogelijk om de breedte van de tabelkolommen aan te passen?
 A: Ja, u kunt de breedte van de tabelkolommen aanpassen met behulp van de`ColumnWidths` eigenschap. Hiermee kunt u de lay-out van de tabel bepalen.

#### V: Hoe kan ik cellen over meerdere kolommen of rijen in de tabel verdelen?
 A: Om cellen over meerdere kolommen te verdelen, kunt u de`ColSpan`eigenschap van de overeenkomstige cel. Op dezelfde manier kunt u de`RowSpan` eigenschap om cellen over meerdere rijen te verdelen.

#### V: Wat gebeurt er als ik een tabel wil toevoegen aan zowel de koptekst als de voettekst van het PDF-document?

 A: U kunt een vergelijkbare aanpak volgen voor zowel de header- als de footersecties. Maak gewoon een`HeaderFooter` exemplaar voor de voettekst, configureer deze en voeg de tabel toe aan de alineaverzameling.

#### V: Kan ik afbeeldingen gebruiken in de tabelcellen en hoe doe ik dat?

 A: Ja, u kunt afbeeldingen toevoegen binnen tabelcellen. Het codevoorbeeld laat zien hoe u een afbeelding aan een cel kunt toevoegen door een`Image` object, stelt u het bestandspad en de afmetingen in en voegt u het vervolgens toe aan de alinea's van een cel.

#### V: Hoe zorg ik ervoor dat de tabel consistent wordt weergegeven op alle pagina's van het PDF-document?

 A: Wanneer u de tabel toevoegt aan de kop- of voettekstsectie met behulp van de`HeaderFooter` Aspose.PDF zorgt er bijvoorbeeld voor dat de tabel op elke pagina consistent wordt weergegeven, met een uniforme lay-out.