---
title: Rand in PDF instellen op tabel
linktitle: Rand in PDF instellen op tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een rand in een PDF-bestand aan een tabel kunt toevoegen met Aspose.PDF voor .NET.
type: docs
weight: 200
url: /nl/net/programming-with-tables/set-border/
---
In deze tutorial begeleiden we u stap voor stap bij het instellen van een rand in een tabel van een PDF-document met behulp van Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten zien hoe u deze implementeert.

## Stap 1: Het Document-object instantiëren
Eerst maken we een Document-object:

```csharp
Document doc = new Document();
```

## Stap 2: Een pagina toevoegen aan het PDF-document
Vervolgens voegen we een pagina toe aan het PDF-document:

```csharp
Page page = doc.Pages.Add();
```

## Stap 3: Het BorderInfo-object maken
We gaan nu een BorderInfo-object maken om de rand van de tabel te definiëren:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Stap 4: Boven- en onderranden specificeren
We geven aan dat de boven- en onderrand dubbel zijn:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Stap 5: Het Table-object instantiëren
Laten we nu een Table-object instantiëren:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Stap 6: Kolombreedtes specificeren
We specificeren de breedtes van de kolommen van de tabel:

```csharp
table. ColumnWidths = "100";
```

## Stap 7: Het rijobject maken
We maken een Row-object:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Stap 8: Een cel toevoegen aan de rij
Vervolgens voegen we een cel toe aan de rij:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Stap 9: De celgrens instellen
We gaan de rand van de cel definiëren (dubbele rand):

```csharp
cell. Border = border;
```

## Stap 10: De tabel aan de pagina toevoegen
Laten we nu de tabel aan de documentpagina toevoegen:

```csharp
page.Paragraphs.Add(table);
```

## Stap 11: PDF-document opslaan
Ten slotte slaan we het PDF-document op:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor Set Border met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer Document-object
Document doc = new Document();
// Pagina toevoegen aan PDF-document
Page page = doc.Pages.Add();
// BorderInfo-object maken
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Geef aan dat de bovenrand dubbel zal zijn
border.Top.IsDoubled = true;
// Geef aan dat de onderste rand dubbel zal zijn
border.Bottom.IsDoubled = true;
// Instantieer tabelobject
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Geef informatie over de breedte van kolommen op
table.ColumnWidths = "100";
// Rijobject maken
Aspose.Pdf.Row row = table.Rows.Add();
// Voeg een tabelcel toe aan de cellenverzameling van de rij
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Rand voor celobject instellen (dubbele rand)
cell.Border = border;
// Tabel toevoegen aan alineaverzameling van pagina
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Sla het PDF-document op
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een rand in een tabel van een PDF-document kunt instellen met Aspose.PDF voor .NET. Deze stapsgewijze handleiding liet u zien hoe u een document kunt maken, een pagina kunt toevoegen, de tabelrand kunt configureren en het PDF-document kunt opslaan. Nu kunt u deze kennis toepassen op uw eigen projecten.

### Veelgestelde vragen

#### V: Kan ik verschillende randstijlen (bijvoorbeeld onderbroken of gestippeld) instellen voor de boven- en onderrand van de tabel?

 A: Ja, u kunt verschillende randstijlen instellen voor de boven- en onderrand van de tabel door de`border.Top.Style` En`border.Bottom.Style`eigenschappen in de meegeleverde C#-broncode. Met Aspose.PDF voor .NET kunt u kiezen uit verschillende randstijlen, waaronder Solid, Dashed, Dotted, Double en meer.

#### V: Hoe kan ik de kleur van de tabelrand instellen?

 A: U kunt de kleur van de rand van de tabel instellen door de`border.Color` eigenschap in de C# broncode. Geef gewoon de gewenste kleur op, zoals`Aspose.Pdf.Color.Red` of een andere geldige kleurweergave, om de randkleur aan te passen.

#### V: Is het mogelijk om randen toe te passen op afzonderlijke cellen in de tabel met verschillende instellingen (bijvoorbeeld verschillende kleuren of randstijlen)?

 A: Ja, u kunt randen toepassen op afzonderlijke cellen in de tabel met verschillende instellingen door de`cell.Border` eigenschap voor elke cel afzonderlijk. Hiermee kunt u celspecifieke randstijlen en kleuren gebruiken op basis van uw vereisten.

#### V: Kan ik de rand aan specifieke kanten van de tabel verwijderen (bijvoorbeeld de linker- en rechterrand)?

 A: Ja, u kunt de rand van specifieke kanten van de tafel verwijderen door de`border.Left`, `border.Right`, `border.Top` , En`border.Bottom`eigenschappen in de C#-broncode. Deze eigenschappen instellen op`null` verwijdert de rand van de overeenkomstige zijden van de tabel.

#### V: Hoe kan ik de dikte van de tafelrand aanpassen?

 A: U kunt de dikte van de rand van de tabel aanpassen door de`border.Width` eigenschap in de C# broncode. Stel eenvoudig de gewenste randbreedte (in punten) in om de gewenste dikte te bereiken.