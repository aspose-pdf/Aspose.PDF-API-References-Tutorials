---
title: Rand in PDF instellen op tabel
linktitle: Rand in PDF instellen op tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een rand in PDF naar tabel kunt instellen met Aspose.PDF voor .NET.
type: docs
weight: 200
url: /nl/net/programming-with-tables/set-border/
---
In deze tutorial begeleiden we u stap voor stap bij het instellen van een rand in een tabel van een PDF-document met behulp van Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze kunt implementeren.

## Stap 1: Het documentobject instantiëren
Eerst zullen we een Document-object instantiëren:

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

## Stap 4: Boven- en onderranden opgeven
We specificeren dat de boven- en onderrand dubbel zijn:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Stap 5: Instantie van het Table-object
Laten we nu een Table-object instantiëren:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Stap 6: Kolombreedtes opgeven
We zullen de breedte van de kolommen van de tabel specificeren:

```csharp
table. ColumnWidths = "100";
```

## Stap 7: Het rijobject maken
We zullen een Row-object maken:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Stap 8: Een cel aan de rij toevoegen
Vervolgens voegen we een cel aan de rij toe:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Stap 9: De celrand instellen
We gaan de rand van de cel definiëren (dubbele rand):

```csharp
cell. Border = border;
```

## Stap 10: De tabel aan de pagina toevoegen
Laten we nu de tabel toevoegen aan de documentpagina:

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

### Voorbeeldbroncode voor Set Border met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een documentobject
Document doc = new Document();
// Pagina toevoegen aan PDF-document
Page page = doc.Pages.Add();
// Maak een BorderInfo-object
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Geef op dat de bovenrand dubbel is
border.Top.IsDoubled = true;
// Geef op dat de onderrand dubbel is
border.Bottom.IsDoubled = true;
// Instantiëer een tabelobject
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Geef informatie over de kolombreedte op
table.ColumnWidths = "100";
// Maak een Rij-object
Aspose.Pdf.Row row = table.Rows.Add();
// Voeg een tabelcel toe aan de celverzameling van de rij
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Stel de rand voor het celobject in (dubbele rand)
cell.Border = border;
// Tabel toevoegen aan alineaverzameling van pagina
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Sla het PDF-document op
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een rand in een tabel van een PDF-document kunt instellen met Aspose.PDF voor .NET. In deze stapsgewijze handleiding werd uitgelegd hoe u een document maakt, een pagina toevoegt, de tabelrand configureert en het PDF-document opslaat. Nu kunt u deze kennis toepassen op uw eigen projecten.

### Veelgestelde vragen

#### Vraag: Kan ik verschillende randstijlen instellen (bijvoorbeeld gestippeld of gestippeld) voor de boven- en onderrand van de tabel?

 A: Ja, u kunt verschillende randstijlen instellen voor de boven- en onderrand van de tabel door de`border.Top.Style` En`border.Bottom.Style`eigenschappen in de meegeleverde C#-broncode. Met Aspose.PDF voor .NET kunt u kiezen uit verschillende randstijlen, waaronder Effen, Gestreept, Gestippeld, Dubbel en meer.

#### Vraag: Hoe kan ik de kleur van de tafelrand instellen?

 A: U kunt de kleur van de tabelrand instellen door de`border.Color` eigenschap in de C#-broncode. Geef eenvoudig de gewenste kleur door, bijv`Aspose.Pdf.Color.Red` of een andere geldige kleurweergave, om de randkleur aan te passen.

#### Vraag: Is het mogelijk om randen toe te passen op individuele cellen in de tabel met verschillende instellingen (bijvoorbeeld verschillende kleuren of randstijlen)?

 A: Ja, u kunt randen toepassen op individuele cellen in de tabel met verschillende instellingen door de`cell.Border` eigenschap voor elke cel afzonderlijk. Hierdoor kunt u celspecifieke randstijlen en -kleuren gebruiken op basis van uw vereisten.

#### Vraag: Kan ik de rand van specifieke zijden van de tabel verwijderen (bijvoorbeeld de linker- en rechterrand)?

 A: Ja, u kunt de rand van specifieke zijden van de tabel verwijderen door de`border.Left`, `border.Right`, `border.Top` , En`border.Bottom`eigenschappen in de C#-broncode. Deze eigenschappen instellen op`null` verwijdert de rand van de overeenkomstige zijden van de tafel.

#### Vraag: Hoe kan ik de dikte van de tafelrand aanpassen?

 A: U kunt de dikte van de tafelrand aanpassen door de`border.Width` eigenschap in de C#-broncode. Stel eenvoudig de gewenste randbreedte (in punten) in om de gewenste dikte te bereiken.