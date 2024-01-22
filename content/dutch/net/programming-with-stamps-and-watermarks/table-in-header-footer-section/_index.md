---
title: Tabel in koptekst-voettekstsectie
linktitle: Tabel in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel toevoegt aan de kop-/voettekstsectie van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In deze zelfstudie begeleiden we u stap voor stap bij het toevoegen van een tabel aan de kop- of voettekst van een PDF-document met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode laat zien hoe u een leeg PDF-document maakt, een pagina toevoegt, de koptekstsectie configureert, een tabel maakt, rijen en cellen aan de tabel toevoegt en uiteindelijk het PDF-document opslaat.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het PDF-document en de pagina maken

 De eerste stap is het maken van een exemplaar van de`Document` class en voeg een pagina toe aan het document. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Een documentobject instantiëren
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Maak een pagina in het PDF-document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar u het PDF-document wilt opslaan.

## Stap 3: Het headergedeelte configureren

 Nu gaan we het koptekstgedeelte van het PDF-document configureren door een exemplaar van het`HeaderFooter` klas. Hier is hoe:

```csharp
// Maak een koptekstsectie voor het PDF-bestand
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definieer de koptekstsectie voor de pagina
page. Header = header;

// Stel de bovenmarge van het koptekstgedeelte in
header. Margin. Top = 20;
```

## Stap 4: De tabel maken

 Nu gaan we een tabel maken met behulp van de`Table` class en voeg deze toe aan de paragraafverzameling van de kopsectie. Hier is hoe:

```csharp
// Instantieer een Table-object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg de tabel toe aan de alineaverzameling van de koptekstsectie
header.Paragraphs.Add(tab1);

// Definieer de breedte van de kolommen van de tabel
tab1.ColumnWidths = "60,300";
```

Met de bovenstaande code wordt een tabel gemaakt met twee kolommen met een opgegeven breedte.

## Stap 5: Voeg rijen en cellen toe aan de tabel

 Nu gaan we rijen en cellen aan de tabel toevoegen met behulp van de`Row` klasse en de`Cell` klas. Hier is hoe:

```csharp
// Maak een rij in de tabel en voeg cellen toe
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Voeg de eerste cel van de eerste rij samen
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Maak nog een rij in de tabel en voeg een cel met een afbeelding toe
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

Nadat de tabel aan het kopgedeelte is toegevoegd, kunnen we het PDF-document opslaan. Hier is hoe:

```csharp
// Sla het PDF-bestand op
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar de map waar u het PDF-document wilt opslaan.

### Voorbeeldbroncode voor tabel in koptekst-voettekstsectie met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer de documentinstantie door een lege constructor aan te roepen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Maak een pagina in het pdf-document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Maak een koptekstsectie van het PDF-bestand
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//Stel de Odd Header in voor het PDF-bestand
page.Header = header;

// Stel de bovenmarge voor de koptekstsectie in
header.Margin.Top = 20;

// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
header.Paragraphs.Add(tab1);

// Stel de standaardcelrand in met het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Ingesteld met kolombreedtes van de tabel
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Stel de rijbereikwaarde voor de eerste rij in op 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Stel de achtergrondkleur in voor Rij2
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

// Sla het pdf-bestand op
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een tabel kunt toevoegen aan de kop- of voettekst van een PDF-document met Aspose.PDF voor .NET. U kunt nu uw kop- en voetteksten aanpassen door tabellen toe te voegen om aanvullende informatie in uw PDF-documenten weer te geven.

### Veelgestelde vragen over de tabel in de koptekst-voettekstsectie

#### Vraag: Wat is het doel van het toevoegen van een tabel in de kop- of voettekst van een PDF-document?

A: Door een tabel toe te voegen aan de kop- of voettekst van een PDF-document kunt u gestructureerde en georganiseerde informatie weergeven, zoals titels, ondertitels, logo's of andere inhoud die u consistent op elke pagina van het document wilt weergeven.

#### Vraag: Hoe zorgt de meegeleverde C#-broncode voor de toevoeging van een tabel in de kop- of voettekst van een PDF-document?

A: De code demonstreert het proces van het maken van een leeg PDF-document, het toevoegen van een pagina, het configureren van de koptekstsectie, het maken van een tabel met rijen en cellen en het uiteindelijk opslaan van het PDF-document. Het resultaat is een tabel die wordt weergegeven in het kopgedeelte van het PDF-document.

#### Vraag: Kan ik het uiterlijk van de tabelcellen aanpassen, zoals randen, achtergrondkleur en tekststijl?

A: Ja, u kunt het uiterlijk van de tabelcellen aanpassen door eigenschappen in te stellen zoals celranden, achtergrondkleur, tekststijl, lettertype, lettergrootte en meer.

#### Vraag: Hoe wordt de tabel toegevoegd aan het kopgedeelte van het PDF-document?

A: De code voegt de tabel toe aan de alineaverzameling van de koptekstsectie, wat ervoor zorgt dat de tabel wordt weergegeven in de koptekst van elke pagina.

#### Vraag: Kan ik indien nodig meer rijen en cellen aan de tabel toevoegen?

 A: Absoluut, u kunt meer rijen en cellen aan de tabel toevoegen door de`Rows.Add()` En`Cells.Add()` methoden. Hierdoor kunt u de tabelinhoud naar wens structureren.

#### Vraag: Is het mogelijk om de breedte van de tabelkolommen aan te passen?
 A: Ja, u kunt de breedte van de tabelkolommen aanpassen met behulp van de`ColumnWidths` eigendom. Hiermee kunt u de indeling van de tafel bepalen.

#### Vraag: Hoe kan ik cellen over meerdere kolommen of rijen in de tabel verdelen?
 A: Om cellen over meerdere kolommen te verdelen, kunt u de`ColSpan` eigenschap van de overeenkomstige cel. Op dezelfde manier kunt u de`RowSpan` eigenschap om cellen over meerdere rijen te verdelen.

#### Vraag: Wat gebeurt er als ik een tabel wil toevoegen aan zowel de koptekst- als de voettekstsectie van het PDF-document?

A: U kunt een vergelijkbare aanpak volgen voor zowel de kop- als de voettekstsecties. Maak eenvoudig een`HeaderFooter` instance voor de voettekst, configureer deze en voeg de tabel toe aan de alineaverzameling.

#### Vraag: Kan ik afbeeldingen in de tabelcellen gebruiken, en hoe wordt dat bereikt?

 A: Ja, u kunt afbeeldingen toevoegen aan tabelcellen. Het codevoorbeeld demonstreert het toevoegen van een afbeelding aan een cel door een`Image` object, stelt het bestandspad en de afmetingen ervan in en voegt het vervolgens toe aan de alinea's van een cel.

#### Vraag: Hoe zorg ik ervoor dat de tabel consistent op alle pagina's in het PDF-document wordt weergegeven?

 A: Wanneer u de tabel toevoegt aan de kop- of voettekstsectie met behulp van de`HeaderFooter` Aspose.PDF zorgt er bijvoorbeeld voor dat de tabel consistent op elke pagina verschijnt, wat een uniforme lay-out oplevert.