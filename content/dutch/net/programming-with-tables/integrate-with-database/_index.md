---
title: Integreren met database in PDF-bestand
linktitle: Integreren met database in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Sluit gegevens uit een database in een PDF-bestand in met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-tables/integrate-with-database/
---
In deze tutorial leren we hoe u data uit een database in een PDF-bestand kunt insluiten met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet u hoe u tabeldata uit een database in een PDF-document kunt importeren. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg ervoor dat u uw C#-ontwikkelomgeving hebt geconfigureerd met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: De DataTable maken
We maken een instantie van DataTable om de gegevens te representeren die we in het PDF-document willen insluiten. In dit voorbeeld maken we een DataTable met drie kolommen: Employee_ID, Employee_Name en Gender. We voegen ook twee rijen toe aan de DataTable met dummy-gegevens.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Stap 3: Het PDF-document en de tabel maken
We maken een instantie van Document en voegen een pagina toe aan dit document. Vervolgens maken we een Tabelinstantie om onze tabel in het PDF-document te vertegenwoordigen. We definiëren tabelkolombreedtes en randstijlen.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Stap 4: Gegevens uit de DataTable importeren in de tabel
We gebruiken de ImportDataTable-methode om de gegevens uit de DataTable te importeren in de tabel in het PDF-document.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Stap 5: De tabel aan het document toevoegen
We voegen de tabel toe aan de alineaverzameling van de documentpagina.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Stap 6: Sla het document op
Wij slaan het PDF-document op met de gegevens uit de ingesloten database.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Gefeliciteerd! U weet nu hoe u databasegegevens in een PDF-document kunt insluiten met Aspose.PDF voor .NET.

### Voorbeeldbroncode voor Integreren met database met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Voeg programmatisch 2 rijen toe aan het DataTable-object
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Documentinstantie maken
Document doc = new Document();
doc.Pages.Add();
// Initialiseert een nieuw exemplaar van de tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Kolombreedtes van de tabel instellen
table.ColumnWidths = "40 100 100 100";
// Stel de kleur van de tabelrand in als Lichtgrijs
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// De rand voor tabelcellen instellen
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Tabelobject toevoegen aan de eerste pagina van het invoerdocument
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Opslaan bijgewerkt document met tabelobject
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Conclusie
In deze tutorial hebben we geleerd hoe u gegevens uit een database kunt insluiten in een PDF-document met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om de gegevens uit uw eigen database te importeren en weer te geven in PDF-documenten. Verken de Aspose.PDF-documentatie verder om andere functies en mogelijkheden te ontdekken die deze krachtige bibliotheek biedt.

### FAQ's voor integratie met database in PDF-bestand

#### V: Kan ik Aspose.PDF voor .NET gebruiken met verschillende databasetypen, zoals MySQL, SQL Server of Oracle?

A: Ja, u kunt Aspose.PDF voor .NET gebruiken met verschillende databasetypen zoals MySQL, SQL Server, Oracle en andere. Aspose.PDF voor .NET biedt functionaliteiten om gegevens uit verschillende gegevensbronnen te lezen, waaronder databases, XML-bestanden en meer. U kunt gegevens ophalen uit het gewenste databasetype en deze vullen in een DataTable of een andere gegevensstructuur die compatibel is met Aspose.PDF voor .NET.

#### V: Hoe kan ik het uiterlijk van de tabel in het PDF-document aanpassen?

A: U kunt het uiterlijk van de tabel in het PDF-document aanpassen met behulp van verschillende eigenschappen die worden geboden door de Aspose.PDF voor .NET-bibliotheek. U kunt bijvoorbeeld verschillende randstijlen, achtergrondkleuren, lettertypestijlen en uitlijning instellen voor de tabel en de cellen ervan. Raadpleeg de Aspose.PDF voor .NET-documentatie voor meer informatie over het aanpassen van het uiterlijk van de tabel.

#### V: Is het mogelijk om hyperlinks of interactieve elementen toe te voegen aan de gegevens die uit de database zijn geïmporteerd?

A: Ja, u kunt hyperlinks of andere interactieve elementen toevoegen aan de gegevens die uit de database zijn geïmporteerd. Aspose.PDF voor .NET ondersteunt het toevoegen van hyperlinks, bladwijzers en andere interactieve elementen aan het PDF-document. U kunt de inhoud in de DataTable manipuleren voordat u deze in de tabel importeert en hyperlinks of andere interactieve functies opnemen.

#### V: Kan ik de tabel pagineren als deze een bepaald aantal rijen overschrijdt?

 A: Ja, u kunt de tabel pagineren als deze een bepaald aantal rijen overschrijdt. Om dit te bereiken, kunt u de`IsInNewPage`eigenschap van het Row-object om aan te geven dat een nieuwe pagina na een specifieke rij moet beginnen. U kunt het aantal rijen berekenen dat per pagina moet worden weergegeven en de`IsInNewPage` eigendom dienovereenkomstig.

#### V: Hoe kan ik een PDF-document met ingesloten databasegegevens exporteren naar verschillende bestandsformaten, zoals DOCX of XLSX?

A: Met Aspose.PDF voor .NET kunt u PDF-documenten converteren naar verschillende andere bestandsformaten, waaronder DOCX (Microsoft Word) en XLSX (Microsoft Excel). U kunt de Aspose.PDF voor .NET-bibliotheek gebruiken in combinatie met andere Aspose-bibliotheken zoals Aspose.Words en Aspose.Cells om dit te bereiken. Sla eerst het PDF-document op met ingesloten databasegegevens en gebruik vervolgens de betreffende Aspose-bibliotheek om het te converteren naar het gewenste bestandsformaat.