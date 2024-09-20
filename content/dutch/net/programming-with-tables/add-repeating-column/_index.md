---
title: Herhalende kolom toevoegen in PDF-document
linktitle: Herhalende kolom toevoegen in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u herhalende kolommen toevoegt aan PDF-documenten met Aspose.PDF voor .NET. Stapsgewijze handleiding met voorbeelden en code. Perfect voor ontwikkelaars.
type: docs
weight: 20
url: /nl/net/programming-with-tables/add-repeating-column/
---
## Invoering

Als u met PDF-documenten werkt en herhalende kolommen wilt toevoegen, bent u hier aan het juiste adres! Met Aspose.PDF voor .NET kunt u eenvoudig tabellen en inhoud in een PDF beheren. Of u nu dynamische rapporten, facturen of een ander gestructureerd document maakt, herhalende kolommen kunnen een game-changer zijn bij het organiseren van gegevens. Laten we eens kijken naar een stapsgewijze handleiding over het toevoegen van herhalende kolommen aan een PDF-document.

## Vereisten

Voordat we met de code beginnen, controleren we of alles is ingesteld:

- Aspose.PDF voor .NET: De Aspose.PDF voor .NET-bibliotheek moet in uw project zijn geïnstalleerd.
- [Download Aspose.PDF voor .NET](https://releases.aspose.com/pdf/net/)
- [Gratis proefperiode](https://releases.aspose.com/)
- Ontwikkelomgeving: Zorg ervoor dat u een .NET-compatibele IDE zoals Visual Studio hebt geïnstalleerd.
- Basiskennis van C#: Hoewel we alles zullen uitleggen, is een basiskennis van C# voldoende om de cursus soepel te kunnen volgen.
  
 Als u Aspose.PDF voor .NET nog niet hebt, kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de functies ervan te gaan verkennen.

## Pakketten importeren

Om te beginnen moet u de benodigde naamruimten importeren uit Aspose.PDF voor .NET. Dit is hoe u dat doet:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Deze pakketten bieden de essentiële klassen en methoden die nodig zijn om met PDF-documenten te werken en tabellen te bewerken.

Laten we het proces nu opsplitsen in meerdere stappen om herhalende kolommen toe te voegen aan een PDF-document. Volg mee!

## Stap 1: Stel het pad naar uw documentenmap in

Voordat we bestanden maken of bewerken, moeten we het pad definiëren waar de gegenereerde PDF wordt opgeslagen. Stel in uw C#-project het directorypad in waar uw bestanden worden opgeslagen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Dit pad verwijst naar de map waar de uitvoer-PDF wordt opgeslagen. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het werkelijke pad op uw machine.

## Stap 2: Maak een nieuw PDF-document

 Om te beginnen, instantiëren van een nieuwe`Document` object. Dit zal dienen als de container voor alle pagina's en inhoud in de PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Hier hebben we een nieuw PDF-document gemaakt en er een lege pagina aan toegevoegd.`doc.Pages.Add()` methode voegt een nieuwe pagina in het document in.

## Stap 3: Instantieer de buitenste tabel

Vervolgens maken we een outer table. Deze tabel zal de gehele breedte van de pagina beslaan en dienen als een container voor andere tabellen, inclusief degene die de herhalende kolommen zal bevatten.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 We hebben de`ColumnWidths` eigenschap op "100%" zetten, wat betekent dat de tabel zich over de gehele paginabreedte uitstrekt.

## Stap 4: Maak de binnenste tabel

 Laten we nu de binnenste tabel maken, die herhalende kolommen zal hebben. De belangrijkste eigenschappen hier zijn`Broken` , waardoor de tabel op dezelfde pagina kan worden voortgezet, en`ColumnAdjustment`, die automatisch de kolombreedtes aanpast aan de inhoud.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Deze binnenste tabel wordt genest in de buitenste tabel.

## Stap 5: Tabellen toevoegen aan de pagina

Nu we zowel de outer als inner tabellen gereed hebben, voegen we ze toe aan de pagina. Deze stap zorgt ervoor dat de tabellen worden opgenomen in de structuur van het document.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Hier hebben we de`outerTable` naar de pagina, en vervolgens hebben we binnen de buitenste tabel de`mytable` . Bovendien stellen we`RepeatingColumnsCount`tot 5, om aan te geven hoeveel kolommen herhaald moeten worden wanneer er gegevens worden toegevoegd.

## Stap 6: Koptekstrij toevoegen

Nu is het tijd om de headers aan de tabel toe te voegen. De headerrij geeft context aan de data en helpt bij het structureren van de kolommen. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Met dit codefragment wordt de eerste rij (die we als kopteksten gebruiken) toegevoegd en worden cellen gevuld met tekst zoals 'koptekst 1', 'koptekst 2', enzovoort.

## Stap 7: Gegevensrijen toevoegen

Ten slotte kunnen we wat data aan de tabel toevoegen. Deze lus creëert dynamisch rijen en vult de cellen met content:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

De lus wordt zes keer herhaald, waarbij rijen worden toegevoegd en elke cel wordt gevuld met bijbehorende kolomgegevens (bijvoorbeeld 'kolom 1, 1', 'kolom 2, 2', enz.).

## Stap 8: Sla het document op

Zodra alle rijen en kolommen zijn toegevoegd, is de laatste stap het opslaan van het document in het opgegeven bestandspad.

```csharp
doc.Save(outFile);
```

Uw document is nu opgeslagen met herhalende kolommen!

## Conclusie

Daar heb je het! Met deze eenvoudige stappen kun je een PDF-document maken met herhalende kolommen met Aspose.PDF voor .NET. Door de flexibiliteit van geneste tabellen te benutten, kun je complexe lay-outs bereiken die je PDF's er professioneel en georganiseerd uit laten zien. Probeer dit uit voor je volgende project en ontdek het volledige potentieel van Aspose.PDF om je PDF-generatiebehoeften te verwerken.

## Veelgestelde vragen

### Wat is Aspose.PDF voor .NET?
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch PDF-documenten kunnen maken, bewerken en beheren.

### Kan ik het aantal herhalende kolommen dynamisch aanpassen?
 Ja, u kunt het aantal herhalende kolommen wijzigen door de`RepeatingColumnsCount` eigendom.

### Hoe kan ik een licentie aanvragen voor Aspose.PDF voor .NET?
 U kunt een licentie van een bestand of stream toepassen door de volgende stappen te volgen:[documentatie](https://reference.aspose.com/pdf/net/).

### Is het mogelijk om afbeeldingen aan de tabelcellen toe te voegen?
Ja, Aspose.PDF voor .NET ondersteunt het toevoegen van verschillende soorten inhoud, waaronder afbeeldingen, aan tabelcellen.

### Kan ik de tabelindeling verder aanpassen?
Absoluut! Aspose.PDF biedt uitgebreide functies voor het aanpassen van tabelstijlen, waaronder randen, opvulling, uitlijning en meer.