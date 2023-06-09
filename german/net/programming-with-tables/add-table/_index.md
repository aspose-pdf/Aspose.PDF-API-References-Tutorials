---
title: Tabelle hinzufügen
linktitle: Tabelle hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Tabellen zu Ihren PDF-Dokumenten hinzu.
type: docs
weight: 40
url: /de/net/programming-with-tables/add-table/
---

Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und umzuwandeln. In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens einer Tabelle zu einem PDF-Dokument mit Aspose.PDF für .NET. Wir erklären jeden Schritt des bereitgestellten Code-Snippets und stellen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, die Funktionalität in Ihren eigenen Projekten zu verstehen und zu implementieren.

## Einführung

PDF-Dokumente werden häufig zum Teilen und Speichern von Informationen in einem tragbaren Format verwendet. Durch das Hinzufügen von Tabellen zu PDF-Dokumenten kann deren visuelles Erscheinungsbild verbessert und die Datenpräsentation organisierter und strukturierter gestaltet werden. Aspose.PDF für .NET bietet eine bequeme Möglichkeit, Tabellen zu vorhandenen PDF-Dokumenten hinzuzufügen oder neue von Grund auf zu erstellen.

## Was ist Aspose.PDF für .NET?

Aspose.PDF für .NET ist eine leistungsstarke und funktionsreiche Bibliothek, die es .NET-Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren. Es bietet eine breite Palette an Funktionen, darunter das Erstellen von PDF-Dateien von Grund auf, das Ändern vorhandener PDF-Dokumente, das Zusammenführen oder Teilen von PDF-Dateien, das Hinzufügen von Text, Bildern und Tabellen, das Extrahieren von Daten aus PDFs und vieles mehr. Mit Aspose.PDF für .NET können Entwickler komplexe PDF-bezogene Aufgaben automatisieren und hochwertige PDF-Lösungen bereitstellen.

## Hinzufügen einer Tabelle zu einem PDF-Dokument

Um mit Aspose.PDF für .NET eine Tabelle zu einem PDF-Dokument hinzuzufügen, befolgen Sie die folgende Schritt-für-Schritt-Anleitung:

## Schritt 1: Laden des Quell-PDF-Dokuments

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Der obige Codeausschnitt lädt das Quell-PDF-Dokument, zu dem Sie die Tabelle hinzufügen möchten. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrer PDF-Datei angeben.

## Schritt 2: Initialisieren einer neuen Instanz der Tabelle

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In diesem Schritt erstellen wir eine neue Instanz der Table-Klasse, die eine Tabelle in einem PDF-Dokument darstellt.

## Schritt 3: Festlegen der Tabellenrandfarbe

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Hier legen wir die Rahmenfarbe für die Tabelle mithilfe der BorderInfo-Klasse fest. Sie können den Rahmenstil, die Breite und die Farbe entsprechend Ihren Anforderungen anpassen.

## Schritt 4: Festlegen des Rahmens für Tabellenzellen

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Wir legen auch den Rahmen für Tabellenzellen fest, indem wir die Eigenschaft DefaultCellBorder des Tabellenobjekts verwenden. Dadurch wird sichergestellt, dass jede Zelle in der Tabelle den angegebenen Rahmenstil, die angegebene Breite und die angegebene Farbe aufweist.

## Schritt 5: Zeilen und Zellen zur Tabelle hinzufügen

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

In diesem Schritt erstellen wir eine Schleife, um der Tabelle 10 Zeilen hinzuzufügen. Innerhalb jeder Zeile fügen wir drei Zellen mit Beispieldaten hinzu. Sie können den Code ändern, um Zeilen und Zellen entsprechend Ihren spezifischen Anforderungen hinzuzufügen.

## Schritt 6: Hinzufügen des Tabellenobjekts zum Dokument

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Speichern Sie das aktualisierte Dokument, das das Tabellenobjekt enthält
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Schließlich fügen wir das Tabellenobjekt zur ersten Seite des PDF-Dokuments hinzu, indem wir die Paragraphs-Sammlung der entsprechenden Seite verwenden.

### Beispielquellcode für das Hinzufügen einer Tabelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie das PDF-Quelldokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Initialisiert eine neue Instanz der Tabelle
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Legen Sie die Rahmenfarbe der Tabelle auf „LightGray“ fest
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Legen Sie den Rahmen für Tabellenzellen fest
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Erstellen Sie eine Schleife, um 10 Zeilen hinzuzufügen
for (int row_count = 1; row_count < 10; row_count++)
{
	// Zeile zur Tabelle hinzufügen
	Aspose.Pdf.Row row = table.Rows.Add();
	// Tabellenzellen hinzufügen
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// Tabellenobjekt zur ersten Seite des Eingabedokuments hinzufügen
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// Speichern Sie das aktualisierte Dokument, das das Tabellenobjekt enthält
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Abschluss

In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess zum Hinzufügen einer Tabelle zu einem PDF-Dokument mit Aspose.PDF für .NET erklärt. Wir haben das Laden des PDF-Quelldokuments, das Initialisieren einer neuen Instanz der Table-Klasse, das Festlegen der Tabellenrahmenfarbe und der Zellränder, das Hinzufügen von Zeilen und Zellen zur Tabelle und das Hinzufügen des Tabellenobjekts zum Dokument behandelt. Wenn Sie dieser Anleitung folgen, können Sie Tabellen ganz einfach programmgesteuert in Ihre PDF-Dokumente integrieren und diese an Ihre spezifischen Bedürfnisse anpassen.