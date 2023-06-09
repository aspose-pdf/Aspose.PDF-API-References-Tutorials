---
title: Exportieren Sie Excel-Arbeitsblattdaten in eine Tabelle
linktitle: Exportieren Sie Excel-Arbeitsblattdaten in eine Tabelle
second_title: Aspose.PDF für .NET API-Referenz
description: Exportieren Sie Daten aus einer Excel-Tabelle in eine PDF-Tabelle mit Aspose.PDF für .NET.
type: docs
weight: 70
url: /de/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Bibliothek Aspose.PDF für .NET Daten aus einem Excel-Arbeitsblatt exportieren und eine Tabelle in einem PDF-Dokument erstellen. Wir gehen den Quellcode Schritt für Schritt durch und erklären jeden Abschnitt im Detail. Am Ende dieses Tutorials werden Sie in der Lage sein, PDF-Dateien mit Tabellen zu generieren, die Daten aus Excel-Arbeitsblättern enthalten. Lass uns anfangen!

## Anforderungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Visual Studio ist auf Ihrem Computer installiert
- Aspose.PDF für .NET-Bibliothek zu Ihrem Projekt hinzugefügt

## Schritt 1: Einrichten der Umgebung
Erstellen Sie zunächst ein neues C#-Projekt in Visual Studio. Fügen Sie den Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt klicken, „NuGet-Pakete verwalten“ auswählen und nach „Aspose.PDF“ suchen. Installieren Sie das Paket und schon kann es losgehen.

## Schritt 2: Laden des Excel-Arbeitsblatts
Im ersten Schritt unseres Codes definieren wir den Pfad zu dem Verzeichnis, das das Excel-Dokument enthält. Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Verzeichnispfad, in dem sich Ihre Excel-Datei befindet.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Hier verwenden wir die Aspose.Cells-Bibliothek, um die Excel-Arbeitsmappe zu laden. Stellen Sie sicher, dass Sie „newBook1.xlsx“ durch den Namen Ihrer Excel-Datei ersetzen.

## Schritt 3: Zugriff auf das Arbeitsblatt
 Als nächstes müssen wir auf das erste Arbeitsblatt in der Excel-Datei zugreifen. Wir machen das mit dem`Worksheets` Sammlung der`Workbook` Objekt.

```csharp
// Zugriff auf das erste Arbeitsblatt in der Excel-Datei
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Wenn Ihre Excel-Datei mehrere Arbeitsblätter enthält, können Sie den Indexwert ändern`[0]` um auf ein anderes Arbeitsblatt zuzugreifen.

## Schritt 4: Daten nach DataTable exportieren
 Jetzt exportieren wir den Inhalt des Excel-Arbeitsblatts in ein`DataTable` Objekt. Wir geben den Bereich der zu exportierenden Zellen mithilfe von an`ExportDataTable` Methode.

```csharp
// Exportieren des Inhalts von 7 Zeilen und 2 Spalten beginnend mit der 1. Zelle in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In diesem Beispiel exportieren wir alle Zeilen und Spalten von der ersten Zelle (0, 0) bis zur letzten Zelle im Arbeitsblatt. Stellen Sie den passenden Bereich entsprechend Ihren Anforderungen ein.

## Schritt 5: Erstellen eines PDF-Dokuments
Jetzt erstellen wir ein neues PDF-Dokument mit der Aspose.PDF-Bibliothek.

```csharp
// Instanziieren Sie eine Dokumentinstanz
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Dadurch wird ein leeres PDF-Dokument erstellt, dem wir Inhalte hinzufügen können.

## Schritt 6: Seite und Tabelle hinzufügen
Um die Daten in einem Tabellenformat anzuzeigen, müssen wir dem PDF-Dokument eine Seite und eine Tabelle hinzufügen.

```csharp
// Erstellen Sie eine Seite in der Dokumentinstanz
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Erstellen Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie das Table-Objekt zur Absatzsammlung des Abschnitts hinzu
sec1.Paragraphs.Add(tab1);
```

Hier erstellen wir eine neue Seite und ein Tabellenobjekt. Anschließend fügen wir die Tabelle zur Absatzsammlung der Seite hinzu.

## Schritt 7: Tabelleneigenschaften festlegen
Bevor wir die Daten importieren, müssen wir einige Eigenschaften der Tabelle festlegen, wie z. B. Spaltenbreiten und Standard-Zellenränder.

```csharp
// Legen Sie die Spaltenbreiten der Tabelle fest
tab1.ColumnWidths = "40 100 100";

// Legen Sie den Standardzellenrahmen der Tabelle mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In diesem Beispiel legen wir die Spaltenbreiten auf 40, 100 und 100 Einheiten fest. Passen Sie die Werte basierend auf Ihren Daten an. Außerdem legen wir den Standard-Zellenrahmen so fest, dass auf allen Seiten jeder Zelle Ränder angezeigt werden.

## Schritt 8: Daten in die Tabelle importieren
 Jetzt importieren wir die Daten aus dem`DataTable` Objekt in die Tabelle mit dem`ImportDataTable` Methode.

```csharp
// Importieren Sie Daten aus der oben erstellten DataTable in das Table-Objekt
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Hier geben wir den Bereich der zu importierenden Zeilen und Spalten an. In diesem Beispiel importieren wir alle Zeilen und Spalten aus`dataTable` Objekt.

## Schritt 9: Formatieren der Tabelle
Um das Erscheinungsbild der Tabelle zu verbessern, können wir Formatierungen auf bestimmte Zellen oder Zeilen anwenden. In diesem Schritt formatieren wir die erste Zeile und alternative Zeilen der Tabelle.

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
    
     // Legen Sie die Textausrichtung für die Zellen in der ersten Zeile fest
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

Hier durchlaufen wir die Zellen in der ersten Zeile und legen deren Hintergrundfarbe, Schriftart, Schriftfarbe und Textausrichtung fest. Dann durchlaufen wir alle Zellen in den alternativen Zeilen und legen deren Hintergrund- und Textfarbe fest.

## Schritt 10: Speichern des PDF-Dokuments
Abschließend speichern wir das PDF-Dokument am angegebenen Ort.

```csharp
// Speichern Sie das PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch den gewünschten Verzeichnispfad und Dateinamen für die Ausgabe-PDF-Datei ersetzen.

### Beispielquellcode für den Export von Excel-Arbeitsblattdaten in eine Tabelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Zugriff auf das erste Arbeitsblatt in der Excel-Datei
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exportieren des Inhalts von 7 Zeilen und 2 Spalten beginnend mit der 1. Zelle in DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instanziieren Sie eine Dokumentinstanz
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Erstellen Sie eine Seite in der Dokumentinstanz
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Erstellen Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie das Table-Objekt zur Absatzsammlung des Abschnitts hinzu
sec1.Paragraphs.Add(tab1);

// Legen Sie die Spaltenbreiten der Tabelle fest. Wir müssen ColumnCount manuell angeben.
// Da das aktuelle Excel-Arbeitsblatt drei Spalten hat, geben wir die gleiche Anzahl an
tab1.ColumnWidths = "40 100 100";

// Legen Sie den Standardzellenrahmen der Tabelle mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importieren Sie Daten aus der oben erstellten DataTable in das Table-Objekt
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Holen Sie sich die 1. Zeile aus der Tabelle
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Durchlaufen Sie alle Zellen in der ersten Zeile und stellen Sie deren Hintergrundfarbe auf Blau ein
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Legen Sie den Hintergrund aller Zellen in der 1. Zeile der Tabelle fest.
	curCell.BackgroundColor = Color.Blue;
	// Legen Sie die Schriftart für die Zellen der ersten Zeile in der Tabelle fest.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Legen Sie die Schriftfarbe aller Zellen in der 1. Zeile der Tabelle fest.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Legen Sie die Textausrichtung für die Zellen der 1. Zeile auf „Mitte“ fest.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Durchlaufen Sie alle Zellen in der ersten Zeile und stellen Sie deren Hintergrundfarbe auf Blau ein
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Legen Sie die Hintergrundfarbe aller Zellen außer der ersten Zeile fest.
		curCell.BackgroundColor = Color.Gray;
		// Legen Sie die Textfarbe aller Zellen außer der ersten Zeile fest.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Speichern Sie das PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mithilfe der Bibliothek Aspose.PDF für .NET Daten aus einem Excel-Arbeitsblatt in eine PDF-Tabelle exportiert. Wir haben den schrittweisen Prozess des Ladens des Excel-Arbeitsblatts, des Erstellens eines PDF-Dokuments, des Hinzufügens einer Tabelle, des Importierens von Daten und des Formatierens der Tabelle behandelt. Sie können jetzt programmgesteuert PDF-Dateien mit Tabellen generieren, die Excel-Daten enthalten.