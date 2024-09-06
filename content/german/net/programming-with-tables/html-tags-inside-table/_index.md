---
title: HTML-Tags in der Tabelle in der PDF-Datei
linktitle: HTML-Tags in der Tabelle in der PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET HTML-Tags in einer Tabelle in einer PDF-Datei verwenden.
type: docs
weight: 100
url: /de/net/programming-with-tables/html-tags-inside-table/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET HTML-Tags in einer Tabelle in einem PDF-Dokument verwendet. Wir erklären den Quellcode in C# Schritt für Schritt. Am Ende dieses Tutorials wissen Sie, wie Sie HTML-Inhalte in eine Tabelle in einem PDF-Dokument einfügen. Fangen wir an!

## Schritt 1: Einrichten der Umgebung
Stellen Sie sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET konfiguriert haben. Fügen Sie den Verweis auf die Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Tabellendaten erstellen
Wir erstellen eine DataTable, die eine „Daten“-Spalte vom Typ String enthält. Anschließend fügen wir dieser DataTable Zeilen mit HTML-Inhalten hinzu.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Schritt 3: Erstellen des Dokuments und der Tabelle
Wir erstellen ein neues PDF-Dokument und fügen diesem Dokument eine Seite hinzu. Als nächstes initialisieren wir eine Instanz der Table-Klasse und legen die Tabelleneigenschaften fest.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Schritt 4: Daten in die Tabelle importieren
Wir importieren die Daten aus der DataTable mit der Methode „ImportDataTable“ in die Tabelle. Über Methodenparameter geben wir an, welcher Zeilen- und Spaltenbereich der DataTable importiert werden soll.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Schritt 5: Hinzufügen der Tabelle zum Dokument
Wir fügen die Tabelle der Dokumentseite hinzu.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Schritt 6: Speichern des Dokuments
Wir speichern das PDF-Dokument mit der Tabelle mit HTML-Inhalten.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Beispiel-Quellcode für HTML-Tags in Tabellen mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Initialisiert eine neue Instanz der Tabelle
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Spaltenbreiten der Tabelle festlegen
tableProvider.ColumnWidths = "400 50 ";
// Stellen Sie die Tabellenrahmenfarbe auf Hellgrau ein
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Festlegen der Rahmen für Tabellenzellen
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET HTML-Tags in einer Tabelle in einem PDF-Dokument verwendet. Mit dieser Schritt-für-Schritt-Anleitung können Sie mit C# HTML-Inhalte in Tabellenzellen in einem PDF-Dokument einfügen.

### FAQs zu HTML-Tags in Tabellen in PDF-Dateien

#### F: Kann ich innerhalb der Tabellenzellen andere HTML-Tags und -Attribute verwenden?

 A: Ja, Sie können verschiedene HTML-Tags und Attribute innerhalb der Tabellenzellen verwenden, wie zum Beispiel`<b>`, `<i>`, `<a>`und viele mehr. Aspose.PDF für .NET unterstützt eine breite Palette an HTML-Elementen und -Stilen, die Sie zum Formatieren des Inhalts in den Tabellenzellen verwenden können.

#### F: Kann ich CSS-Stile auf den HTML-Inhalt in den Tabellenzellen anwenden?

A: Ja, Sie können CSS-Stile auf den HTML-Inhalt in den Tabellenzellen anwenden. Aspose.PDF für .NET bietet Unterstützung für grundlegende CSS-Stile, die auf die HTML-Elemente angewendet werden können.

#### F: Ist es möglich, Bilder zusammen mit HTML-Inhalten in die Tabellenzellen einzufügen?

 A: Ja, Sie können Bilder zusammen mit HTML-Inhalten in die Tabellenzellen einfügen. Sie können HTML verwenden`<img>` Tags zum Einbinden von Bildern aus verschiedenen Quellen, wie etwa lokalen Dateien oder URLs.

#### F: Wie kann ich unterschiedliche Spaltenbreiten für die Tabelle festlegen?

 A: Sie können verschiedene Spaltenbreiten für die Tabelle festlegen mit dem`ColumnWidths` Eigenschaft der Tabelle. Die Eigenschaft nimmt eine Zeichenfolge mit durch Leerzeichen getrennten Werten an, wobei jeder Wert die Breite einer Spalte in Punkten darstellt.

#### F: Kann ich verschachtelte Tabellen innerhalb einer Zelle mit HTML-Inhalt verwenden?

A: Ja, Sie können verschachtelte Tabellen in einer Zelle mit HTML-Inhalt verwenden. Sie können separate Tabelleninstanzen erstellen und diese als Teil des HTML-Inhalts in einer Zelle hinzufügen, um den Verschachtelungseffekt zu erzielen.