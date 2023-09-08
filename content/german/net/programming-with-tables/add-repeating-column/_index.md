---
title: Wiederholende Spalte im PDF-Dokument hinzufügen
linktitle: Wiederholende Spalte im PDF-Dokument hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine sich wiederholende Spalte in ein PDF-Dokument einfügen.
type: docs
weight: 20
url: /de/net/programming-with-tables/add-repeating-column/
---
In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET eine sich wiederholende Spalte in ein PDF-Dokument einfügt. Wir erklären Ihnen Schritt für Schritt den Quellcode in C#. Am Ende dieses Tutorials erfahren Sie, wie Sie eine Tabelle mit einer sich wiederholenden Spalte in einem PDF-Dokument erstellen. Lasst uns beginnen!

## Schritt 1: Einrichten der Umgebung
Stellen Sie zunächst sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Fügen Sie den Verweis zur Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen des PDF-Dokuments
In diesem Schritt erstellen wir ein neues PDF-Dokument.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Wir haben ein leeres PDF-Dokument erstellt, dem wir Inhalte hinzufügen können.

## Schritt 3: Erstellen der Tabellen
In diesem Schritt erstellen wir eine Haupttabelle (`outerTable`) und eine verschachtelte Tabelle (`mytable`), der in der Spalte wiederholt wird.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Wir haben Tabelleneigenschaften wie die Spaltenbreite und den Umbruchmodus für verschachtelte Tabellen angegeben.

## Schritt 4: Hinzufügen der Tabellen zum Dokument
Nun fügen wir die erstellten Tabellen dem PDF-Dokument hinzu.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Wir fügen zuerst die Haupttabelle hinzu (`outerTable`) zum PDF-Dokument. Als nächstes fügen wir die verschachtelte Tabelle hinzu (`mytable` ) als Absatz in einer Zelle in der Haupttabelle. Wir geben auch die Anzahl der wiederholten Spalten an`mytable` (in diesem Beispiel 5 Spalten).

## Schritt 5: Überschriften und Zeilen hinzufügen
Jetzt fügen wir die Überschriften und Zeilen zur Tabelle hinzu.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Fügen Sie hier weitere Header hinzu

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Fügen Sie hier die anderen Spalten hinzu
}
```

Wir fügen zunächst die Überschriften zur ersten Zeile der Tabelle hinzu (`headerRow`). Dann fügen wir die Datenzeilen aus einer Schleife hinzu. In diesem Beispiel fügen wir 6 Datenzeilen hinzu.

## Schritt 6: Speichern des PDF-Dokuments
Abschließend speichern wir das PDF-Dokument in der angegebenen Datei.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Stellen Sie sicher, dass Sie das richtige Verzeichnis und den richtigen Dateinamen angeben, um die ausgegebene PDF-Datei zu speichern.

### Beispielquellcode zum Hinzufügen einer sich wiederholenden Spalte mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Erstellen Sie ein neues Dokument
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instanziieren Sie eine äußere Tabelle, die die gesamte Seite einnimmt
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Instanziieren Sie ein Tabellenobjekt, das in „outerTable“ verschachtelt wird und innerhalb derselben Seite umgebrochen wird
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Fügen Sie die äußere Tabelle zu den Seitenabsätzen hinzu
// Mytable zur OuterTable hinzufügen
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Kopfzeile hinzufügen
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine sich wiederholende Spalte in ein PDF-Dokument einfügt. Mit dieser Schritt-für-Schritt-Anleitung können Sie Tabellen mit sich wiederholenden Spalten in Ihren eigenen C#-Projekten erstellen.

### FAQs zum Hinzufügen einer sich wiederholenden Spalte in einem PDF-Dokument

#### F: Kann ich die Anzahl der wiederholten Spalten in der verschachtelten Tabelle anpassen?

 A: Ja, Sie können die Anzahl der wiederholten Spalten in der verschachtelten Tabelle anpassen. Im bereitgestellten Beispiel legen wir fest`mytable.RepeatingColumnsCount = 5;`, was bedeutet, dass es 5 wiederholte Spalten gibt. Sie können diesen Wert auf eine beliebige Zahl ändern.

#### F: Ist es möglich, der verschachtelten Tabelle dynamisch weitere Zeilen hinzuzufügen?

A: Ja, Sie können der verschachtelten Tabelle auf die gleiche Weise wie im Tutorial gezeigt dynamisch weitere Zeilen hinzufügen. Sie können Schleifen oder jede andere Logik verwenden, um Zeilen basierend auf Ihren Daten hinzuzufügen.

#### F: Kann ich Stile und Formatierungen auf die Tabelle und ihre Zellen anwenden?

A: Ja, Sie können mit Aspose.PDF für .NET Stile und Formatierungen auf die Tabelle und ihre Zellen anwenden. Die Bibliothek stellt verschiedene Eigenschaften und Methoden zur Verfügung, um das Erscheinungsbild der Tabelle und ihres Inhalts anzupassen.

#### F: Ist Aspose.PDF für .NET mit .NET Core kompatibel?

A: Ja, Aspose.PDF für .NET ist mit .NET Core kompatibel. Sie können es sowohl in .NET Framework- als auch in .NET Core-Anwendungen verwenden.

#### F: Kann ich diesen Ansatz verwenden, um sich wiederholende Spalten in einem vorhandenen PDF-Dokument hinzuzufügen?

A: Ja, Sie können diesen Ansatz verwenden, um sich wiederholende Spalten in einem vorhandenen PDF-Dokument hinzuzufügen. Laden Sie einfach das vorhandene Dokument mit Aspose.PDF für .NET und befolgen Sie die gleichen Schritte, um die Wiederholungsspalte zu erstellen und hinzuzufügen.