---
title: Stijl tabelcel
linktitle: Stijl tabelcel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelcellen in een PDF kunt stylen met Aspose.PDF voor .NET met deze gedetailleerde tutorial. Volg de instructies om prachtige PDF-tabellen te maken en op te maken.
type: docs
weight: 160
url: /nl/net/programming-with-tagged-pdf/style-table-cell/
---
## Invoering

Het maken van professioneel ogende PDF-tabellen kan lastig zijn, maar met Aspose.PDF voor .NET is het verrassend eenvoudig! Of u nu kopteksten, voetteksten of specifieke tabelcellen wilt stylen, deze krachtige bibliotheek biedt u alle tools die u nodig hebt om prachtig opgemaakte PDF-documenten te maken. In deze tutorial laten we u zien hoe u tabelcellen in een PDF-document kunt stylen met Aspose.PDF voor .NET. Maak u geen zorgen, we splitsen alles op in eenvoudig te volgen stappen.

## Vereisten

Voordat u aan de slag gaat met de code, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Aspose.PDF voor .NET: Download en installeer de nieuwste versie van Aspose.PDF van[hier](https://releases.aspose.com/pdf/net/).
2. IDE (zoals Visual Studio): Stel een .NET-ontwikkelomgeving in.
3. Basiskennis van C#-programmering: Een beetje vertrouwdheid met C# is vereist.
4.  Aspose.PDF Licentie: Verkrijg een tijdelijke of volledige licentie om de volledige functies van de bibliotheek te ontgrendelen. U kunt een gratis proefversie krijgen[hier](https://purchase.aspose.com/temporary-license/).

## Pakketten importeren

Zorg ervoor dat u de benodigde namespaces importeert voordat u begint. U hebt het volgende nodig in uw project:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nu alles is ingesteld, gaan we verder met de stapsgewijze handleiding!

We gaan een tabel maken in een PDF-document en de cellen ervan stylen. Elke stap zal het proces in detail uitleggen.

## Stap 1: Maak een nieuw PDF-document

 De eerste stap is het maken van een nieuw PDF-document. In Aspose.PDF kunt u een nieuw`Document` object, dat uw PDF-bestand vertegenwoordigt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een nieuw PDF-document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Hier initialiseren we een PDF-document en stellen de titel en taal in. Dit geeft uw document een goede structuur, wat essentieel is voor PDF/UA-compliance.

## Stap 2: De tabelstructuur instellen

Tabellen in PDF's worden gedefinieerd binnen structuurelementen. Laten we de tabel maken en de rijen en kolommen van de tabel definiëren.

```csharp
// Krijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;

// Een tabelstructuurelement maken
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

We hebben nu de kop van de tabel gedefinieerd (`TableTHeadElement`), lichaam (`TableTBodyElement`), en voet (`TableTFootElement`) secties. U kunt deze zien als het skelet van uw tabel.

## Stap 3: Stijl de koptekstcellen

Door de headercellen te stylen, vallen ze op. Hier passen we achtergrondkleuren, randen en tekstuitlijning toe.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

In deze stap doorlopen we elke headercel, waarbij we deze een groen-gele achtergrond, een grijze rand en een rechts uitgelijnde tekst geven. U kunt deze eigenschappen aanpassen aan uw gewenste ontwerp.

## Stap 4: Vul en style de tabelbody

De tabelbody bevat de werkelijke gegevens. Hier ziet u hoe u elke cel kunt stylen met specifieke marges, randen en tekstinstellingen.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 In deze stap vullen we de tabelbody met vier rijen en stylen we elke cel met gele achtergronden en gecentreerde, vette blauwe tekst. We gebruiken ook de`MarginInfo`klasse om de opvulling rond de tekst te definiëren.

## Stap 5: Stijl de voettekst

Om de tabel een complete structuur te geven, voegen we voettekstcellen toe en geven we deze de gewenste stijl, net zoals we dat met de koptekst hebben gedaan.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

De voettekst heeft een vergelijkbare opmaak als de koptekst, waardoor lezers de structuur van de tabel gemakkelijk kunnen volgen.

## Stap 6: Sla het PDF-document op en valideer het

Ten slotte slaan we het PDF-document op en controleren of het PDF/UA-compatibel is.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableCell.pdf");

// Controleren van PDF/UA-compatibiliteit
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 We slaan de PDF op en gebruiken de`Validate` methode om te garanderen dat het voldoet aan de toegankelijkheidsnormen (PDF/UA-naleving).

## Conclusie

Het stylen van tabellen in een PDF met Aspose.PDF voor .NET is zowel krachtig als flexibel. Met een paar regels code kunt u aangepaste tabelontwerpen maken die uw PDF-documenten laten opvallen. Van het aanpassen van celranden en achtergronden tot het garanderen van toegankelijkheidsnaleving, Aspose.PDF maakt het eenvoudig om gepolijste PDF-bestanden te maken.

## Veelgestelde vragen

### Kan ik verschillende stijlen toepassen op afzonderlijke tabelcellen?  
Ja, u kunt individuele cellen stylen door de`TableTDElement` eigenschappen.

### Hoe kan ik tabelcellen samenvoegen?  
 U kunt de`ColSpan` En`RowSpan` Eigenschappen om cellen in een tabel samen te voegen.

### Is het mogelijk om een PDF/UA-compatibele tabel te maken?  
 Ja, zoals in deze handleiding wordt aangetoond, kunt u PDF/UA-naleving garanderen door uw document te valideren met behulp van de`Validate` methode.

### Kan ik verschillende lettertypen gebruiken in de tabelcellen?  
 Absoluut! U kunt verschillende lettertypen opgeven met behulp van de`TextState` object voor elke cel.

### Hoe download ik Aspose.PDF voor .NET?  
 Je kunt het downloaden van de[releases pagina](https://releases.aspose.com/pdf/net/).