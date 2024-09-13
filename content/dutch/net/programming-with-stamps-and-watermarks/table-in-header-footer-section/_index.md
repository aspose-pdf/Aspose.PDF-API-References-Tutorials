---
title: Tabel in koptekst-voettekstsectie
linktitle: Tabel in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel toevoegt aan de kop-/voettekstsectie van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## Invoering

Heb je ooit naar een saai PDF-document gestaard en gewenst dat het net dat beetje extra flair had? Nou, dan heb je geluk! Met Aspose.PDF voor .NET kun je PDF-bestanden maken en bewerken als een pro. Vandaag duiken we in een handige functie waarmee je een tabel in de koptekst van je PDF-document kunt toevoegen. Je leert niet alleen hoe je dat moet doen, maar ik begeleid je ook stap voor stap, waardoor het hele proces zo soepel als boter verloopt. 🎉

## Vereisten

Voordat we beginnen met het daadwerkelijke coderen, zorgen we ervoor dat je alles hebt wat je nodig hebt om te beginnen. Dit is wat je nodig hebt:

1.  Visual Studio: Zorg ervoor dat u Visual Studio op uw computer hebt geïnstalleerd. Als u dat niet hebt gedaan, kunt u het downloaden van[De website van Microsoft](https://visualstudio.microsoft.com/).
2.  Aspose.PDF-bibliotheek: U moet de Aspose.PDF-bibliotheek voor .NET hebben. U kunt de volgende link gebruiken om de[Aspose.PDF voor .NET-pakket](https://releases.aspose.com/pdf/net/).
3. Basiskennis van C#: Je zou ten minste een basiskennis van C# moeten hebben. Maak je geen zorgen als je nog aan het leren bent; ik zal het zo eenvoudig mogelijk houden!

## Pakketten importeren

Oké, tijd om de mouwen op te stropen en te gaan coderen! Maar eerst moeten we onze omgeving instellen door de benodigde pakketten te importeren. Zo doe je dat:

###  Open uw project
Open het Visual Studio-project waarin u aan het PDF-bestand gaat werken. 

###  Referentie toevoegen aan Aspose.PDF
1. NuGet Package Manager: Klik met de rechtermuisknop op uw project in Solution Explorer en selecteer 'NuGet-pakketten beheren'.
2. Zoeken naar Aspose.PDF: typ 'Aspose.PDF' in de zoekbalk en installeer het pakket.

Aan het einde van deze stap zou alles ingesteld moeten zijn en klaar om te beginnen met coderen!

Laten we nu aan de slag gaan met wat code! Volg deze stappen om een tabel te maken in de headersectie van uw PDF:

## Stap 1: Stel het pad naar uw documentdirectory in

Voordat we beginnen met het maken van onze PDF, moeten we definiëren waar ons document wordt opgeslagen. Dit is hoe je dat doet:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Verander dit naar uw werkelijke directory
```

 Vervangen`YOUR DOCUMENT DIRECTORY`met het pad waar u uw PDF wilt opslaan. Dit kan overal op uw systeem zijn, zorg er alleen voor dat het toegankelijk is!

## Stap 2: Het document instantiëren

Vervolgens maken we een nieuw PDF-document.

```csharp
// Instantieer Document-instantie door een lege constructor aan te roepen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

Wat we hier doen is een leeg PDF-document maken waar we al onze extraatjes aan toevoegen.

## Stap 3: Maak een nieuwe pagina

Laten we een nieuwe pagina aan ons document toevoegen. 

```csharp
// Maak een pagina in het pdf-document
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Beschouw deze pagina als een leeg canvas waarop we ons meesterwerk schilderen!

## Stap 4: Maak een koptekstsectie

Nu gaan we een header voor onze PDF maken.

```csharp
// Maak een koptekstsectie van het PDF-bestand
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

Deze header bevat onze tabel. 

## Stap 5: Wijs de koptekst toe aan de pagina

Vervolgens willen we ervoor zorgen dat onze header op de pagina wordt weergegeven.

```csharp
// Stel de oneven koptekst in voor het PDF-bestand
page.Header = header;
```

## Stap 6: Stel de bovenmarge in

Om ervoor te zorgen dat er bovenaan wat ruimte is voor de header, passen we de marge aan.

```csharp
//Stel de bovenmarge voor de headersectie in
header.Margin.Top = 20;
```

Het instellen van een marge is alsof je je tekst wat persoonlijke ruimte geeft: niemand houdt ervan om opgesloten te zitten!

## Stap 7: Maak de tabel

Nu is het tijd om de tabel te maken die in onze header komt.

```csharp
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Stap 8: Voeg de tabel toe aan de koptekst

We voegen onze nieuwe tabel toe aan de alineaverzameling van de koptekst.

```csharp
// Voeg de tabel toe in de alineaverzameling van de gewenste sectie
header.Paragraphs.Add(tab1);
```

## Stap 9: Celranden instellen

Laten we onze tabel wat structuur geven door de standaard celrand te definiëren.

```csharp
// Standaard celrand instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Stap 10: Kolombreedtes definiëren

U kunt aangeven hoe breed elke kolom van de tabel moet zijn.

```csharp
// Instellen met kolombreedtes van de tabel
tab1.ColumnWidths = "60 300";
```

De waarden geven de breedte van elke kolom in punten weer. U kunt ze gerust aanpassen aan uw behoeften!

## Stap 11: Rijen maken en cellen toevoegen

Het is tijd om wat rijen en cellen toe te voegen! 

```csharp
//Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

Hiermee wordt de eerste rij met een cel met tekst gemaakt en wordt de achtergrondkleur ingesteld op grijs.

## Stap 12: Rijbreedte en tekststijl instellen

Wilt u dat uw rij meerdere kolommen beslaat? Dit doet u als volgt:

```csharp
// Stel de rijspanwaarde voor de eerste rij in op 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

Met deze stap stelt u niet alleen de rijbreedte in, maar wijzigt u ook de tekstkleur en het lettertype.

## Stap 13: Voeg een tweede rij toe

Zullen we een extra rij aan onze tabel toevoegen?

```csharp
// Maak een andere rij in de tabel
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Stel de achtergrondkleur in voor Rij 2
row2.BackgroundColor = Color.White;
```

## Stap 14: Voeg een afbeelding toe aan de tweede rij

Nu gaan we een logo toevoegen om onze tafel er flitsend uit te laten zien!

```csharp
// Voeg de cel toe die de afbeelding bevat
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; // Zorg ervoor dat u de afbeelding in uw directory plaatst
```

 Vergeet niet de`"aspose-logo.jpg"` met de werkelijke naam van uw afbeelding!

## Stap 15: Pas de breedte van de afbeelding aan

Stel de afbeeldingsbreedte in om ervoor te zorgen dat deze er goed uitziet in de cel.

```csharp
// Stel de afbeeldingsbreedte in op 60
img.FixWidth = 60;

//Voeg de afbeelding toe aan de tabelcel
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## Stap 16: Voeg tekst toe aan de tweede cel

Tijd om een kleine tekst naast ons logo toe te voegen!

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## Stap 17: Lijn de tekst verticaal en horizontaal uit

Zorg dat alles er netjes uitziet. Lijn je tekst uit!

```csharp
// Stel de verticale uitlijning van de tekst in op gecentreerd
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Stap 18: Sla het PDF-document op

En als laatste, maar zeker niet onbelangrijk: laten we onze creatie redden!

```csharp
// Sla het PDF-bestand op
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Et voilà! Je hebt een verbluffende PDF gemaakt, compleet met een tabel in de headersectie!

## Conclusie

En daar heb je het! Je hebt succesvol een tabel toegevoegd aan de header van je PDF-document met Aspose.PDF voor .NET. Het is verbazingwekkend hoe slechts een paar regels code een eenvoudige PDF kunnen transformeren in een professioneel ogend document. Of je nu rapporten, facturen of presentaties voorbereidt, een vleugje creativiteit kan het verschil maken. 

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken en bewerken.

### Heb ik een licentie nodig om Aspose.PDF te gebruiken?
 Hoewel u de bibliotheek gratis kunt gebruiken tijdens de proefperiode, is een licentie vereist voor uitgebreid gebruik. U kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.

### Waar kan ik de documentatie vinden?
Uitgebreide documentatie en voorbeelden vindt u op de[Aspose.PDF documentatiepagina](https://reference.aspose.com/pdf/net/).

### Hoe kan ik contact opnemen met de ondersteuning bij technische problemen?
 U kunt contact opnemen voor ondersteuning via de[Aspose-forum](https://forum.aspose.com/c/pdf/10).

### Kan ik tabellen maken in andere secties van de PDF?
Absoluut! Je kunt ook tabellen maken in voetteksten en body-secties; volg gewoon dezelfde stappen.