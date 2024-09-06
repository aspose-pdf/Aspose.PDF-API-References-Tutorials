---
title: lnk Annotatie Lijnbreedte
linktitle: lnk Annotatie Lijnbreedte
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u de lijnbreedte van inktannotaties in een PDF instelt met Aspose.PDF voor .NET. Deze gedetailleerde tutorial begeleidt u door elke stap en zorgt voor een uitvoer van hoge kwaliteit.
type: docs
weight: 110
url: /nl/net/annotations/lnkannotationlinewidth/
---
## Invoering

Bij het werken met PDF-documenten kan het toevoegen van annotaties een krachtige manier zijn om informatie te markeren of interactieve elementen toe te voegen aan uw bestanden. Een dergelijke annotatie is de Ink Annotation, waarmee u vrije lijnen op uw PDF kunt tekenen. Maar wat als u het uiterlijk van deze lijnen wilt aanpassen, met name de lijnbreedte? In deze tutorial leiden we u door het proces van het instellen van de lijnbreedte van de inktannotatie met behulp van Aspose.PDF voor .NET.

## Vereisten

Voordat we in de code duiken, controleren we of alles klaar is om deze tutorial soepel te kunnen volgen:

1.  Aspose.PDF voor .NET: Zorg ervoor dat u de Aspose.PDF voor .NET-bibliotheek hebt geïnstalleerd. U kunt deze downloaden van de[downloadpagina](https://releases.aspose.com/pdf/net/) of installeer het via NuGet Package Manager in Visual Studio.
2. Ontwikkelomgeving: in deze zelfstudie gaan we ervan uit dat u in een .NET-ontwikkelomgeving werkt, zoals Visual Studio.
3. Basiskennis van C#: Een basiskennis van C# helpt u de coderingsstappen te volgen.
4. PDF-document: Gebruik een bestaand PDF-document of maak een nieuw document voor deze tutorial.

## Noodzakelijke naamruimten importeren

Voordat u begint met coderen, moet u ervoor zorgen dat u de benodigde naamruimten in uw project importeert:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Deze naamruimten bieden de klassen en methoden die nodig zijn om PDF-documenten te bewerken, met annotaties te werken en grafische elementen te verwerken.

Nu we aan de vereisten hebben voldaan, kunnen we het proces voor het instellen van de lijnbreedte voor inktannotaties opsplitsen in duidelijke, beheersbare stappen.

## Stap 1: Initialiseer het PDF-document

Eerst moeten we een PDF-document maken of openen. Voor deze tutorial maken we een nieuw PDF-document vanaf nul.

```csharp
// Initialiseer het PDF-document
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Geef uw documentdirectory op
Document doc = new Document();
doc.Pages.Add(); // Voeg een lege pagina toe aan het document
```

 Hier initialiseren we een nieuwe`Document` object, dat ons PDF-bestand vertegenwoordigt. Vervolgens voegen we een lege pagina toe aan dit document om mee te werken.

## Stap 2: Maak de inktannotatie

Vervolgens maken we de inktannotatie zelf. Dit houdt in dat we de punten definiëren die de inktstreken vormen.

```csharp
// Maak de inktannotatie
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 In deze stap definiëren we de`LineInfo` object, dat de coördinaten van de inktstreken, hun zichtbaarheid, kleur en initiële lijnbreedte bevat.`VerticeCoordinate` array bevat de X- en Y-coördinaten van elk punt in de streek.

## Stap 3: Coördinaten omzetten in punten

Nu moeten we deze coördinaten omzetten in punten die gebruikt kunnen worden door de inktannotatie.

```csharp
// Coördinaten omzetten naar punten
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Deze lus verwerkt de coördinatenreeks en zet elk paar coördinaten om in een`Point` object, dat vervolgens aan onze wordt toegevoegd`inkList`.

## Stap 4: Voeg de inktannotatie toe aan de PDF-pagina

Nu de punten gereed zijn, kunnen we de inktannotatie maken en deze aan de PDF-pagina toevoegen.

```csharp
// Voeg de inktannotatie toe aan de PDF-pagina
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 In deze stap initialiseren we een`InkAnnotation`object, waarbij de pagina, een begrenzende rechthoek en onze lijst met punten worden gespecificeerd. We stellen ook het onderwerp, de titel en de kleur van de annotatie in.

## Stap 5: Pas de rand van de annotatie aan

Om het uiterlijk van onze annotatie verder te personaliseren, passen we de randeigenschappen aan.

```csharp
// Pas de rand van de annotatie aan
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Hier creëren we een`Border` object voor onze annotatie, waarbij de breedte, het effect, het streepjespatroon en de stijl worden ingesteld. Deze stap zorgt ervoor dat de annotatie visueel opvalt op de PDF-pagina.

## Stap 6: Sla het PDF-document op

Nadat u alle benodigde wijzigingen hebt aangebracht, is het tijd om het document op te slaan.

```csharp
// Sla het PDF-document op
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Deze code slaat het gewijzigde PDF-document met de inktannotatie op in de opgegeven directory.`Console.WriteLine` De instructie bevestigt de succesvolle uitvoering van de code.

## Conclusie

Gefeliciteerd! U hebt met succes een inktannotatie in een PDF-document gemaakt en aangepast met Aspose.PDF voor .NET. Deze tutorial behandelde het hele proces, van het initialiseren van het document tot het opslaan van het uiteindelijke bestand. Met deze kennis kunt u de uitgebreide mogelijkheden van Aspose.PDF voor .NET verder verkennen en vergelijkbare technieken toepassen op andere typen annotaties of PDF-manipulaties.

## Veelgestelde vragen

### Kan ik verschillende kleuren gebruiken voor verschillende delen van de inktannotatie?  
 Ja, u kunt meerdere`InkAnnotation` objecten met verschillende kleuren en voeg ze toe aan dezelfde of verschillende pagina's van uw PDF.

### Hoe kan ik de lijnbreedte dynamisch wijzigen?  
 U kunt de`LineWidth` eigendom van de`LineInfo` object voordat de coördinaten naar punten worden omgezet.

### Is het mogelijk om de inktannotatie transparant te maken?  
 Ja, u kunt de`Opacity` eigendom van de`InkAnnotation` object om het transparant te maken.

### Kan ik meerdere inkttekeningen op dezelfde pagina maken?  
Absoluut! U kunt zoveel inktannotaties als u wilt toevoegen aan een enkele pagina door het proces te herhalen.

### Hoe verwijder ik een inkt-annotatie uit een PDF?  
 U kunt een aantekening verwijderen met behulp van de`doc.Pages[1].Annotations.Delete(a1)` methode, waarbij`a1` is uw annotatieobject.