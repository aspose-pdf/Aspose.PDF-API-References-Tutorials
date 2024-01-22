---
title: SVG-object toevoegen aan PDF-bestand
linktitle: SVG-object toevoegen aan PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig SVG-objecten toe aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-tables/add-svg-object/
---
In deze zelfstudie leren we hoe u een SVG-object aan een PDF-bestand kunt toevoegen met behulp van de Aspose.PDF voor .NET-bibliotheek. SVG (Scalable Vector Graphics) is een populair formaat voor vectorafbeeldingen die eenvoudig kunnen worden geschaald zonder kwaliteitsverlies. Met Aspose.PDF kunt u programmatisch SVG-objecten aan uw PDF-documenten toevoegen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

- Visual Studio geïnstalleerd
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd

## Stap 1: Stel de omgeving in

Laten we eerst de omgeving instellen door een nieuw C#-project in Visual Studio te maken. Open Visual Studio en volg deze stappen:

1. Klik op "Bestand" > "Nieuw" > "Project" om een nieuw project aan te maken.
2. Selecteer de sjabloon 'Console-app (.NET Framework)' of 'Console-app (.NET Core)', afhankelijk van uw configuratie.
3. Kies een geschikte naam en locatie voor uw project en klik vervolgens op 'Maken'.

## Stap 2: Maak document- en afbeeldingsobjecten

In deze stap maken we de benodigde objecten voor ons PDF-document en SVG-afbeelding. Open het C#-bestand van uw project en voeg de volgende code toe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document-object
Document doc = new Document();
// Maak een afbeeldingsinstantie
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Stap 3: Stel afbeeldingseigenschappen in

Vervolgens zullen we de eigenschappen voor onze SVG-afbeelding instellen. We specificeren het bestandstype SVG, het pad naar het SVG-bestand en de afmetingen van de afbeelding. Voeg de volgende code toe na de vorige stap:

```csharp
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pad voor bronbestand
img.File = dataDir + "SVGToPDF.svg";
// Stel de breedte in voor de afbeeldingsinstantie
img. FixWidth = 50;
// Stel de hoogte in voor de afbeeldingsinstantie
img.FixHeight = 50;
```

## Stap 4: Maak en configureer de tabel

Laten we nu een tabelobject maken en de kolombreedtes instellen. We gaan een tabel maken met twee kolommen, elk met een breedte van 100 eenheden. Voeg de volgende code toe:

```csharp
// Maak een exemplaartabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breedte voor tabelcellen instellen
table. ColumnWidths = "100 100";
```

## Stap 5: Voeg cellen toe aan de tabel

In deze stap voegen we een rij en cellen toe aan de tabel. Elke rij vertegenwoordigt een horizontale rij in de tabel en cellen worden aan de rijen toegevoegd. Voeg de volgende code toe:

```csharp
//Maak een rijobject en voeg het toe aan de tabelinstantie
Aspose.Pdf.Row row = table.Rows.Add();
// Maak een celobject en voeg het toe aan de rijinstantie
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Stap 6: voeg tekst en afbeelding toe aan cellen

Laten we vervolgens tekst en de SVG-afbeelding toevoegen aan de cellen van de tabel. We voegen de tekst "Eerste cel" toe aan de eerste cel en de SVG-afbeelding aan de tweede cel. Voeg de volgende code toe:

```csharp
// Voeg een tekstfragment toe aan de alineaverzameling van het celobject
cell.Paragraphs.Add(new TextFragment("First cell"));
// Voeg nog een cel toe aan het rijobject
cell = row. Cells. Add();
// Voeg een SVG-afbeelding toe aan de alineaverzameling van recent toegevoegde celinstantie
cell.Paragraphs.Add(img);
```

## Stap 7: Maak een pagina aan en voeg deze toe aan het document

Laten we nu een paginaobject maken en dit aan het document toevoegen. De tabel wordt toegevoegd aan de alineacollectie van de pagina. Voeg de volgende code toe:

```csharp
// Maak een paginaobject en voeg het toe aan de paginaverzameling van de documentinstantie
Page page = doc.Pages.Add();
// Tabel toevoegen aan alineaverzameling van paginaobject
page.Paragraphs.Add(table);
```

## Stap 8: Sla het PDF-bestand op

Ten slotte slaan we het PDF-bestand op de opgegeven locatie op. Voeg de volgende code toe:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor het toevoegen van een SVG-object met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een documentobject
Document doc = new Document();
// Maak een afbeeldingsinstantie
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pad voor bronbestand
img.File = dataDir + "SVGToPDF.svg";
// Stel de breedte in voor de afbeeldingsinstantie
img.FixWidth = 50;
// Stel de hoogte in voor de afbeeldingsinstantie
img.FixHeight = 50;
// Tabelinstantie maken
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breedte voor tabelcellen instellen
table.ColumnWidths = "100 100";
//Maak een rijobject en voeg het toe aan de tabelinstantie
Aspose.Pdf.Row row = table.Rows.Add();
// Maak een celobject en voeg het toe aan de rijinstantie
Aspose.Pdf.Cell cell = row.Cells.Add();
// Voeg een tekstfragment toe aan de alineaverzameling van het celobject
cell.Paragraphs.Add(new TextFragment("First cell"));
// Voeg nog een cel toe aan het rijobject
cell = row.Cells.Add();
// Voeg een SVG-afbeelding toe aan de alineaverzameling van recent toegevoegde celinstantie
cell.Paragraphs.Add(img);
// Maak een paginaobject en voeg het toe aan de paginaverzameling van de documentinstantie
Page page = doc.Pages.Add();
// Tabel toevoegen aan alineaverzameling van paginaobject
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een SVG-object aan een PDF-bestand kunt toevoegen met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het stapsgewijze proces besproken van het maken van een document, het instellen van de omgeving, het toevoegen van een SVG-afbeelding aan een tabelcel en het opslaan van het PDF-bestand. Nu kunt u SVG-objecten programmatisch in uw PDF-documenten opnemen.

### Veelgestelde vragen over het toevoegen van SVG-objecten aan PDF-bestanden

#### Vraag: Kan ik meerdere SVG-objecten aan het PDF-document toevoegen?

 A: Ja, u kunt meerdere SVG-objecten aan het PDF-document toevoegen. Maak en configureer eenvoudig extra`Aspose.Pdf.Image` exemplaren voor elke SVG-afbeelding die u wilt toevoegen en voeg deze vervolgens toe aan de gewenste tabelcellen of alinea's in het PDF-document.

#### Vraag: Hoe kan ik de grootte en positie van de SVG-afbeelding in de tabelcel aanpassen?

 A: Om de grootte en positie van de SVG-afbeelding in de tabelcel aan te passen, kunt u de`FixWidth` En`FixHeight` eigenschappen van de`Aspose.Pdf.Image`voorbeeld. U kunt ook andere eigenschappen gebruiken, zoals`HorizontalAlignment` En`VerticalAlignment` van de tabelcel om de positionering te regelen.

#### Vraag: Is het mogelijk om tekst toe te voegen naast de SVG-afbeelding in dezelfde tabelcel?

 A: Ja, het is mogelijk om tekst toe te voegen naast de SVG-afbeelding in dezelfde tabelcel. U kunt gebruik maken van de`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` methode om tekst aan de cel toe te voegen samen met de SVG-afbeelding.

#### Vraag: Kan ik hyperlinks toevoegen aan de SVG-afbeelding?

 A: Ja, u kunt hyperlinks toevoegen aan de SVG-afbeelding met behulp van de`Hyperlink` eigendom van de`Aspose.Pdf.Image` voorbeeld. Stel de hyperlink-URL of actie in om de afbeelding klikbaar te maken.

#### Vraag: Is Aspose.PDF voor .NET compatibel met .NET Core 3.1 of latere versies?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET Core 3.1 en latere versies. U kunt het gebruiken in zowel .NET Framework- als .NET Core-toepassingen.