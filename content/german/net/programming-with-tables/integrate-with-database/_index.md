---
title: Mit Datenbank in PDF-Datei integrieren
linktitle: Mit Datenbank in PDF-Datei integrieren
second_title: Aspose.PDF für .NET API-Referenz
description: Betten Sie mit Aspose.PDF für .NET Daten aus einer Datenbank in eine PDF-Datei ein.
type: docs
weight: 120
url: /de/net/programming-with-tables/integrate-with-database/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET Daten aus einer Datenbank in eine PDF-Datei einbettet. Wir erklären den Quellcode in C# Schritt für Schritt. Am Ende dieses Tutorials wissen Sie, wie Sie Tabellendaten aus einer Datenbank in ein PDF-Dokument importieren. Fangen wir an!

## Schritt 1: Einrichten der Umgebung
Stellen Sie sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET konfiguriert haben. Fügen Sie den Verweis auf die Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen der DataTable
Wir erstellen eine Instanz von DataTable, um die Daten darzustellen, die wir in das PDF-Dokument einbetten möchten. In diesem Beispiel erstellen wir eine DataTable mit drei Spalten: Employee_ID, Employee_Name und Gender. Außerdem fügen wir der DataTable zwei Zeilen mit Dummy-Daten hinzu.

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

## Schritt 3: Erstellen des PDF-Dokuments und der Tabelle
Wir erstellen eine Instanz von Document und fügen diesem Dokument eine Seite hinzu. Als nächstes erstellen wir eine Table-Instanz, um unsere Tabelle im PDF-Dokument darzustellen. Wir definieren die Spaltenbreiten und Rahmenstile der Tabelle.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Schritt 4: Daten aus der DataTable in die Tabelle importieren
Mit der Methode ImportDataTable importieren wir die Daten aus der DataTable in die Tabelle im PDF-Dokument.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Schritt 5: Hinzufügen der Tabelle zum Dokument
Wir fügen die Tabelle der Absatzsammlung der Dokumentseite hinzu.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Schritt 6: Speichern Sie das Dokument
Wir speichern das PDF-Dokument mit den Daten aus der eingebetteten Datenbank.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Herzlichen Glückwunsch! Sie wissen jetzt, wie Sie mit Aspose.PDF für .NET Datenbankdaten in ein PDF-Dokument einbetten.

### Beispielquellcode für die Integration mit Datenbank unter Verwendung von Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Fügen Sie dem DataTable-Objekt programmgesteuert zwei Zeilen hinzu
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
// Dokumentinstanz erstellen
Document doc = new Document();
doc.Pages.Add();
// Initialisiert eine neue Instanz der Tabelle
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Spaltenbreiten der Tabelle festlegen
table.ColumnWidths = "40 100 100 100";
// Stellen Sie die Tabellenrahmenfarbe auf Hellgrau ein
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Festlegen der Rahmen für Tabellenzellen
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Tabellenobjekt zur ersten Seite des Eingabedokuments hinzufügen
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Daten aus einer Datenbank in ein PDF-Dokument einbettet. Mit dieser Schritt-für-Schritt-Anleitung können Sie die Daten aus Ihrer eigenen Datenbank importieren und in PDF-Dokumenten anzeigen. Erkunden Sie die Aspose.PDF-Dokumentation weiter, um weitere Funktionen und Möglichkeiten dieser leistungsstarken Bibliothek zu entdecken.

### FAQs zur Integration mit Datenbank in PDF-Datei

#### F: Kann ich Aspose.PDF für .NET mit verschiedenen Datenbanktypen wie MySQL, SQL Server oder Oracle verwenden?

A: Ja, Sie können Aspose.PDF für .NET mit verschiedenen Datenbanktypen wie MySQL, SQL Server, Oracle und anderen verwenden. Aspose.PDF für .NET bietet Funktionen zum Lesen von Daten aus verschiedenen Datenquellen, einschließlich Datenbanken, XML-Dateien und mehr. Sie können Daten aus Ihrem gewünschten Datenbanktyp abrufen und in eine DataTable oder eine andere mit Aspose.PDF für .NET kompatible Datenstruktur einfügen.

#### F: Wie kann ich das Erscheinungsbild der Tabelle im PDF-Dokument anpassen?

A: Sie können das Erscheinungsbild der Tabelle im PDF-Dokument mithilfe verschiedener Eigenschaften anpassen, die von der Aspose.PDF für .NET-Bibliothek bereitgestellt werden. Sie können beispielsweise verschiedene Rahmenstile, Hintergrundfarben, Schriftarten und Ausrichtungen für die Tabelle und ihre Zellen festlegen. Weitere Informationen zum Anpassen des Tabellenaussehens finden Sie in der Aspose.PDF für .NET-Dokumentation.

#### F: Ist es möglich, den aus der Datenbank importierten Daten Hyperlinks oder interaktive Elemente hinzuzufügen?

A: Ja, Sie können den aus der Datenbank importierten Daten Hyperlinks oder andere interaktive Elemente hinzufügen. Aspose.PDF für .NET unterstützt das Hinzufügen von Hyperlinks, Lesezeichen und anderen interaktiven Elementen zum PDF-Dokument. Sie können den Inhalt in der DataTable bearbeiten, bevor Sie ihn in die Tabelle importieren, und Hyperlinks oder andere interaktive Funktionen einfügen.

#### F: Kann ich die Tabelle paginieren, wenn sie eine bestimmte Zeilenanzahl überschreitet?

A: Ja, Sie können die Tabelle paginieren, wenn sie eine bestimmte Anzahl von Zeilen überschreitet. Dazu können Sie die`IsInNewPage` Eigenschaft des Row-Objekts, um anzugeben, dass eine neue Seite nach einer bestimmten Zeile beginnen soll. Sie können die Anzahl der pro Seite anzuzeigenden Zeilen berechnen und die`IsInNewPage` Eigentum entsprechend.

#### F: Wie kann ich das PDF-Dokument mit eingebetteten Datenbankdaten in andere Dateiformate wie DOCX oder XLSX exportieren?

A: Mit Aspose.PDF für .NET können Sie PDF-Dokumente in verschiedene andere Dateiformate konvertieren, darunter DOCX (Microsoft Word) und XLSX (Microsoft Excel). Sie können die Bibliothek Aspose.PDF für .NET in Kombination mit anderen Aspose-Bibliotheken wie Aspose.Words und Aspose.Cells verwenden, um dies zu erreichen. Speichern Sie zunächst das PDF-Dokument mit eingebetteten Datenbankdaten und verwenden Sie dann die entsprechende Aspose-Bibliothek, um es in das gewünschte Dateiformat zu konvertieren.