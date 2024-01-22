---
title: Tabel toevoegen in PDF-bestand
linktitle: Tabel toevoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig tabellen toe aan een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-tables/add-table/
---
Aspose.PDF voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PDF-documenten programmatisch kunnen maken, manipuleren en transformeren. In deze zelfstudie begeleiden we u bij het toevoegen van een tabel in een PDF-bestand met Aspose.PDF voor .NET. We leggen elke stap van het meegeleverde codefragment uit en bieden een uitgebreide handleiding om u te helpen de functionaliteit in uw eigen projecten te begrijpen en te implementeren.

## Invoering

PDF-documenten worden veel gebruikt voor het delen en bewaren van informatie in een draagbaar formaat. Het toevoegen van tabellen aan PDF-documenten kan de visuele weergave ervan verbeteren en de gegevenspresentatie overzichtelijker en gestructureerder maken. Aspose.PDF voor .NET biedt een handige manier om tabellen aan bestaande PDF-documenten toe te voegen of geheel nieuwe te maken.

## Wat is Aspose.PDF voor .NET?

Aspose.PDF voor .NET is een krachtige bibliotheek met veel functies waarmee .NET-ontwikkelaars programmatisch PDF-documenten kunnen maken, manipuleren en converteren. Het biedt een breed scala aan functionaliteiten, waaronder het helemaal opnieuw maken van PDF-bestanden, het wijzigen van bestaande PDF-documenten, het samenvoegen of splitsen van PDF-bestanden, het toevoegen van tekst, afbeeldingen en tabellen, het extraheren van gegevens uit PDF's en nog veel meer. Met Aspose.PDF voor .NET kunnen ontwikkelaars complexe PDF-gerelateerde taken automatiseren en hoogwaardige PDF-oplossingen leveren.

## Een tabel toevoegen aan een PDF-document

Volg de onderstaande stapsgewijze handleiding om een tabel aan een PDF-document toe te voegen met Aspose.PDF voor .NET:

## Stap 1: Het bron-PDF-document laden

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Met het bovenstaande codefragment wordt het bron-PDF-document geladen waaraan u de tabel wilt toevoegen. Zorg ervoor dat u het juiste pad naar uw PDF-bestand opgeeft.

## Stap 2: Een nieuw exemplaar van de tabel initialiseren

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In deze stap maken we een nieuw exemplaar van de klasse Table, die een tabel in een PDF-document vertegenwoordigt.

## Stap 3: De kleur van de tabelrand instellen

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Hier stellen we de randkleur voor de tabel in met behulp van de klasse BorderInfo. U kunt de randstijl, breedte en kleur aanpassen aan uw wensen.

## Stap 4: De rand voor tabelcellen instellen

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

We stellen ook de rand voor tabelcellen in met behulp van de eigenschap DefaultCellBorder van het tabelobject. Dit zorgt ervoor dat elke cel in de tabel de opgegeven randstijl, breedte en kleur heeft.

## Stap 5: Rijen en cellen aan de tabel toevoegen

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

In deze stap maken we een lus om 10 rijen aan de tabel toe te voegen. Binnen elke rij voegen we drie cellen met voorbeeldgegevens toe. U kunt de code wijzigen om rijen en cellen toe te voegen volgens uw specifieke vereisten.

## Stap 6: Het tabelobject aan het document toevoegen

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Bewaar het bijgewerkte document met het tabelobject
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Ten slotte voegen we het tabelobject toe aan de eerste pagina van het PDF-document met behulp van de Paragraphs-verzameling van de overeenkomstige pagina.

### Voorbeeldbroncode voor het toevoegen van een tabel met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Bron-PDF-document laden
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Initialiseert een nieuw exemplaar van de tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Stel de kleur van de tabelrand in als LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Stel de rand voor tabelcellen in
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Maak een lus om 10 rijen toe te voegen
for (int row_count = 1; row_count < 10; row_count++)
{
	// Rij toevoegen aan tabel
	Aspose.Pdf.Row row = table.Rows.Add();
	// Tabelcellen toevoegen
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Voeg een tabelobject toe aan de eerste pagina van het invoerdocument
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Bewaar het bijgewerkte document met het tabelobject
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Conclusie

In deze zelfstudie hebben we het stapsgewijze proces uitgelegd van het toevoegen van een tabel aan een PDF-document met Aspose.PDF voor .NET. We behandelden het laden van het bron-PDF-document, het initialiseren van een nieuw exemplaar van de klasse Table, het instellen van de kleur van de tabelrand en de celranden, het toevoegen van rijen en cellen aan de tabel en het toevoegen van het tabelobject aan het document. Door deze handleiding te volgen, kunt u eenvoudig tabellen programmatisch in uw PDF-documenten opnemen en deze aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen over het toevoegen van een tabel in een PDF-bestand

#### Vraag: Kan ik meer kolommen aan de tabel toevoegen?

A: Ja, u kunt meer kolommen aan de tabel toevoegen door het aantal cellen dat aan elke rij wordt toegevoegd te vergroten. In het gegeven voorbeeld heeft elke rij drie cellen die drie kolommen vertegenwoordigen. U kunt meer cellen aan elke rij toevoegen om extra kolommen toe te voegen.

#### Vraag: Hoe kan ik het uiterlijk van de tabel wijzigen, zoals lettergrootte en stijl?

 A: U kunt het uiterlijk van de tabel aanpassen, inclusief lettergrootte en stijl, door eigenschappen in te stellen op het`Aspose.Pdf.Table` En`Aspose.Pdf.TextFragment` voorwerpen. U kunt bijvoorbeeld de`DefaultCellTextState` eigenschap om de lettertype-eigenschappen van de tekst in de tabelcellen te wijzigen.

#### Vraag: Is het mogelijk om cellen in de tabel samen te voegen?

 A: Ja, u kunt cellen in de tabel samenvoegen met behulp van de`MergeCells` werkwijze van de`Aspose.Pdf.Row` klas. Hierdoor kunt u cellen maken die meerdere rijen en kolommen beslaan.

#### Vraag: Kan ik afbeeldingen of andere inhoud aan de tabelcellen toevoegen?

A: Ja, u kunt verschillende soorten inhoud aan de tabelcellen toevoegen, inclusief afbeeldingen, tekst, hyperlinks en meer. U kunt de juiste klassen van Aspose.PDF voor .NET gebruiken om verschillende soorten inhoud aan de cellen toe te voegen.

#### Vraag: Is Aspose.PDF voor .NET compatibel met .NET 5.0 of latere versies?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET 5.0 en latere versies. Het ondersteunt verschillende .NET-platforms, waaronder .NET Framework, .NET Core en .NET 5.0+.