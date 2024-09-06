---
title: Maak een PDF met meerdere kolommen
linktitle: Maak een PDF met meerdere kolommen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een PDF met meerdere kolommen maakt met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-text/create-multi-column-pdf/
---
Deze tutorial begeleidt u door het proces van het maken van een PDF met meerdere kolommen met behulp van Aspose.PDF voor .NET. De meegeleverde C#-broncode demonstreert de benodigde stappen.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u over het volgende beschikt:

- Visual Studio of een andere C#-compiler die op uw computer is geïnstalleerd.
- Aspose.PDF voor .NET-bibliotheek. U kunt het downloaden van de officiële Aspose-website of een pakketbeheerder zoals NuGet gebruiken om het te installeren.

## Stap 1: Het project opzetten
1. Maak een nieuw C#-project in uw favoriete ontwikkelomgeving.
2. Voeg een verwijzing toe naar de Aspose.PDF voor .NET-bibliotheek.

## Stap 2: Importeer de vereiste naamruimten
Voeg in het codebestand waarin u een PDF met meerdere kolommen wilt maken, het volgende toe met behulp van richtlijnen boven aan het bestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Stap 3: Stel de documentdirectory in
 Zoek in de code de regel met de tekst`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het pad naar de map waar uw documenten zijn opgeslagen.

## Stap 4: Maak een nieuw Document-exemplaar
 Een nieuwe instantiëren`Document` object door de volgende regel code toe te voegen:

```csharp
Document doc = new Document();
```

## Stap 5: Stel de paginamarges in
 Geef de linker- en rechtermarge-informatie voor het PDF-bestand op met behulp van de`PageInfo.Margin` eigendom van de`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Stap 6: Voeg een pagina toe aan het document
 Voeg een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages`verzameling. In de meegeleverde code wordt de nieuwe pagina toegewezen aan de variabele`page`.

```csharp
Page page = doc.Pages.Add();
```

## Stap 7: Maak een grafiekobject en voeg een lijn toe
 Maak een nieuwe`Graph` object met specifieke afmetingen en voeg er een lijn aan toe. Voeg vervolgens de`Graph` bezwaar maken tegen de`Paragraphs` verzameling van de pagina.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Stap 8: Voeg koptekst toe met HTML-opmaak
 Maak een`HtmlFragment` object en stel de inhoud in op de gewenste HTML-tekst. Voeg vervolgens het fragment toe aan de`Paragraphs` verzameling van de pagina.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Stap 9: Maak een FloatingBox met meerdere kolommen
 Maak een`FloatingBox` object en stel het aantal kolommen en de kolomafstand in. Voeg vervolgens tekstfragmenten en een regel toe aan de`Paragraphs` verzameling van de`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Stap 10: Sla het PDF-document op
 Sla het PDF-document op met behulp van de`Save` methode van de`Document` voorwerp.

```csharp
doc.Save(dataDir);
```

### Voorbeeldbroncode voor het maken van een PDF met meerdere kolommen met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//Geef de linkermarge-informatie voor het PDF-bestand op
doc.PageInfo.Margin.Left = 40;
// Geef de rechtermarge-info op voor het PDF-bestand
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Voeg de regel toe aan de parafrasenverzameling van het sectieobject
page.Paragraphs.Add(graph1);
// Geef de coördinaten voor de lijn op
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Maak stringvariabelen met tekst die html-tags bevat
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Maak tekstparagrafen met HTML-tekst
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Voeg vier kolommen toe in de sectie
box.ColumnInfo.ColumnCount = 2;
// Stel de afstand tussen de kolommen in
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Maak een grafiekobject om een lijn te tekenen
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Geef de coördinaten voor de lijn op
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Voeg de regel toe aan de paragrafenverzameling van het sectieobject
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusie
U hebt met succes een PDF met meerdere kolommen gemaakt met Aspose.PDF voor .NET. Het resulterende PDF-bestand is nu te vinden op het opgegeven pad naar het uitvoerbestand.

### Veelgestelde vragen

#### V: Waarop richt deze tutorial zich?

Deze tutorial is gericht op het begeleiden van u door het proces van het maken van een multi-kolom PDF met behulp van de Aspose.PDF voor .NET-bibliotheek. De meegeleverde C#-broncode demonstreert de benodigde stappen om dit te bereiken.

#### V: Welke naamruimten moet ik importeren voor deze tutorial?

A: Importeer de volgende naamruimten aan het begin van het bestand in het codebestand waarin u een PDF met meerdere kolommen wilt maken:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### V: Hoe geef ik de documentenmap op?

 A: Zoek in de code de regel`string dataDir = "YOUR DOCUMENT DIRECTORY";` en vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

#### V: Hoe maak ik een nieuw Document-exemplaar?

 A: In stap 4 maakt u een nieuwe`Document` object met behulp van de verstrekte code.

#### V: Hoe stel ik de paginamarges in?

 A: In stap 5 gebruikt u de`PageInfo.Margin` eigendom van de`Document` om de linker- en rechtermarge-informatie voor het PDF-bestand op te geven.

#### V: Hoe voeg ik een pagina toe aan het document?

 A: In stap 6 voegt u een nieuwe pagina toe aan het document met behulp van de`Add` methode van de`Pages` verzameling.

#### V: Hoe maak ik een grafiekobject en voeg ik een lijn toe?

 A: In stap 7 maakt u een nieuwe`Graph` object, voeg er een regel aan toe en voeg vervolgens de`Graph` bezwaar maken tegen de`Paragraphs` verzameling van de pagina.

#### V: Hoe voeg ik een koptekst met HTML-opmaak toe?

 A: In stap 8 maakt u een`HtmlFragment` object en stel de inhoud in op de gewenste HTML-tekst, en voeg vervolgens het fragment toe aan de`Paragraphs` verzameling van de pagina.

#### V: Hoe maak ik een FloatingBox met meerdere kolommen?

 A: In stap 9 maak je een`FloatingBox` object met meerdere kolommen en kolomafstand, voeg vervolgens tekstfragmenten en een regel toe aan de`Paragraphs` verzameling van de`FloatingBox`.

#### V: Hoe kan ik het PDF-document opslaan?

 A: In stap 10 slaat u het PDF-document op met behulp van de`Save` methode van de`Document` voorwerp.

#### V: Wat is de belangrijkste les die je uit deze tutorial hebt geleerd?

A: Door deze tutorial te volgen, hebt u geleerd hoe u een PDF-document met meerdere kolommen kunt maken met Aspose.PDF voor .NET. Dit kan handig zijn om inhoud in een gestructureerde en georganiseerde lay-out weer te geven.