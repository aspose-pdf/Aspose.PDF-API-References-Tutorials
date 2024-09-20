---
title: Stijl Tabel Element
linktitle: Stijl Tabel Element
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabelelement in Aspose.PDF voor .NET maakt en opmaakt met stapsgewijze instructies, aangepaste opmaak en PDF/UA-compatibiliteit.
type: docs
weight: 170
url: /nl/net/programming-with-tagged-pdf/style-table-element/
---
## Invoering

In dit artikel duiken we in hoe je een tabelelement maakt en stylet met Aspose.PDF voor .NET. Je leert hoe je een tabel structureert, aangepaste stijlen toepast en de PDF/UA-compliance van je document valideert. Aan het einde van deze tutorial kun je eenvoudig professioneel ogende tabellen in je PDF's maken!

## Vereisten

Voordat u met de tutorial begint, moet u ervoor zorgen dat u over het volgende beschikt:

1. Visual Studio of een vergelijkbare IDE op uw computer geïnstalleerd.
2. .NET Framework of .NET Core SDK voor het uitvoeren van de toepassing.
3.  Aspose.PDF voor .NET-bibliotheek gedownload en gerefereerd in uw project. U kunt de nieuwste versie ophalen van[hier](https://releases.aspose.com/pdf/net/).
4.  Een geldige Aspose-licentie of een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de volledige functionaliteit van de bibliotheek te ontgrendelen.

## Pakketten importeren

Om te beginnen importeert u de benodigde naamruimten in uw project:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Deze naamruimten omvatten de belangrijkste PDF-bewerkingen, getagde inhoud, tabellen en tekstopmaak.

Laten we nu het proces van het maken en stylen van een tabel in Aspose.PDF eens doornemen. We zullen elke sectie in detail doornemen, zodat u het kunt volgen.

## Stap 1: Maak een nieuw PDF-document en stel getagde inhoud in

In deze eerste stap maken we een leeg PDF-document en stellen we de getagde inhoud ervan in.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een nieuw PDF-document maken
Document document = new Document();

// Getagde inhoud instellen
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 We beginnen met het maken van een nieuwe`Document` object, dat onze PDF vertegenwoordigt. De`TaggedContent`object wordt gebruikt om de structuur van het document te beheren, en zo te zorgen voor naleving van toegankelijkheidsnormen. We stellen de titel en taal van het document in voor correcte tagging.

## Stap 2: Definieer het rootelement

Vervolgens maken we het rootstructuurelement, dat fungeert als container voor alle inhoud in onze PDF.

```csharp
// Krijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;
```

 De`RootElement` fungeert als de basiscontainer voor alle gestructureerde elementen, inclusief onze tabel. Het helpt de structurele hiërarchie van het document te behouden, wat belangrijk is voor zowel de organisatie als de toegankelijkheid.

## Stap 3: Het tabelelement maken en stylen

 Nu het rootelement is ingesteld, gaan we een`TableElement` en stijlen zoals achtergrondkleur, randen en uitlijning toepassen.

```csharp
// Maak een tabelstructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Stijl de tafel
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Wij creëren een`TableElement` , die onze tabelstructuur definieert. De`BackgroundColor`, `Border` , En`Alignment` eigenschappen stellen ons in staat om het uiterlijk van de tabel aan te passen.`Broken` Deze eigenschap zorgt ervoor dat als de tabel over meerdere pagina's wordt verdeeld, de tabel verticaal wordt verdeeld.

## Stap 4: Tabelafmetingen en celstijlen instellen

In deze stap definiëren we het aantal kolommen, de celopvulling en andere belangrijke tabeleigenschappen.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 We specificeren de kolombreedtes om ervoor te zorgen dat elke kolom in de tabel gelijkmatig verdeeld is.`DefaultCellBorder`, `DefaultCellPadding` , En`DefaultCellTextState` Definieer de standaardstijlen voor de cellen, inclusief randen, opvulling, tekstkleur en lettergrootte.

## Stap 5: Herhaalde rijen en aangepaste stijlen toevoegen

We kunnen ook stijlen definiëren voor herhalende rijen en andere specifieke tabelelementen, zoals kopteksten en voetteksten.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 De`RepeatingRowsCount` zorgt ervoor dat de eerste drie rijen worden herhaald als de tabel meerdere pagina's beslaat. We stellen de`RepeatingRowsStyle` om een aangepaste achtergrondkleur op deze rijen toe te passen.

## Stap 6: Voeg tafelhoofd-, body- en voetelementen toe

Laten we nu de secties voor de koptekst, hoofdtekst en voettekst van de tabel maken en deze vullen met inhoud.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Koptekstrij maken
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Vul de tabelbody
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 De tabel is verdeeld in drie delen: het hoofd, het lichaam en de voet. We maken eerst de koprij met behulp van`TableTHElement`en voeg kolomkoppen toe. Vervolgens vullen we de body van de tabel met`TableTDElement`, waarbij elke cel wordt gevuld met een label dat de positie ervan aangeeft.

## Stap 7: Sla het document op

Ten slotte slaan we het PDF-document op in de opgegeven map.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableElement.pdf");
```

Met deze stap rondt u het documentcreatieproces af door het PDF-bestand met de opgemaakte tabel op te slaan.

## Stap 8: Valideer PDF/UA-naleving

Nadat u het document hebt opgeslagen, is het belangrijk om te controleren of het voldoet aan de PDF/UA-standaarden (Universal Accessibility).

```csharp
// Controleer PDF/UA-compatibiliteit
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Hier laden we het document opnieuw en valideren het tegen PDF/UA-standaarden. Compliance zorgt ervoor dat uw PDF voldoet aan de toegankelijkheidsvereisten, waardoor het geschikt is voor een breed scala aan gebruikers.

## Conclusie

Met Aspose.PDF voor .NET is het maken en stylen van tabellen in uw PDF-documenten eenvoudig en intuïtief. Door de stappen in deze tutorial te volgen, kunt u tabellen maken met aangepaste stijlen en ervoor zorgen dat uw PDF's voldoen aan toegankelijkheidsnormen. Of u nu rapporten genereert of gestructureerde documenten maakt, tabellen zijn een krachtig hulpmiddel om gegevens duidelijk te presenteren.

## Veelgestelde vragen

### Kan ik afbeeldingen toevoegen in tabelcellen?
 Ja, u kunt afbeeldingen in tabelcellen invoegen met behulp van de`Image` element.

### Hoe pas ik de kolombreedtes dynamisch aan?
 U kunt de`ColumnAdjustment` eigendom van`AutoFitToWindow` om de kolombreedte automatisch aan te passen op basis van de inhoud.

### Is PDF/UA-compliance verplicht voor alle documenten?
Hoewel het niet verplicht is, wordt het aanbevolen voor documenten die hoge toegankelijkheidsnormen vereisen.

### Kan ik verschillende stijlen op specifieke rijen toepassen?
 Ja, u kunt individuele rijen of cellen aanpassen door hun`TextState` of`BackgroundColor`.

### Wat is het voordeel van het gebruik van getagde inhoud?
Gelabelde inhoud verbetert de toegankelijkheid van documenten en draagt bij aan de naleving van standaarden zoals PDF/UA.