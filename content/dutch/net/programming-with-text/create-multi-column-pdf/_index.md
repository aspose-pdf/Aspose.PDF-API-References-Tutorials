---
title: Maak een PDF met meerdere kolommen
linktitle: Maak een PDF met meerdere kolommen
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u PDF's met meerdere kolommen maakt met Aspose.PDF voor .NET. Een stapsgewijze handleiding met codevoorbeelden en gedetailleerde uitleg. Perfect voor professionals.
type: docs
weight: 110
url: /nl/net/programming-with-text/create-multi-column-pdf/
---
## Invoering

Het maken van PDF's met meerdere kolommen is een geweldige manier om tekst in een meer georganiseerde, leesbare vorm te presenteren. Of u nu een rapport, artikel of lay-out voor een publicatie maakt, structuren met meerdere kolommen kunnen uw content aantrekkelijker maken. In deze tutorial laten we u zien hoe u een PDF met meerdere kolommen maakt met Aspose.PDF voor .NET. Maak u geen zorgen, we splitsen alles op in eenvoudige stappen die het gemakkelijk te volgen maken, zelfs als u nieuw bent op het platform.

## Vereisten

Voordat we met de code beginnen, zijn er een paar dingen die je nodig hebt om het proces soepel te kunnen volgen:

1.  Aspose.PDF voor .NET: Deze bibliotheek moet geïnstalleerd zijn. U kunt deze downloaden van[hier](https://releases.aspose.com/pdf/net/).
2. Ontwikkelomgeving: Stel uw favoriete IDE in, zoals Visual Studio, voor het schrijven en uitvoeren van C#-code.
3. .NET Framework: Zorg ervoor dat u een compatibele versie van .NET hebt geïnstalleerd.
4. Basiskennis van C#: Kennis van de C#-syntaxis is nuttig, maar we leggen elke stap gedetailleerd uit.
5.  Tijdelijke licentie: Aspose.PDF vereist een licentie om watermerken of beperkingen te vermijden. U kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) indien nodig.

## Pakketten importeren

Voordat u begint met coderen, moet u de benodigde naamruimten importeren die u in staat stellen om te interacteren met Aspose.PDF. Dit is wat u moet importeren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Deze naamruimten bieden toegang tot klassen die nodig zijn voor het maken van PDF's, het tekenen van vormen en het verwerken van tekstopmaak.

Laten we het proces voor het maken van een PDF met meerdere kolommen opsplitsen in eenvoudige, beheersbare stappen.

## Stap 1: Het document instellen

Om te beginnen moet u een nieuw PDF-document maken. Dit houdt in dat u de marges definieert en een pagina toevoegt waar uw content komt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een nieuw PDF-document maken
Document doc = new Document();

// Stel de marges voor het PDF-bestand in
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Een pagina toevoegen aan het document
Page page = doc.Pages.Add();
```

 Hier hebben we een gemaakt`Document`object en stel de linker- en rechtermarges in op 40 eenheden. Vervolgens hebben we een nieuwe pagina aan dit document toegevoegd, die onze multi-kolom lay-out zal bevatten.

## Stap 2: Een regel toevoegen om secties te scheiden

Voeg vervolgens een horizontale lijn toe aan de pagina voor visuele scheiding. Dit helpt om een schone en professionele look te creëren.

```csharp
// Maak een grafiekobject om de lijn vast te houden
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Voeg de regel toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(graph1);

// Definieer de coördinaten voor de lijn
float[] posArr = new float[] { 1, 2, 500, 2 };

// Maak een lijn en voeg deze toe aan de grafiek
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 Hier maken we een horizontale lijn met behulp van de`Graph` En`Line` klassen. Deze regel wordt toegevoegd aan de pagina's`Paragraphs` collectie, die alle visuele elementen bevat.

## Stap 3: HTML-tekst met opmaak toevoegen

Laten we nu wat tekst invoegen die HTML-tags bevat om te laten zien hoe u tekst dynamisch kunt opmaken in de PDF.

```csharp
// Maak een string met HTML-inhoud
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Maak een nieuw HtmlFragment met de opgemaakte tekst
HtmlFragment heading_text = new HtmlFragment(s);

// Voeg de HTML-tekst toe aan de pagina
page.Paragraphs.Add(heading_text);
```

 Met behulp van de`HtmlFragment`klasse, kunnen we geformatteerde tekst toevoegen die HTML-tags bevat, zoals lettergrootte, stijl en vetgedrukte tekst. Dit is handig om het uiterlijk van uw PDF-inhoud te verbeteren.

## Stap 4: Een lay-out met meerdere kolommen maken

Nu gaan we een multi-kolom lay-out maken. Dit is waar de magie gebeurt — u kunt specificeren hoeveel kolommen u wilt en hoe breed ze moeten zijn.

```csharp
// Maak een zwevende doos om de kolommen vast te houden
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Stel het aantal kolommen en de afstand ertussen in
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Voeg het vak toe aan de pagina
page.Paragraphs.Add(box);
```

Hier maken we een zwevende box die twee kolommen zal bevatten. We stellen de afstand tussen de kolommen in en specificeren dat elke kolom 105 eenheden breed moet zijn. Dit stelt ons in staat om de gewenste kolomindeling binnen de PDF te maken.

## Stap 5: Tekst toevoegen aan de kolommen

 Laten we nu de kolommen vullen met wat tekstinhoud. U kunt verschillende`TextFragment` objecten aan elke kolom toe.

```csharp
// Maak en formatteer het eerste tekstfragment
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Voeg een extra regel toe voor scheiding
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//Maak en voeg een tweede tekstfragment toe
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 Wij voegen een toe`TextFragment` naar de zwevende doos, gevolgd door een andere horizontale lijn. De tweede`TextFragment` bevat meer tekst om de tweede kolom te vullen. Deze fragmenten stellen ons in staat om verschillende tekstelementen aan de PDF toe te voegen met verschillende opmaakopties.

## Stap 6: De PDF opslaan

Nadat u alle inhoud hebt toegevoegd, slaat u het document als PDF-bestand op.

```csharp
// Definieer het uitvoerpad voor de PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Sla het PDF-document op
doc.Save(dataDir);

// Bericht over succes bij uitvoer
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

Dit blok slaat het PDF-bestand op in de opgegeven directory en geeft een succesbericht in de console. De PDF is nu klaar om te bekijken!

## Conclusie

Door deze eenvoudige stappen te volgen, kunt u eenvoudig een professioneel ogende PDF met meerdere kolommen maken met Aspose.PDF voor .NET. Of het nu voor een rapport, artikel of nieuwsbrief is, deze techniek helpt u inhoud te organiseren in een visueel aantrekkelijk formaat. Aspose.PDF biedt krachtige tools voor het aanpassen van uw PDF's, van marges en lay-out tot tekstopmaak en het tekenen van vormen. Nu is het uw beurt om het uit te proberen en uw vaardigheden in het maken van PDF's naar een hoger niveau te tillen!

## Veelgestelde vragen

### Kan ik meer dan twee kolommen in een PDF maken?
 Ja, u kunt zoveel kolommen maken als u nodig hebt. Pas gewoon de`ColumnCount` eigenschap om het aantal kolommen te matchen dat u wilt.

### Hoe wijzig ik de breedte van elke kolom?
 U kunt de`ColumnWidths` eigenschap om verschillende breedtes voor elke kolom te specificeren. Deze eigenschap accepteert een string met waarden gescheiden door spaties.

### Is het mogelijk om afbeeldingen aan de kolommen toe te voegen?
 Absoluut! U kunt afbeeldingen toevoegen met behulp van de`Image` klasse en neem ze op in het zwevende vak of een ander lay-outelement in uw PDF.

### Kan ik tekst opmaken met HTML-tags in de kolommen?
 Ja, u kunt HTML-tags gebruiken binnen`HtmlFragment` objecten om uw tekst te stylen. Dit omvat het toevoegen van lettertypen, groottes, kleuren en meer.

### Hoe kan ik meer pagina's toevoegen met dezelfde kolomindeling?
 U kunt extra pagina's toevoegen met behulp van`doc.Pages.Add()` en herhaal het proces van het toevoegen van kolommen en inhoud voor elke pagina.