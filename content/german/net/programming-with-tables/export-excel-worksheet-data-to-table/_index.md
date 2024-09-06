---
title: Excel-Arbeitsblattdaten in Tabelle exportieren
linktitle: Excel-Arbeitsblattdaten in Tabelle exportieren
second_title: Aspose.PDF für .NET API-Referenz
description: Exportieren Sie Daten aus einem Excel-Blatt mit Aspose.PDF für .NET in eine PDF-Tabelle.
type: docs
weight: 70
url: /de/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In diesem Tutorial lernen wir, wie man Daten aus einem Excel-Arbeitsblatt exportiert und mithilfe der Aspose.PDF-Bibliothek für .NET eine Tabelle in einem PDF-Dokument erstellt. Wir gehen den Quellcode Schritt für Schritt durch und erklären jeden Abschnitt im Detail. Am Ende dieses Tutorials können Sie PDF-Dateien mit Tabellen erstellen, die Daten aus Excel-Arbeitsblättern enthalten. Legen wir los!

## Anforderungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse der Programmiersprache C#
- Auf Ihrem Computer installiertes Visual Studio
- Aspose.PDF für .NET-Bibliothek zu Ihrem Projekt hinzugefügt

## Schritt 1: Einrichten der Umgebung
Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Fügen Sie den Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu, indem Sie im Solution Explorer mit der rechten Maustaste auf Ihr Projekt klicken, „NuGet-Pakete verwalten“ auswählen und nach „Aspose.PDF“ suchen. Installieren Sie das Paket und schon kann es losgehen.

## Schritt 2: Laden des Excel-Arbeitsblatts
Im ersten Schritt unseres Codes definieren wir den Pfad zum Verzeichnis, das das Excel-Dokument enthält. Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Verzeichnispfad, in dem sich Ihre Excel-Datei befindet.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Hier verwenden wir die Aspose.Cells-Bibliothek, um die Excel-Arbeitsmappe zu laden. Achten Sie darauf, „newBook1.xlsx“ durch den Namen Ihrer Excel-Datei zu ersetzen.

## Schritt 3: Zugriff auf das Arbeitsblatt
 Als nächstes müssen wir auf das erste Arbeitsblatt in der Excel-Datei zugreifen. Dies tun wir mit dem`Worksheets` Sammlung der`Workbook` Objekt.

```csharp
// Zugriff auf das erste Arbeitsblatt in der Excel-Datei
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Wenn Ihre Excel-Datei mehrere Arbeitsblätter enthält, können Sie den Indexwert ändern`[0]` um auf ein anderes Arbeitsblatt zuzugreifen.

## Schritt 4: Daten in DataTable exportieren
 Nun exportieren wir den Inhalt des Excel-Arbeitsblatts in ein`DataTable` Objekt. Wir geben den zu exportierenden Zellbereich mit dem`ExportDataTable` Verfahren.

```csharp
// Exportieren des Inhalts von 7 Zeilen und 2 Spalten beginnend mit der 1. Zelle in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In diesem Beispiel exportieren wir alle Zeilen und Spalten von der ersten Zelle (0, 0) bis zur letzten Zelle im Arbeitsblatt. Legen Sie den entsprechenden Bereich entsprechend Ihren Anforderungen fest.

## Schritt 5: Erstellen eines PDF-Dokuments
Jetzt erstellen wir mit der Aspose.PDF-Bibliothek ein neues PDF-Dokument.

```csharp
// Instanziieren einer Dokumentinstanz
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Dadurch wird ein leeres PDF-Dokument erstellt, in das wir Inhalte einfügen können.

## Schritt 6: Hinzufügen einer Seite und einer Tabelle
Um die Daten in einem Tabellenformat anzuzeigen, müssen wir dem PDF-Dokument eine Seite und eine Tabelle hinzufügen.

```csharp
// Erstellen einer Seite in der Dokumentinstanz
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Erstellen eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie das Tabellenobjekt in die Absatzsammlung des Abschnitts ein.
sec1.Paragraphs.Add(tab1);
```

Hier erstellen wir eine neue Seite und ein Tabellenobjekt. Anschließend fügen wir die Tabelle zur Absatzsammlung der Seite hinzu.

## Schritt 7: Festlegen der Tabelleneigenschaften
Bevor wir die Daten importieren, müssen wir einige Eigenschaften der Tabelle festlegen, beispielsweise Spaltenbreiten und Standardzellenränder.

```csharp
// Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "40 100 100";

// Festlegen des Standardzellenrahmens der Tabelle mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In diesem Beispiel legen wir die Spaltenbreiten auf 40, 100 und 100 Einheiten fest. Passen Sie die Werte basierend auf Ihren Daten an. Wir legen auch den Standardzellenrahmen so fest, dass auf allen Seiten jeder Zelle Rahmen angezeigt werden.

## Schritt 8: Daten in die Tabelle importieren
 Nun importieren wir die Daten aus dem`DataTable` Objekt in die Tabelle mit dem`ImportDataTable` Verfahren.

```csharp
// Importieren Sie Daten aus der oben erstellten DataTable in das Table-Objekt.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Hier geben wir den Bereich der zu importierenden Zeilen und Spalten an. In diesem Beispiel importieren wir alle Zeilen und Spalten aus dem`dataTable` Objekt.

## Schritt 9: Formatieren der Tabelle
Um das Erscheinungsbild der Tabelle zu verbessern, können wir Formatierungen auf bestimmte Zellen oder Zeilen anwenden. In diesem Schritt formatieren wir die erste Zeile und die nachfolgenden Zeilen der Tabelle.

```csharp
// Holen Sie sich die 1. Zeile aus der Tabelle
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatieren Sie die erste Zeile
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Legen Sie die Hintergrundfarbe der Zellen in der ersten Zeile fest
     curCell.BackgroundColor = Color.Blue;// Legen Sie das Gesicht für die Zellen in der ersten Zeile fest
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Legen Sie die Schriftfarbe der Zellen in der ersten Zeile fest
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Festlegen der Textausrichtung für die Zellen in der ersten Zeile
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatives Zeilenformat
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Legen Sie die Hintergrundfarbe der Zellen in abwechselnden Zeilen fest
         curCell.BackgroundColor = Color.Gray;
        
         // Legen Sie die Textfarbe der Zellen in abwechselnden Zeilen fest
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Hier durchlaufen wir die Zellen in der ersten Zeile und legen deren Hintergrundfarbe, Schriftart, Schriftfarbe und Textausrichtung fest. Anschließend durchlaufen wir alle Zellen in den anderen Zeilen und legen deren Hintergrund- und Textfarbe fest.

## Schritt 10: Speichern des PDF-Dokuments
Abschließend speichern wir das PDF-Dokument am angegebenen Ort.

```csharp
// Speichern Sie das PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch den gewünschten Verzeichnispfad und Dateinamen für die PDF-Ausgabedatei ersetzen.

### Beispielquellcode zum Exportieren von Excel-Arbeitsblattdaten in eine Tabelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Zugriff auf das erste Arbeitsblatt in der Excel-Datei
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportieren des Inhalts von 7 Zeilen und 2 Spalten beginnend mit der 1. Zelle in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instanziieren einer Dokumentinstanz
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Erstellen einer Seite in der Dokumentinstanz
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Erstellen eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie das Tabellenobjekt in die Absatzsammlung des Abschnitts ein.
sec1.Paragraphs.Add(tab1);

// Legen Sie die Spaltenbreiten der Tabelle fest. Wir müssen die Spaltenanzahl manuell angeben.
// Da das aktuelle Excel-Arbeitsblatt drei Spalten hat, geben wir die gleiche Anzahl an
tab1.ColumnWidths = "40 100 100";

// Festlegen des Standardzellenrahmens der Tabelle mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importieren Sie Daten aus der oben erstellten DataTable in das Table-Objekt.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Holen Sie sich die 1. Zeile aus der Tabelle
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Durchlaufen Sie alle Zellen in der 1. Zeile und setzen Sie deren Hintergrundfarbe auf Blau
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Legen Sie den Hintergrund aller Zellen in der 1. Zeile der Tabelle fest.
	curCell.BackgroundColor = Color.Blue;
	// Legen Sie die Schriftart für die Zellen der 1. Zeile der Tabelle fest.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Legen Sie die Schriftfarbe aller Zellen in der 1. Zeile der Tabelle fest.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Stellen Sie die Textausrichtung für die Zellen der 1. Zeile auf „Zentriert“ ein.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Durchlaufen Sie alle Zellen in der 1. Zeile und setzen Sie deren Hintergrundfarbe auf Blau
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Legen Sie die Hintergrundfarbe aller Zellen außer der ersten Zeile fest.
		curCell.BackgroundColor = Color.Gray;
		// Legen Sie die Textfarbe aller Zellen außer der 1. Zeile fest.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Speichern Sie das PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.PDF für .NET-Bibliothek Daten aus einem Excel-Arbeitsblatt in eine PDF-Tabelle exportiert. Wir haben den schrittweisen Prozess des Ladens des Excel-Arbeitsblatts, des Erstellens eines PDF-Dokuments, des Hinzufügens einer Tabelle, des Importierens von Daten und des Formatierens der Tabelle behandelt. Sie können jetzt programmgesteuert PDF-Dateien mit Tabellen erstellen, die Excel-Daten enthalten.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Exportierens von Excel-Arbeitsblattdaten in eine PDF-Tabelle?

A: Durch das Exportieren von Excel-Arbeitsblattdaten in eine PDF-Tabelle können Sie die Daten in einem strukturierten und organisierten Format präsentieren. Sie können PDF-Dateien mit Tabellen erstellen, die Daten aus Excel-Arbeitsblättern enthalten, wodurch das Teilen und Aufbewahren von Informationen in einem portablen Dokumentformat einfacher wird.

#### F: Kann ich das Erscheinungsbild der PDF-Tabelle anpassen?

A: Ja, Sie können das Erscheinungsbild der PDF-Tabelle mithilfe verschiedener Eigenschaften anpassen, die von Aspose.PDF für .NET bereitgestellt werden. Im bereitgestellten C#-Quellcode können Sie die Spaltenbreiten, Zellränder, Textausrichtung, Schriftstil und mehr an Ihre spezifischen Anforderungen anpassen.

#### F: Wie gehe ich mit Excel-Dateien mit mehreren Arbeitsblättern um?

 A: Im bereitgestellten C#-Code haben wir über den Index auf das erste Arbeitsblatt in der Excel-Datei zugegriffen.`[0]` Wenn Ihre Excel-Datei mehrere Arbeitsblätter enthält, können Sie darauf zugreifen, indem Sie den Indexwert entsprechend ändern, z. B.`[1]` für das zweite Arbeitsblatt oder`[2]` für das dritte Arbeitsblatt.

#### F: Kann ich bestimmten Zeilen oder Zellen in der PDF-Tabelle eine andere Formatierung zuweisen?

A: Ja, Sie können bestimmten Zeilen oder Zellen in der PDF-Tabelle unterschiedliche Formatierungen zuweisen. Im bereitgestellten C#-Quellcode haben wir gezeigt, wie Sie die erste Zeile und die nachfolgenden Zeilen unterschiedlich formatieren können, indem Sie deren Hintergrundfarbe, Schriftstil und Schriftfarbe ändern. Sie können bei Bedarf ähnliche Formatierungstechniken auf beliebige bestimmte Zeilen oder Zellen anwenden.

#### F: Ist Aspose.PDF für .NET die einzige Bibliothek, die den Export von Excel-Daten in eine PDF-Tabelle ermöglicht?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek für die Arbeit mit PDF-Dokumenten in .NET-Anwendungen. Obwohl möglicherweise auch andere Bibliotheken verfügbar sind, bietet Aspose.PDF für .NET eine breite Palette an Funktionen und Möglichkeiten zum Generieren, Bearbeiten und Exportieren von PDF-Dateien mit Tabellen aus Excel-Daten und ist daher eine beliebte Wahl für solche Aufgaben.