---
title: Automatisch aanpassen aan venster
linktitle: Automatisch aanpassen aan venster
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om Aspose.PDF voor .NET te gebruiken en automatisch aan venster aan te passen bij het genereren van PDF's.
type: docs
weight: 50
url: /nl/net/programming-with-tables/auto-fit-to-window/
---
Het volgende artikel is een stapsgewijze handleiding voor het gebruik van de meegeleverde C#-broncode om de functionaliteit Auto Fit To Window te bereiken met behulp van de Aspose.PDF-bibliotheek voor .NET. Met de functie Auto Fit To Window kunt u PDF-bestanden genereren met een lay-out die is aangepast aan het weergavevenster. Deze functie is vooral handig als u wilt dat uw PDF-document zich automatisch aanpast aan de grootte van het PDF-lezervenster dat door de gebruiker wordt gebruikt.

## Stap 1: De omgeving instellen

Voordat u begint, moet u de Aspose.PDF-bibliotheek voor .NET op uw computer installeren. Zorg er ook voor dat u de benodigde naamruimten in uw project importeert.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een PDF-document maken

 Om te beginnen moet u een`Document` object door de standaardconstructor ervan aan te roepen.

```csharp
Document doc = new Document();
```

 Maak vervolgens een sectie in het`Pdf` voorwerp.

```csharp
Page sec1 = doc.Pages.Add();
```

## Stap 3: Een tabel aan het document toevoegen

 In deze stap gaan we een tabel toevoegen aan ons PDF-document. Maak eerst een`Table` voorwerp.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Voeg vervolgens de tabel toe aan de alineaverzameling van de sectie.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Stap 4: Het uiterlijk van de tabel aanpassen

U kunt het uiterlijk van de tabel aanpassen door eigenschappen in te stellen, zoals celranden en marge.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Stap 4: Rijen en cellen aan de tabel toevoegen

Laten we nu rijen en cellen aan onze tabel toevoegen. Begin met het maken van een rij en het toevoegen van cellen aan die rij.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Stap 5: Het document opslaan

Geef ten slotte het pad van het uitvoerbestand op en sla het document op.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor automatisch aanpassen aan venster met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Start het Pdf-object door de lege constructor ervan aan te roepen
Document doc = new Document();
// Maak de sectie in het Pdf-object
Page sec1 = doc.Pages.Add();

// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
sec1.Paragraphs.Add(tab1);

// Ingesteld met kolombreedtes van de tabel
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Stel de standaardcelrand in met het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Stel de tabelrand in met een ander aangepast BorderInfo-object
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Stel de standaardcelopvulling in op het MarginInfo-object
tab1.DefaultCellPadding = margin;

// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Bewaar het bijgewerkte document met het tabelobject
doc.Save(dataDir);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u Aspose.PDF voor .NET kunt gebruiken om een PDF-bestand te genereren met de functie Automatisch aanpassen aan venster. Deze functie is uiterst handig als u wilt dat uw PDF-document zich automatisch aanpast aan de grootte van het weergavevenster. Aspose.PDF voor .NET biedt vele andere krachtige functies voor het genereren en manipuleren van PDF-bestanden. Ik moedig u aan om deze bibliotheek verder te verkennen en alle mogelijkheden ervan te ontdekken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van de functie Automatisch aanpassen aan venster bij het genereren van PDF's?

A: De functie Automatisch aanpassen aan venster bij het genereren van PDF's zorgt ervoor dat de lay-out van het PDF-document zich automatisch aanpast aan de grootte van het PDF-lezervenster dat door de gebruiker wordt gebruikt. Dit zorgt voor een betere weergave en zorgt ervoor dat de inhoud perfect binnen het beschikbare kijkgebied past.

#### Vraag: Kan ik het uiterlijk van de tabel aanpassen, zoals lettergrootte en kleuren?

A: Ja, u kunt het uiterlijk van de tabel in het PDF-document aanpassen met Aspose.PDF voor .NET. Het meegeleverde codefragment laat zien hoe u eigenschappen zoals celranden, marges en kolombreedtes instelt. U kunt de lettergrootte, kleuren en andere stijlaspecten van de tabel en de inhoud ervan verder aanpassen.

#### Vraag: Hoe integreer ik Aspose.PDF voor .NET in mijn C#-project?

A: Om Aspose.PDF voor .NET in uw C#-project te gebruiken, moet u eerst de Aspose.PDF-bibliotheek voor .NET op uw computer installeren. Vervolgens kunt u een verwijzing naar de bibliotheek in uw C#-project toevoegen. Importeer ten slotte de benodigde naamruimten om toegang te krijgen tot de klassen en methoden die door Aspose.PDF voor .NET worden geleverd.

#### Vraag: Is Aspose.PDF voor .NET compatibel met .NET Core-applicaties?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET Core-applicaties. Het ondersteunt verschillende .NET-platforms, waaronder .NET Framework, .NET Core en .NET 5.0+.

#### Vraag: Kan ik meer tabellen aan het PDF-document toevoegen?

A: Ja, u kunt meerdere tabellen aan een PDF-document toevoegen door soortgelijke stappen te volgen als weergegeven in het codefragment. Maak eenvoudig nieuwe exemplaren van de`Aspose.Pdf.Table` klasse en voeg ze toe aan verschillende secties of pagina's van het PDF-document.