---
title: Tabelle zur PDF-Datei hinzufügen
linktitle: Tabelle zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach Tabellen in PDF-Dateien ein.
type: docs
weight: 40
url: /de/net/programming-with-tables/add-table/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, mit der Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und transformieren können. In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens einer Tabelle in eine PDF-Datei mit Aspose.PDF für .NET. Wir erklären jeden Schritt des bereitgestellten Codeausschnitts und bieten eine umfassende Anleitung, die Ihnen hilft, die Funktionalität zu verstehen und in Ihren eigenen Projekten zu implementieren.

## Einführung

PDF-Dokumente werden häufig zum Teilen und Aufbewahren von Informationen in einem portablen Format verwendet. Das Hinzufügen von Tabellen zu PDF-Dokumenten kann deren visuelles Erscheinungsbild verbessern und die Datenpräsentation übersichtlicher und strukturierter gestalten. Aspose.PDF für .NET bietet eine bequeme Möglichkeit, Tabellen zu vorhandenen PDF-Dokumenten hinzuzufügen oder von Grund auf neue zu erstellen.

## Was ist Aspose.PDF für .NET?

Aspose.PDF für .NET ist eine leistungsstarke und funktionsreiche Bibliothek, mit der .NET-Entwickler PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Sie bietet eine breite Palette an Funktionen, darunter das Erstellen von PDF-Dateien von Grund auf, das Ändern vorhandener PDF-Dokumente, das Zusammenführen oder Aufteilen von PDF-Dateien, das Hinzufügen von Text, Bildern und Tabellen, das Extrahieren von Daten aus PDFs und vieles mehr. Mit Aspose.PDF für .NET können Entwickler komplexe PDF-bezogene Aufgaben automatisieren und hochwertige PDF-Lösungen bereitstellen.

## Hinzufügen einer Tabelle zu einem PDF-Dokument

Um mit Aspose.PDF für .NET einem PDF-Dokument eine Tabelle hinzuzufügen, folgen Sie der folgenden Schritt-für-Schritt-Anleitung:

## Schritt 1: Laden des PDF-Quelldokuments

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

Der obige Codeausschnitt lädt das Quell-PDF-Dokument, dem Sie die Tabelle hinzufügen möchten. Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrer PDF-Datei angeben.

## Schritt 2: Initialisieren einer neuen Instanz der Tabelle

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

In diesem Schritt erstellen wir eine neue Instanz der Table-Klasse, die eine Tabelle in einem PDF-Dokument darstellt.

## Schritt 3: Festlegen der Tabellenrahmenfarbe

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Hier legen wir die Rahmenfarbe für die Tabelle mithilfe der Klasse BorderInfo fest. Sie können den Rahmenstil, die Breite und die Farbe nach Ihren Anforderungen anpassen.

## Schritt 4: Rahmen für Tabellenzellen festlegen

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

Wir legen auch den Rahmen für Tabellenzellen mithilfe der Eigenschaft DefaultCellBorder des Tabellenobjekts fest. Dadurch wird sichergestellt, dass jede Zelle in der Tabelle den angegebenen Rahmenstil, die angegebene Breite und Farbe hat.

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
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

Abschließend fügen wir das Tabellenobjekt der ersten Seite des PDF-Dokuments hinzu und verwenden dazu die Paragraphs-Sammlung der entsprechenden Seite.

### Beispielquellcode zum Hinzufügen einer Tabelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Quell-PDF-Dokument laden
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// Initialisiert eine neue Instanz der Tabelle
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Stellen Sie die Tabellenrahmenfarbe auf Hellgrau ein
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Festlegen der Rahmen für Tabellenzellen
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
// Aktualisiertes Dokument mit Tabellenobjekt speichern
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## Abschluss

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET eine Tabelle zu einem PDF-Dokument hinzufügen. Wir haben das Laden des PDF-Quelldokuments, das Initialisieren einer neuen Instanz der Klasse Table, das Festlegen der Tabellenrahmenfarbe und der Zellenränder, das Hinzufügen von Zeilen und Zellen zur Tabelle und das Hinzufügen des Tabellenobjekts zum Dokument behandelt. Wenn Sie dieser Anleitung folgen, können Sie Tabellen problemlos programmgesteuert in Ihre PDF-Dokumente integrieren und sie Ihren spezifischen Anforderungen entsprechend anpassen.

### FAQs zum Hinzufügen einer Tabelle in eine PDF-Datei

#### F: Kann ich der Tabelle weitere Spalten hinzufügen?

A: Ja, Sie können der Tabelle weitere Spalten hinzufügen, indem Sie die Anzahl der Zellen erhöhen, die jeder Zeile hinzugefügt werden. Im angegebenen Beispiel hat jede Zeile drei Zellen, die drei Spalten darstellen. Sie können jeder Zeile weitere Zellen hinzufügen, um zusätzliche Spalten hinzuzufügen.

#### F: Wie kann ich das Erscheinungsbild der Tabelle, beispielsweise Schriftgröße und -stil, ändern?

 A: Sie können das Erscheinungsbild der Tabelle, einschließlich Schriftgröße und -stil, anpassen, indem Sie Eigenschaften auf der`Aspose.Pdf.Table` Und`Aspose.Pdf.TextFragment` Objekte. Sie können beispielsweise die`DefaultCellTextState` , um die Schrifteigenschaften des Textes in den Tabellenzellen zu ändern.

#### F: Ist es möglich, Zellen in der Tabelle zusammenzuführen?

 A: Ja, Sie können Zellen in der Tabelle verbinden, indem Sie`MergeCells` Methode der`Aspose.Pdf.Row` Klasse. Dadurch können Sie Zellen erstellen, die sich über mehrere Zeilen und Spalten erstrecken.

#### F: Kann ich den Tabellenzellen Bilder oder andere Inhalte hinzufügen?

A: Ja, Sie können den Tabellenzellen verschiedene Arten von Inhalten hinzufügen, darunter Bilder, Text, Hyperlinks und mehr. Sie können die entsprechenden Klassen von Aspose.PDF für .NET verwenden, um den Zellen verschiedene Arten von Inhalten hinzuzufügen.

#### F: Ist Aspose.PDF für .NET mit .NET 5.0 oder späteren Versionen kompatibel?

A: Ja, Aspose.PDF für .NET ist mit .NET 5.0 und späteren Versionen kompatibel. Es unterstützt verschiedene .NET-Plattformen, darunter .NET Framework, .NET Core und .NET 5.0+.