---
title: Stijl tabelrij
linktitle: Stijl tabelrij
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelrijen in een PDF kunt opmaken met Aspose.PDF voor .NET. De handleiding helpt u om de opmaak van uw document eenvoudig te verbeteren.
type: docs
weight: 180
url: /nl/net/programming-with-tagged-pdf/style-table-row/
---
## Invoering

Als het aankomt op het maken van goed gestructureerde en prachtig opgemaakte PDF-documenten, is Aspose.PDF voor .NET een go-to-oplossing. Of u nu rapporten, facturen of dynamische tabellen automatiseert, het opmaken van tabellen met verschillende stijlen is de sleutel tot een gepolijst document. In deze tutorial duiken we diep in het stylen van een tabelrij met Aspose.PDF voor .NET. En maak je geen zorgen, ik begeleid je stap voor stap, net als een goed gesprek bij een kopje koffie!

## Vereisten

Voordat we in de details duiken, zorgen we ervoor dat je alles op een rijtje hebt. Je hebt nodig:

1. Aspose.PDF voor .NET-bibliotheek  
    Als je het nog niet hebt, kun je het hier downloaden[hier](https://releases.aspose.com/pdf/net/) . Je kunt ook een[gratis proefperiode](https://releases.aspose.com/) om te beginnen.
2. Ontwikkelomgeving  
   Installeer Visual Studio of een andere C# IDE naar keuze. Je hebt ook .NET nodig, maar ik gok dat je daar al bekend mee bent.
3. Basiskennis van C# en .NET  
   Een goed begrip van C# maakt deze tutorial een fluitje van een cent. Maar maak je geen zorgen, ik zal elke stap in detail uitleggen!

## Pakketten importeren

Voordat we kunnen beginnen met Aspose.PDF, moeten we de benodigde namespaces importeren. Zorg ervoor dat u het volgende in uw C#-project opneemt:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Deze zijn essentieel voor het maken en stylen van de tabel en natuurlijk voor het werken met getagde inhoud om aan de regels te voldoen.

Laten we de taak nu stap voor stap doornemen, zodat u uw tabelrijen als een professional kunt opmaken!

## Stap 1: Maak een nieuw PDF-document

Eerst even het belangrijkste: laten we een gloednieuw PDF-document maken. Dit document zal alle gestileerde tabelrijen bevatten.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
```

 Hier initialiseren we eenvoudigweg een nieuwe`Document` object dat ons PDF-bestand zal vertegenwoordigen. Zorg ervoor dat u het directorypad instelt waar u uw uitvoerbestanden opslaat.

## Stap 2: Werk met getagde inhoud

Om uw PDF te structureren voor toegankelijkheid, werken we met getagde content. Dit helpt bij het maken van gestructureerde elementen zoals tabellen, zodat ze voldoen aan toegankelijkheidsnormen zoals PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Hier stellen we de titel en taal in voor de getagde content van de PDF. Het is alsof je je PDF een naam geeft en vertelt welke taal hij moet spreken!

## Stap 3: Definieer de tabelstructuur

Laten we nu de structuur definiëren van de tabel die we gaan maken. Elke tabel heeft een header, body en footer nodig – net als een goed georganiseerde blogpost!

```csharp
// Krijg wortelstructuur element
StructureElement rootElement = taggedContent.RootElement;

// Maak een tabelstructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Wat we hier doen is een tabel maken met een koptekst (`THead`), lichaam (`TBody`), en voettekst (`TFoot`). Deze elementen gaan onze rijen vasthouden.

## Stap 4: Voeg de tabelkoprij toe

Tabellen zonder headers zijn als boeken zonder titels. Laten we eerst de headerrij maken om context te bieden voor de data.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Hier doorlopen we de drie headercellen en voegen deze toe (`TableTHElement`), en geef ze elk een beschrijvende tekst. Simpel, toch?

## Stap 5: Voeg gestileerde bodyrijen toe

Nu komt het leuke gedeelte: de rijen stylen! Laten we zeven rijen maken met aangepaste stijlen. We stellen achtergrondkleuren, randen, opvulling en tekstuitlijning in.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Achtergrondkleur: We hebben een lichtgouden geel gebruikt voor een professionele en toch warme uitstraling.
- Randen: Elke rij krijgt een donkergrijze buitenrand en blauwe celranden voor een strakke uitstraling.
- Hoogte en opvulling: De rijhoogtes worden ingesteld en er wordt opvulling toegevoegd voor een overzichtelijk uiterlijk.
- Pagina-einden: Om de tabel leesbaarder te maken, begint elke tweede rij op een nieuwe pagina.

## Stap 6: Voeg de voettekstrij toe

Net als de header, verankert de footer de tabel. Laten we er een maken.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

We loopen gewoon door drie footercellen en voegen een stukje tekst toe. De alternatieve tekst voor de footer is "Foot Row" om het toegankelijk te maken.

## Stap 7: Sla het PDF-document op

Nu de tafel helemaal gedekt is, is het tijd om je meesterwerk op te slaan!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Zo wordt uw PDF opgeslagen met alle mooie tabelrijen die we zojuist hebben opgemaakt.

## Stap 8: Valideer PDF/UA-naleving

Om ervoor te zorgen dat onze PDF voldoet aan de toegankelijkheidsnormen, valideren we deze op PDF/UA-compliance.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Dit zorgt ervoor dat uw PDF voldoet aan de PDF/UA-standaard, waardoor deze voor iedereen toegankelijk is. Toegankelijkheid is de naam van het spel!

## Conclusie

En daar heb je het! Met slechts een paar regels code heb je een volledig gestyleerde tabel in een PDF gemaakt met Aspose.PDF voor .NET. Van kopteksten tot voetteksten, we hebben elke rij gestyled, toegankelijkheidselementen toegevoegd en zelfs het document gevalideerd op naleving. Of je nu werkt aan bedrijfsrapporten, presentaties of gewoon plezier hebt met PDF's, deze gids heeft alles voor je. Ga nu aan de slag en begin met het stylen van je tabellen als een pro!

## Veelgestelde vragen

### Kan ik ook het lettertype van de tabel wijzigen?  
 Ja! U kunt het lettertype wijzigen met behulp van de`TextState` object voor elke cel, waardoor volledige aanpassing mogelijk is.

### Hoe voeg ik meer kolommen toe aan mijn tabel?  
 Pas gewoon de`colCount`variabele en voeg meer cellen toe aan de lussen voor kopteksten, hoofdtekst en voetteksten.

### Wat gebeurt er als ik de rijhoogte niet instel?  
Als u de rijhoogte niet instelt, wordt de tabel automatisch aangepast op basis van de inhoud.

### Kan ik dit gebruiken voor een dynamisch aantal rijen?  
Absoluut! U kunt gegevens ophalen uit een database of een andere bron en dynamisch de rij- en kolomaantallen aanpassen.

### Is Aspose.PDF voor .NET gratis te gebruiken?  
 Aspose.PDF voor .NET is een gelicentieerd product, maar u kunt het uitproberen met een[gratis proefperiode](https://releases.aspose.com/) of krijg een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/).