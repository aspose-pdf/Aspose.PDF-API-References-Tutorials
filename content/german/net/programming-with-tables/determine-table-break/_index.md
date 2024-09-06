---
title: Tabellenumbruch in PDF-Datei bestimmen
linktitle: Tabellenumbruch in PDF-Datei bestimmen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Tabellenumbrüche in PDF-Dateien bestimmen.
type: docs
weight: 60
url: /de/net/programming-with-tables/determine-table-break/
---
In diesem Tutorial lernen wir, wie man Tabellenumbrüche in PDF-Dateien mit Aspose.PDF für .NET bestimmt. Wir erklären den Quellcode in C# Schritt für Schritt. Am Ende dieses Tutorials wissen Sie, wie Sie feststellen, ob eine Tabelle die Seitenränder überschreitet. Fangen wir an!

## Schritt 1: Einrichten der Umgebung
Stellen Sie zunächst sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Fügen Sie den Verweis auf die Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen des PDF-Dokuments
 In diesem Schritt erstellen wir ein neues`Document` Objekt zur Darstellung des PDF-Dokuments.

```csharp
pdf-Document = new Document();
```

Dieses Dokument wird zum Hinzufügen von Abschnitten und Tabellen verwendet.

## Schritt 3: Einen Abschnitt und eine Tabelle hinzufügen
Jetzt fügen wir unserem PDF-Dokument einen Abschnitt hinzu und erstellen innerhalb dieses Abschnitts eine Tabelle.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Außerdem legen wir für die Tabelle einen oberen Rand von 300 Punkten fest. Diesen Wert können Sie nach Ihren Wünschen anpassen.

## Schritt 4: Tabellenaufbau
In diesem Schritt konfigurieren wir Tabelleneigenschaften wie Spaltenbreiten und Ränder.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Hier legen wir die Breite der Tabellenspalten und der Zellränder fest. Diese Werte können Sie nach Ihren Wünschen anpassen.

## Schritt 5: Zeilen und Zellen zur Tabelle hinzufügen
Nun erstellen wir mithilfe einer Schleife Zeilen und Zellen in der Tabelle.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Hier erstellen wir 17 Zeilen in der Tabelle und fügen jeder Zeile drei Zellen hinzu. Sie können die Schnalle nach Ihren Wünschen anpassen.

## Schritt 6: Tabellenumbrüche festlegen
Nun ermitteln wir, ob die Tabelle die Seitenränder überschreitet, indem wir die Seitenhöhe mit der Gesamthöhe der Objekte in der Tabelle vergleichen.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Wir berechnen die Höhe der Seite und die Gesamthöhe der Objekte unter Berücksichtigung der Ränder. Wenn die Differenz 10 oder weniger beträgt, überschreitet die Tabelle die Seitenränder.

## Schritt 7: Speichern des PDF-Dokuments
Abschließend speichern wir das PDF-Dokument mit den Ergebnissen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Achten Sie darauf, das richtige Dokumentverzeichnis anzugeben. Die resultierende PDF-Datei wird mit den ermittelten Tabellenumbrüchen gespeichert.

### Beispielquellcode zum Bestimmen des Tabellenumbruchs mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren einer Objekt-PDF-Klasse
Document pdf = new Document();
// Fügen Sie den Abschnitt zur Abschnittssammlung des PDF-Dokuments hinzu
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
page.Paragraphs.Add(table1);
// Mit Spaltenbreiten der Tabelle festlegen
table1.ColumnWidths = "100 100 100";
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Festlegen des Tabellenrahmens mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Festlegen der Standardzellenpolsterung auf das MarginInfo-Objekt
table1.DefaultCellPadding = margin;
// Wenn Sie den Zähler auf 17 erhöhen, bricht der Tisch zusammen
// Weil es auf dieser Seite nicht mehr Platz findet
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Informationen zur Seitenhöhe abrufen
float PageHeight = (float)pdf.PageInfo.Height;
// Erhalten Sie die Gesamthöheninformationen für den oberen und unteren Seitenrand.
// Tischplattenrand und Tischhöhe.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Anzeigeseitenhöhe, Tabellenhöhe, oberer Tabellenrand und Seitenanfang
// Und Informationen zum unteren Rand
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Überprüfen Sie, ob wir die Summe aus Seitenrand oben + Seitenrand unten abziehen
// + Tabellenrand und Tabellenhöhe von Seitenhöhe und weniger
// Als 10 (eine durchschnittliche Zeile kann größer als 10 sein)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Wenn der Wert kleiner als 10 ist, wird die Meldung angezeigt.
	//Das zeigt, dass keine weitere Zeile platziert werden kann und wenn wir neue hinzufügen
	// Zeile, Tabelle wird umgebrochen. Dies hängt vom Zeilenhöhenwert ab.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Speichern Sie das PDF-Dokument
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Tabellenumbrüche in einem PDF-Dokument mit Aspose.PDF für .NET bestimmt. Mit dieser Schritt-für-Schritt-Anleitung können Sie in Ihren eigenen C#-Projekten überprüfen, ob eine Tabelle die Seitenränder überschreitet.

### FAQs zum Festlegen des Tabellenumbruchs in einer PDF-Datei

#### F: Was ist der Zweck der Festlegung von Tabellenumbrüchen in einem PDF-Dokument?

A: Der Zweck der Ermittlung von Tabellenumbrüchen in einem PDF-Dokument besteht darin, zu prüfen, ob die Tabelle die Seitenränder überschreitet. Dadurch wird sichergestellt, dass der Inhalt der Tabelle innerhalb des verfügbaren Seitenraums korrekt angezeigt wird. Durch die Erkennung von Tabellenumbrüchen können Sie den Inhaltsüberlauf bewältigen und das Tabellenlayout entsprechend anpassen.

#### F: Wie kann ich den oberen Rand der Tabelle anpassen?

 A: Im bereitgestellten C#-Quellcode können Sie den oberen Rand der Tabelle anpassen, indem Sie den Wert des`table1.Margin.Top`-Eigenschaft. Erhöhen oder verringern Sie den Wert nach Bedarf, um den gewünschten oberen Rand für die Tabelle festzulegen.

#### F: Kann ich das Erscheinungsbild der Tabelle, beispielsweise Zellenfarben und Schriftgröße, anpassen?

A: Ja, Sie können das Erscheinungsbild der Tabelle und ihrer Zellen mithilfe verschiedener Eigenschaften und Methoden anpassen, die von Aspose.PDF für .NET bereitgestellt werden. Sie können beispielsweise die Zellenhintergrundfarben, die Schriftgröße, die Schriftfamilie, die Textausrichtung und mehr ändern. Weitere Informationen zum Anpassen des Tabellenerscheinungsbilds finden Sie in der offiziellen Dokumentation.

#### F: Was passiert, wenn die Tabelle die Seitenränder überschreitet?

A: Wenn die Tabelle über die Seitenränder hinausragt, kann es dazu kommen, dass der Inhalt abgeschnitten oder überlappt wird, wodurch das PDF-Dokument schlechter lesbar und übersichtlich wird. Indem Sie Tabellenumbrüche erkennen und den Überlauf behandeln, können Sie sicherstellen, dass der Inhalt innerhalb des verfügbaren Seitenbereichs weiterhin richtig angezeigt wird.

#### F: Kann ich Tabellenumbrüche für mehrere Tabellen im selben PDF-Dokument festlegen?

A: Ja, Sie können Tabellenumbrüche für mehrere Tabellen im selben PDF-Dokument festlegen. Wiederholen Sie einfach die Schritte für jede Tabelle, die Sie analysieren möchten, und passen Sie das Tabellenlayout nach Bedarf an, um einen Inhaltsüberlauf zu vermeiden.