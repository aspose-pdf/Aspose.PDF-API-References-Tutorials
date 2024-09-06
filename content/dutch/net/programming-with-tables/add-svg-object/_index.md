---
title: SVG-object toevoegen in PDF-bestand
linktitle: SVG-object toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig SVG-objecten toe aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-tables/add-svg-object/
---
In deze tutorial leren we hoe u een SVG-object toevoegt aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. SVG (Scalable Vector Graphics) is een populair formaat voor vectorafbeeldingen dat eenvoudig kan worden geschaald zonder kwaliteitsverlies. Met Aspose.PDF kunt u SVG-objecten programmatisch toevoegen aan uw PDF-documenten.

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

- Visual Studio geïnstalleerd
- Aspose.PDF voor .NET-bibliotheek geïnstalleerd

## Stap 1: De omgeving instellen

Laten we eerst de omgeving instellen door een nieuw C#-project in Visual Studio te maken. Open Visual Studio en volg deze stappen:

1. Klik op "Bestand" > "Nieuw" > "Project" om een nieuw project te maken.
2. Selecteer de sjabloon 'Console App (.NET Framework)' of 'Console App (.NET Core)', afhankelijk van uw configuratie.
3. Kies een geschikte naam en locatie voor uw project en klik op 'Maken'.

## Stap 2: Document- en afbeeldingsobjecten maken

In deze stap maken we de benodigde objecten voor ons PDF-document en SVG-afbeelding. Open het C#-bestand van uw project en voeg de volgende code toe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document-object
Document doc = new Document();
// Een afbeeldinginstantie maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Stap 3: Stel de eigenschappen van de afbeelding in

Vervolgens stellen we de eigenschappen voor onze SVG-afbeelding in. We specificeren het bestandstype als SVG, het pad naar het SVG-bestand en de afmetingen van de afbeelding. Voeg de volgende code toe na de vorige stap:

```csharp
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pad voor bronbestand
img.File = dataDir + "SVGToPDF.svg";
// Breedte instellen voor afbeeldinginstantie
img. FixWidth = 50;
// Hoogte instellen voor afbeeldinginstantie
img.FixHeight = 50;
```

## Stap 4: De tabel maken en configureren

Laten we nu een tabelobject maken en de kolombreedtes instellen. We maken een tabel met twee kolommen, elk met een breedte van 100 eenheden. Voeg de volgende code toe:

```csharp
// Instantietabel maken
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breedte instellen voor tabelcellen
table. ColumnWidths = "100 100";
```

## Stap 5: Cellen toevoegen aan de tabel

In deze stap voegen we een rij en cellen toe aan de tabel. Elke rij vertegenwoordigt een horizontale rij in de tabel en cellen worden toegevoegd aan de rijen. Voeg de volgende code toe:

```csharp
//Maak een rijobject en voeg het toe aan een tabelinstantie
Aspose.Pdf.Row row = table.Rows.Add();
// Maak een celobject en voeg het toe aan een rij-instantie
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Stap 6: Tekst en afbeelding toevoegen aan cellen

Laten we nu tekst en de SVG-afbeelding toevoegen aan de cellen van de tabel. We voegen de tekst "Eerste cel" toe aan de eerste cel en de SVG-afbeelding aan de tweede cel. Voeg de volgende code toe:

```csharp
// Voeg tekstfragment toe aan alineaverzameling van celobject
cell.Paragraphs.Add(new TextFragment("First cell"));
// Voeg een andere cel toe aan een rijobject
cell = row. Cells. Add();
// SVG-afbeelding toevoegen aan alineaverzameling van recent toegevoegde celinstantie
cell.Paragraphs.Add(img);
```

## Stap 7: Maak en voeg een pagina toe aan het document

Laten we nu een paginaobject maken en toevoegen aan het document. De tabel wordt toegevoegd aan de alineaverzameling van de pagina. Voeg de volgende code toe:

```csharp
// Maak een pagina-object en voeg het toe aan de paginaverzameling van het documentexemplaar
Page page = doc.Pages.Add();
// Tabel toevoegen aan alineaverzameling van pagina-object
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

### Voorbeeldbroncode voor het toevoegen van SVG-objecten met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer Document object
Document doc = new Document();
// Een afbeeldinginstantie maken
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Stel het afbeeldingstype in als SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pad voor bronbestand
img.File = dataDir + "SVGToPDF.svg";
// Breedte instellen voor afbeeldinginstantie
img.FixWidth = 50;
// Hoogte instellen voor afbeeldinginstantie
img.FixHeight = 50;
// Tabelinstantie maken
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breedte instellen voor tabelcellen
table.ColumnWidths = "100 100";
//Maak een rijobject en voeg het toe aan een tabelinstantie
Aspose.Pdf.Row row = table.Rows.Add();
// Maak een celobject en voeg het toe aan een rij-instantie
Aspose.Pdf.Cell cell = row.Cells.Add();
// Voeg tekstfragment toe aan alineaverzameling van celobject
cell.Paragraphs.Add(new TextFragment("First cell"));
// Voeg een andere cel toe aan een rijobject
cell = row.Cells.Add();
// SVG-afbeelding toevoegen aan alineaverzameling van recent toegevoegde celinstantie
cell.Paragraphs.Add(img);
// Maak een pagina-object en voeg het toe aan de paginaverzameling van het documentexemplaar
Page page = doc.Pages.Add();
// Tabel toevoegen aan alineaverzameling van pagina-object
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-bestand opslaan
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusie

In deze tutorial hebben we geleerd hoe u een SVG-object toevoegt aan een PDF-bestand met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het stapsgewijze proces behandeld van het maken van een document, het instellen van de omgeving, het toevoegen van een SVG-afbeelding aan een tabelcel en het opslaan van het PDF-bestand. Nu kunt u SVG-objecten programmatisch in uw PDF-documenten opnemen.

### FAQ's voor het toevoegen van SVG-objecten aan een PDF-bestand

#### V: Kan ik meerdere SVG-objecten aan het PDF-document toevoegen?

 A: Ja, u kunt meerdere SVG-objecten toevoegen aan het PDF-document. Maak en configureer eenvoudig extra`Aspose.Pdf.Image` exemplaren voor elke SVG-afbeelding die u wilt toevoegen en voeg ze vervolgens toe aan de gewenste tabelcellen of alinea's in het PDF-document.

#### V: Hoe kan ik de grootte en positie van de SVG-afbeelding in de tabelcel aanpassen?

 A: Om de grootte en positie van de SVG-afbeelding in de tabelcel aan te passen, kunt u de`FixWidth` En`FixHeight` eigenschappen van de`Aspose.Pdf.Image`voorbeeld. U kunt ook andere eigenschappen gebruiken, zoals`HorizontalAlignment` En`VerticalAlignment` van de tabelcel om de positionering te regelen.

#### V: Is het mogelijk om tekst toe te voegen naast de SVG-afbeelding in dezelfde tabelcel?

 A: Ja, het is mogelijk om tekst toe te voegen naast de SVG-afbeelding in dezelfde tabelcel. U kunt de`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` Methode om tekst aan de cel toe te voegen samen met de SVG-afbeelding.

#### V: Kan ik hyperlinks toevoegen aan de SVG-afbeelding?

 A: Ja, u kunt hyperlinks toevoegen aan de SVG-afbeelding met behulp van de`Hyperlink` eigendom van de`Aspose.Pdf.Image` voorbeeld. Stel de hyperlink-URL of actie in om de afbeelding klikbaar te maken.

#### V: Is Aspose.PDF voor .NET compatibel met .NET Core 3.1 of latere versies?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET Core 3.1 en latere versies. U kunt het gebruiken in zowel .NET Framework als .NET Core-applicaties.