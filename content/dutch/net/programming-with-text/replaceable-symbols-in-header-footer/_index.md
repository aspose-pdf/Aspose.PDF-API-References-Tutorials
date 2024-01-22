---
title: Vervangbare symbolen in de koptekst en voettekst
linktitle: Vervangbare symbolen in de koptekst en voettekst
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u vervangbare symbolen gebruikt in de kop- en voettekst van een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 320
url: /nl/net/programming-with-text/replaceable-symbols-in-header-footer/
---
In deze zelfstudie leggen we uit hoe u vervangbare symbolen kunt gebruiken in de kop- en voettekst van een PDF-document met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het maken van een PDF, het instellen van marges, het toevoegen van kop- en voettekst met vervangbare symbolen en het opslaan van de PDF met behulp van de meegeleverde C#-broncode.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- De Aspose.PDF voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van programmeren in C#.

## Stap 1: Stel de documentmap in

 Eerst moet u het pad instellen naar de map waarin u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir`variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een PDF-document en -pagina

 Vervolgens maken we een nieuw PDF-document en voegen er een pagina aan toe met behulp van de`Document` klasse en`Page` klasse uit de Aspose.PDF-bibliotheek.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 3: Stel marges in

 We stellen de marges voor de pagina in met behulp van de`MarginInfo`klas. Pas de margewaarden aan volgens uw vereisten.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Stap 4: Koptekst toevoegen met vervangbare symbolen

 Wij creëren een`HeaderFooter` object voor de pagina en voeg een toe`TextFragment` met vervangbare symbolen erop.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Stel desgewenst teksteigenschappen in
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Voeg meer tekstfragmenten toe of pas deze indien nodig aan
```

## Stap 5: Voettekst toevoegen met vervangbare symbolen

 Op dezelfde manier creëren we een`HeaderFooter` object voor de paginavoettekst en voeg toe`TextFragment` objecten met vervangbare symbolen erop.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Voeg meer tekstfragmenten toe of pas deze indien nodig aan

hfFoot.Paragraphs.Add(tab2);
```

## Stap 6: Sla het PDF-document op

Ten slotte slaan we het PDF-document op in het opgegeven uitvoerbestand.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor vervangbare symbolen in koptekstvoettekst met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Wijs de marginInfo-instantie toe aan de Margin-eigenschap van sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Maak een tekstparagraaf waarin de inhoud wordt opgeslagen en als koptekst wordt weergegeven
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Maak een HeaderFooter-object voor de sectie
HeaderFooter hfFoot = new HeaderFooter();
// Stel het HeaderFooter-object in op oneven en even voettekst
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Voeg een tekstparagraaf toe met het huidige paginanummer van het totale aantal pagina's
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Een tabelobject instantiëren
Table tab2 = new Table();
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
hfFoot.Paragraphs.Add(tab2);
// Ingesteld met kolombreedtes van de tabel
tab2.ColumnWidths = "165 172 165";
// Maak rijen in de tabel en vervolgens cellen in de rijen
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Stel de verticale uitlijning van de tekst in als gecentreerd
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total voor Java is een compilatie van elke Java-component die door Aspose wordt aangeboden. Het wordt op #$NL" + "dagelijks gecompileerd om ervoor te zorgen dat het de meest actuele versies van elke component bevat van onze Java-componenten. #$NL " + "Met Aspose.Total voor Java kunnen ontwikkelaars een breed scala aan applicaties creëren. #$NL #$NL #$NP" + "Aspose.Total voor Java is een compilatie van elke Java-component aangeboden door Aspose. Het wordt op #$NL" + "dagelijks samengesteld om ervoor te zorgen dat het de meest up-to-date versies van elk van onze Java-componenten bevat. #$NL " + "Het gebruik van Aspose.Total voor Java-ontwikkelaars kan een brede scala aan toepassingen. #$NL #$NL #$NP" + "Aspose.Total voor Java is een compilatie van alle Java-componenten die door Aspose worden aangeboden. Het wordt #$NL" + "dagelijks samengesteld om ervoor te zorgen dat het de meeste up-to-date versies van elk van onze Java-componenten. #$NL " + "Het gebruik van Aspose.Total voor Java-ontwikkelaars kan een breed scala aan applicaties creëren. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(table);
// Stel de standaardcelrand in met het BorderInfo-object
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Stel de tabelrand in met een ander aangepast BorderInfo-object
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Maak rijen in de tabel en vervolgens cellen in de rijen
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Conclusie

In deze zelfstudie hebt u geleerd hoe u vervangbare symbolen kunt gebruiken in de kop- en voettekst van een PDF-document met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een PDF maken, marges instellen, kop- en voettekst met vervangbare symbolen toevoegen en de PDF opslaan.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de tutorial "Vervangbare symbolen in koptekstvoettekst"?

A: De tutorial "Vervangbare symbolen in koptekstvoettekst" is bedoeld om u te begeleiden bij het gebruik van de Aspose.PDF-bibliotheek voor .NET om vervangbare symbolen toe te voegen aan de kop- en voettekst van een PDF-document. Met vervangbare symbolen kunt u specifieke tijdelijke aanduidingen dynamisch vervangen door werkelijke waarden bij het genereren van de PDF.

#### Vraag: Wat zijn vervangbare symbolen in de context van een PDF-kop- en voettekst?

A: Vervangbare symbolen zijn tijdelijke aanduidingen die u in de kop- en voettekst van een PDF-document kunt invoegen. Deze symbolen fungeren als dynamische tijdelijke aanduidingen voor waarden die tijdens runtime kunnen worden ingevuld, zoals paginanummers, datums en aangepaste informatie.

#### Vraag: Waarom zou ik vervangbare symbolen willen gebruiken in de kop- en voettekst van een PDF?

A: Vervangbare symbolen in de kop- en voettekst zijn handig als u dynamische informatie in uw PDF-documenten wilt opnemen, zoals paginanummers, datums of andere variabele gegevens die kunnen veranderen wanneer het document wordt gegenereerd.

#### Vraag: Hoe kan ik de marges voor de PDF-pagina instellen?

 A: U kunt de marges voor de PDF-pagina instellen met behulp van de`MarginInfo` klasse en wijs deze toe aan de`Margin` eigendom van de`PageInfo` van de pagina. Pas de margewaarden indien nodig aan.

#### Vraag: Hoe voeg ik vervangbare symbolen toe aan de kop- en voettekst?

 A: U kunt vervangbare symbolen toevoegen door een`HeaderFooter` object voor de kop- en voettekst van de pagina. Vervolgens kunt u toevoegen`TextFragment`objecten met de gewenste tekst, inclusief vervangbare symbolen, naar de`Paragraphs` verzameling van de`HeaderFooter` voorwerp.

#### Vraag: Kan ik het uiterlijk van de vervangbare symbolen aanpassen?

 A: Ja, u kunt het uiterlijk van de vervangbare symbolen aanpassen door de eigenschappen van de`TextFragment` objecten die de symbolen bevatten. U kunt eigenschappen instellen zoals lettertype, lettergrootte, kleur, uitlijning en regelafstand.

#### Vraag: Welk soort vervangbare symbolen kan ik gebruiken?

A: U kunt verschillende vervangbare symbolen gebruiken, zoals:

- `$p`: Huidig paginanummer.
- `$P`: Totaal aantal pagina's.
- `$d`: Huidige datum.
- `$t`: Huidige tijd.
- Aangepaste tijdelijke aanduidingen die u definieert.

#### Vraag: Kan ik andere tekst en opmaak rond de vervangbare symbolen opnemen?

 A: Ja, u kunt andere tekst en opmaak rondom de vervangbare symbolen in het`TextFragment` voorwerpen. Hierdoor kunt u complexere kop- en voetteksten maken die dynamische en statische inhoud bevatten.

#### Vraag: Hoe kan ik het gegenereerde PDF-document opslaan?

 A: Om het gegenereerde PDF-document op te slaan, kunt u de`Save` werkwijze van de`Document`klas. Geef het gewenste pad en de naam van het uitvoerbestand op als argument.

#### Vraag: Is een geldige Aspose-licentie vereist voor deze zelfstudie?

A: Ja, een geldige Aspose-licentie is vereist om de code in deze tutorial succesvol uit te voeren. U kunt een volledige licentie of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.