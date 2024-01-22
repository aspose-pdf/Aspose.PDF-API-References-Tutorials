---
title: Afgeronde hoektafel in PDF-document
linktitle: Afgeronde hoektafel in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel met afgeronde hoeken in een PDF-document kunt maken met Aspose.PDF voor .NET.
type: docs
weight: 190
url: /nl/net/programming-with-tables/rounded-corner-table/
---
In deze zelfstudie begeleiden we u stap voor stap bij het maken van een tabel met afgeronde hoeken in een PDF-document met behulp van Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze kunt implementeren.

## Stap 1: De tabel maken
Eerst zullen we de tabel maken met behulp van de volgende code:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Stap 2: Afgeronde hoekstijl instellen
Vervolgens configureren we de afgeronde hoekstijl voor de tafel:

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

// Pas randinformatie toe op de tabel
tab1.Border = bInfo;
```

### Voorbeeldbroncode voor Rounded Corner Table met Aspose.PDF voor .NET

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
// Stel de hoekstijl van de tafel in op Rond.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Stel de tabelrandinformatie in
tab1.Border = bInfo;
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een tabel met afgeronde hoeken in een PDF-document kunt maken met Aspose.PDF voor .NET. Deze stapsgewijze handleiding liet u zien hoe u de afgeronde hoekstijl en de tafelrand instelt. Nu kunt u deze kennis toepassen op uw eigen projecten.

### Veelgestelde vragen over tafel met ronde hoeken in PDF-document

#### Vraag: Kan ik de straal van de afgeronde hoeken van de tafel aanpassen?

A: Ja, u kunt de straal van de afgeronde hoeken van de tafel aanpassen door de waarde van de te wijzigen`bInfo.RoundedBorderRadius` eigenschap in de opgegeven C#-broncode. Stel eenvoudig de gewenste straalwaarde in (in punten) om het gewenste afgeronde hoekeffect te bereiken.

#### Vraag: Kan ik afgeronde hoeken toepassen op individuele cellen in de tabel?

A: Nee, de afgeronde hoekstijl wordt op de hele tafel als geheel toegepast. Aspose.PDF voor .NET biedt momenteel geen ingebouwde ondersteuning voor het toepassen van afgeronde hoeken op individuele cellen in de tabel.

#### Vraag: Kan ik de kleur van de afgeronde hoekrand wijzigen?

 A: Ja, u kunt de kleur van de afgeronde hoekrand wijzigen door de waarde van de`graph.Color` eigenschap in de C#-broncode. Geef eenvoudig de gewenste kleur door, bijv`Aspose.Pdf.Color.Red` of enige andere geldige kleurweergave.

#### Vraag: Is het mogelijk om verschillende hoekstijlen (bijvoorbeeld vierkant en afgerond) toe te passen op verschillende tabellen binnen hetzelfde PDF-document?

A: Ja, het is mogelijk om verschillende hoekstijlen toe te passen op verschillende tabellen binnen hetzelfde PDF-document. U kunt meerdere tafels maken en hun hoekstijlen individueel configureren op basis van uw vereisten.

#### Vraag: Kan ik de dikte van de afgeronde hoekrand aanpassen?

 A: Ja, u kunt de dikte van de afgeronde hoekrand aanpassen door de`BorderInfo` objecteigenschappen in de C#-broncode. U kunt bijvoorbeeld de`bInfo.Width` eigenschap om de dikte van de rand aan te passen.