---
title: Tabellenumbruch festlegen
linktitle: Tabellenumbruch festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Tabellenumbrüche in einem PDF-Dokument bestimmen.
type: docs
weight: 60
url: /de/net/programming-with-tables/determine-table-break/
---

In diesem Tutorial lernen wir, wie man mit Aspose.PDF für .NET Tabellenumbrüche in einem PDF-Dokument ermittelt. Wir erklären Ihnen Schritt für Schritt den Quellcode in C#. Am Ende dieses Tutorials erfahren Sie, wie Sie feststellen können, ob eine Tabelle über die Seitenränder hinausgeht. Lasst uns beginnen!

## Schritt 1: Einrichten der Umgebung
Stellen Sie zunächst sicher, dass Sie Ihre C#-Entwicklungsumgebung mit Aspose.PDF für .NET eingerichtet haben. Fügen Sie den Verweis zur Bibliothek hinzu und importieren Sie die erforderlichen Namespaces.

## Schritt 2: Erstellen des PDF-Dokuments
 In diesem Schritt erstellen wir ein neues`Document` Objekt zur Darstellung des PDF-Dokuments.

```csharp
pdf-Document = new Document();
```

Dieses Dokument wird zum Hinzufügen von Abschnitten und Tabellen verwendet.

## Schritt 3: Einen Abschnitt und eine Tabelle hinzufügen
Jetzt fügen wir unserem PDF-Dokument einen Abschnitt hinzu und erstellen in diesem Abschnitt eine Tabelle.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Für die Tabelle geben wir außerdem einen oberen Rand von 300 Punkten vor. Sie können diesen Wert Ihren Bedürfnissen entsprechend anpassen.

## Schritt 4: Tabellenaufbau
In diesem Schritt konfigurieren wir Tabelleneigenschaften wie Spaltenbreiten und Ränder.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Hier definieren wir die Breite der Tabellenspalten und der Zellränder. Sie können diese Werte nach Ihren Wünschen anpassen.

## Schritt 5: Fügen Sie der Tabelle Zeilen und Zellen hinzu
Jetzt erstellen wir mithilfe einer Schleife Zeilen und Zellen in der Tabelle.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Hier erstellen wir 17 Zeilen in der Tabelle und fügen jeder Zeile drei Zellen hinzu. Sie können die Schnalle je nach Bedarf anpassen.

## Schritt 6: Tabellenumbrüche festlegen
Jetzt ermitteln wir, ob die Tabelle die Seitenränder überschreitet, indem wir die Höhe der Seite mit der Gesamthöhe der Objekte in der Tabelle vergleichen.

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

Stellen Sie sicher, dass Sie das richtige Dokumentverzeichnis angeben. Die resultierende PDF-Datei wird mit den ermittelten Tabellenumbrüchen gespeichert.

### Beispielquellcode für „Determine Table Break“ mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie eine Objekt-PDF-Klasse
Document pdf = new Document();
// Fügen Sie den Abschnitt zur Abschnittssammlung des PDF-Dokuments hinzu
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(table1);
// Mit den Spaltenbreiten der Tabelle festlegen
table1.ColumnWidths = "100 100 100";
// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Legen Sie den Tabellenrand mithilfe eines anderen benutzerdefinierten BorderInfo-Objekts fest
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Legen Sie den Standard-Zellenabstand für das MarginInfo-Objekt fest
table1.DefaultCellPadding = margin;
// Wenn Sie den Zähler auf 17 erhöhen, wird die Tabelle unterbrochen
// Denn es lässt sich über diese Seite nicht mehr unterbringen
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Rufen Sie die Informationen zur Seitenhöhe ab
float PageHeight = (float)pdf.PageInfo.Height;
// Erhalten Sie Informationen zur Gesamthöhe des oberen und unteren Rands der Seite.
// Tischplattenrand und Tischhöhe.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Zeigt Seitenhöhe, Tabellenhöhe, Tischoberseitenrand und Seitenanfang an
// Und Informationen zum unteren Rand
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//Überprüfen Sie, ob wir die Summe aus oberem Seitenrand + unterem Seitenrand abziehen
// + Tabellenoberseitenrand und Tabellenhöhe von Seitenhöhe und weniger
// Als 10 (eine durchschnittliche Zeile kann größer als 10 sein)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Wenn der Wert kleiner als 10 ist, wird die Meldung angezeigt.
	// Das zeigt, dass keine weitere Zeile platziert werden kann und wenn wir eine neue hinzufügen
	// Zeile, Tabelle wird kaputt gehen. Dies hängt vom Wert der Zeilenhöhe ab.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Speichern Sie das PDF-Dokument
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET Tabellenumbrüche in einem PDF-Dokument ermittelt. Mit dieser Schritt-für-Schritt-Anleitung können Sie in Ihren eigenen C#-Projekten prüfen, ob eine Tabelle die Seitenränder überschreitet.