---
title: Tekst rond afbeelding in PDF-bestand plaatsen
linktitle: Tekst rond afbeelding in PDF-bestand plaatsen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tekst rond een afbeelding in een PDF-bestand plaatst met Aspose.PDF voor .NET.
type: docs
weight: 260
url: /nl/net/programming-with-text/placing-text-around-image/
---
In deze tutorial leggen we uit hoe u tekst rond een afbeelding in een PDF-bestand plaatst met behulp van de Aspose.PDF-bibliotheek voor .NET. We doorlopen het stapsgewijze proces van het maken van een tabel, het toevoegen van een afbeelding en het positioneren van tekst rond de afbeelding met behulp van de meegeleverde C#-broncode.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- De Aspose.PDF voor .NET-bibliotheek is geïnstalleerd.
- Basiskennis van C#-programmering.

## Stap 1: De documentenmap instellen

 Eerst moet u het pad instellen naar de map waar u het gegenereerde PDF-bestand wilt opslaan. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de gewenste map.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en pagina

 Vervolgens maken we een`Document` object en voeg er een pagina aan toe met behulp van de`Pages.Add()` methode.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Stap 3: Maak een tabel

 We maken een tabel met behulp van de`Table` klasse en voeg deze toe aan de paragrafenverzameling van de pagina.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Stap 4: Stel de breedte en marges van de tabelkolommen in

 We stellen de kolombreedtes van de tabel in en maken een`MarginInfo` object om de marges in te stellen.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Stap 5: Voeg een afbeelding toe aan de tabel

 Wij creëren een`Image` object, specificeer het pad van het afbeeldingsbestand en stel de vaste hoogte en breedte van de afbeelding in. Vervolgens voegen we de afbeelding toe aan de verzameling paragrafen van de tabelcel.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Stap 6: Voeg tekst toe rond de afbeelding

 We maken stringvariabelen met HTML-geformatteerde tekst en maken een`HtmlFragment`object. Vervolgens voegen we de HTML-tekst toe aan de tabelcel met de afbeelding.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Stap 7: Voeg extra tekst toe

 Wij creëren een andere`HtmlFragment` object met aanvullende HTML-geformatteerde tekst en voeg deze toe aan een aparte tabelcel.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Stap 8: Sla het PDF-document op

Ten slotte slaan we het PDF-document op in het opgegeven uitvoerbestand.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Voorbeeldbroncode voor het plaatsen van tekst rond een afbeelding met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Documentobject instantiëren
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Maak een pagina in de Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Een tabelobject instantiëren
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Voeg de tabel toe in de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(table1);
// Instellen met kolombreedtes van de tabel
table1.ColumnWidths = "120 270";
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Stel de standaard celopvulling in op het MarginInfo-object
table1.DefaultCellPadding = margin;
// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Een afbeeldingsobject maken
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Geef het pad naar het afbeeldingsbestand op
logo.File = dataDir + "aspose-logo.jpg";
// Geef de afbeelding op Vaste hoogte
logo.FixHeight = 120;
// Geef de afbeelding een vaste breedte
logo.FixWidth = 110;
row1.Cells.Add();
// Voeg de afbeelding toe aan de alineaverzameling van de tabelcel
row1.Cells[0].Paragraphs.Add(logo);
// Maak stringvariabelen met tekst die html-tags bevat
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Maak een tekstobject dat rechts van de afbeelding moet worden toegevoegd
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Voeg de tekstparagrafen met HTML-tekst toe aan de tabelcel
row1.Cells[1].Paragraphs.Add(TitleText);
// Stel de verticale uitlijning van de rij-inhoud in als Boven
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Stel de rijspanwaarde voor de tweede rij in op 2
SecondRow.Cells[0].ColSpan = 2;
// Stel de verticale uitlijning van de tweede rij in als Boven
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Voeg de tekstparagrafen met HTML-tekst toe aan de tabelcel
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Sla het PDF-bestand op
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Conclusie

In deze tutorial hebt u geleerd hoe u tekst rond een afbeelding in een PDF-document plaatst met behulp van de Aspose.PDF-bibliotheek voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code uit te voeren, kunt u een tabel maken, een afbeelding toevoegen en tekst rond de afbeelding in een PDF-document plaatsen.

### Veelgestelde vragen

#### V: Wat is het doel van de tutorial 'Tekst rond een afbeelding in een PDF-bestand plaatsen'?

A: De tutorial "Tekst rondom afbeelding in PDF-bestand plaatsen" laat zien hoe u de Aspose.PDF-bibliotheek voor .NET kunt gebruiken om tekst rondom een afbeelding in een PDF-document te plaatsen. De tutorial biedt een stapsgewijze handleiding en C#-broncode om u te helpen een tabel te maken, een afbeelding toe te voegen en tekst rondom de afbeelding te positioneren.

#### V: Waarom zou ik tekst rond een afbeelding in een PDF-document willen plaatsen?

A: Tekst rondom een afbeelding plaatsen verbetert de visuele presentatie van uw PDF-documenten, waardoor ze aantrekkelijker en informatiever worden. Deze techniek wordt vaak gebruikt in documenten, brochures, rapporten en andere materialen waarbij u afbeeldingen en tekst op een esthetisch aantrekkelijke manier wilt combineren.

#### V: Hoe stel ik de documentenmap in?

A: Om de documentenmap in te stellen:

1.  Vervangen`"YOUR DOCUMENT DIRECTORY"` in de`dataDir` variabele met het pad naar de map waar u het gegenereerde PDF-bestand wilt opslaan.

#### V: Hoe maak ik een tabel en voeg ik er een afbeelding aan toe?

 A: De tutorial begeleidt u door het proces van het maken van een tabel met behulp van de`Table` klasse en een afbeelding aan de tabel toevoegen met behulp van de`Image` klasse. U geeft het pad, de hoogte en de breedte van het afbeeldingsbestand op voordat u het aan een tabelcel toevoegt.

#### V: Hoe plaats ik tekst rond de afbeelding?

 A: Om tekst rond de afbeelding te plaatsen, maakt u HTML-geformatteerde tekst met behulp van de`HtmlFragment` klasse. Deze tekst bevat zowel een titel als een hoofdtekst. Vervolgens voegt u deze HTML-tekst toe aan een tabelcel die grenst aan de afbeeldingscel.

#### V: Kan ik het uiterlijk van de tekst en de afbeelding aanpassen?

A: Ja, u kunt het uiterlijk van de tekst en afbeelding aanpassen met behulp van HTML-tags en -eigenschappen. U kunt bijvoorbeeld lettergroottes, kleuren, stijlen en uitlijning voor de tekst instellen. Daarnaast kunt u de grootte en afmetingen van de afbeelding aanpassen.

#### V: Hoe kan ik het PDF-document opslaan?

 A: Nadat u de afbeelding en tekst aan de tabel hebt toegevoegd, kunt u het PDF-document opslaan met behulp van de`Save` methode van de`Document` klasse. Geef het gewenste pad naar het uitvoerbestand als argument voor de`Save` methode.

#### V: Wat is het verwachte resultaat van deze tutorial?

A: Door de tutorial te volgen en de meegeleverde C#-code uit te voeren, genereert u een PDF-document dat laat zien hoe u tekst rond een afbeelding plaatst. Het uitvoerdocument bevat een tabel met een afbeelding en tekst eromheen.

#### V: Kan ik andere afbeeldingsformaten dan JPG gebruiken?

 A: Ja, u kunt verschillende afbeeldingsformaten gebruiken die worden ondersteund door de Aspose.PDF-bibliotheek, zoals PNG, BMP, GIF en meer. Bij het maken van de`Image` object, geef het bestandspad van het gewenste afbeeldingsformaat op.

#### V: Is een geldige Aspose-licentie vereist voor deze tutorial?

A: Ja, een geldige Aspose-licentie is vereist om deze tutorial correct te laten werken. U kunt een volledige licentie kopen of een tijdelijke licentie van 30 dagen verkrijgen via de Aspose-website.