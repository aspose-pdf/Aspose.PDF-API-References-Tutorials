---
title: Afgeronde hoektafel in PDF-document
linktitle: Afgeronde hoektafel in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een ronde hoektabel in een PDF-document maakt met Aspose.PDF voor .NET.
type: docs
weight: 190
url: /nl/net/programming-with-tables/rounded-corner-table/
---
In deze tutorial begeleiden we u stap voor stap bij het maken van een afgeronde hoektabel in een PDF-document met behulp van Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze implementeert.

## Stap 1: De tabel maken
Eerst maken we de tabel aan met behulp van de volgende code:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Stap 2: Afgeronde hoekstijl-opstelling
Vervolgens configureren we de stijl voor de afgeronde hoeken van de tabel:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Stap 3: Tabelrand instellen
Om de tabel een afgeronde hoekrand te geven, moeten we een BorderInfo-object maken en dit configureren met de juiste parameters:

```csharp
// Maak een GraphInfo-object om de randkleur in te stellen
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Maak een leeg BorderInfo-object
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Stel de straal van de afgeronde rand in op 15
bInfo.RoundedBorderRadius = 15;

// Randinformatie op de tabel toepassen
tab1.Border = bInfo;
```

### Voorbeeldbroncode voor Rounded Corner Table met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Maak een leeg BorderInfo-object
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Stel de rand in op een rondere rand waarbij de straal van de ronde 15 is
bInfo.RoundedBorderRadius = 15;
// Stel de hoekstijl van de tabel in op Rond.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Stel de tabelrandinformatie in
tab1.Border = bInfo;
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een ronde hoektabel in een PDF-document kunt maken met Aspose.PDF voor .NET. Deze stapsgewijze handleiding liet u zien hoe u de ronde hoekstijl en tabelrand instelt. Nu kunt u deze kennis toepassen op uw eigen projecten.

### FAQ's voor ronde hoektafel in PDF-document

#### V: Kan ik de straal van de afgeronde hoeken van de tafel aanpassen?

A: Ja, u kunt de straal van de afgeronde hoeken voor de tabel aanpassen door de waarde van de`bInfo.RoundedBorderRadius` eigenschap in de meegeleverde C# broncode. Stel eenvoudig de gewenste radiuswaarde (in punten) in om het gewenste afgeronde hoekuiterlijk te bereiken.

#### V: Kan ik afgeronde hoeken toepassen op afzonderlijke cellen in de tabel?

A: Nee, de stijl met afgeronde hoeken wordt toegepast op de gehele tabel als geheel. Aspose.PDF voor .NET biedt momenteel geen ingebouwde ondersteuning voor het toepassen van afgeronde hoeken op afzonderlijke cellen in de tabel.

#### V: Kan ik de kleur van de afgeronde hoekrand wijzigen?

 A: Ja, u kunt de kleur van de afgeronde hoekrand wijzigen door de waarde van de`graph.Color` eigenschap in de C# broncode. Geef gewoon de gewenste kleur op, zoals`Aspose.Pdf.Color.Red` of een andere geldige kleurweergave.

#### V: Is het mogelijk om verschillende hoekstijlen (bijvoorbeeld vierkant en afgerond) toe te passen op verschillende tabellen in hetzelfde PDF-document?

A: Ja, het is mogelijk om verschillende hoekstijlen toe te passen op verschillende tabellen binnen hetzelfde PDF-document. U kunt meerdere tabellen maken en hun hoekstijlen individueel configureren op basis van uw vereisten.

#### V: Kan ik de dikte van de afgeronde hoekrand aanpassen?

 A: Ja, u kunt de dikte van de afgeronde hoekrand aanpassen door de`BorderInfo` eigenschappen van het object in de C#-broncode. U kunt bijvoorbeeld de`bInfo.Width` eigenschap om de dikte van de rand aan te passen.