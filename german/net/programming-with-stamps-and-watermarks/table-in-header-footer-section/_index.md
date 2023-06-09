---
title: Tabelle im Kopf- und Fußzeilenbereich
linktitle: Tabelle im Kopf- und Fußzeilenbereich
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in den Kopf-/Fußzeilenbereich eines PDF-Dokuments einfügen.
type: docs
weight: 170
url: /de/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode zeigt Ihnen, wie Sie ein leeres PDF-Dokument erstellen, eine Seite hinzufügen, den Kopfzeilenabschnitt konfigurieren, eine Tabelle erstellen, Zeilen und Zellen zur Tabelle hinzufügen und schließlich das PDF-Dokument speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des PDF-Dokuments und der Seite

 Der erste Schritt besteht darin, eine Instanz davon zu erstellen`Document` Klasse und fügen Sie dem Dokument eine Seite hinzu. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren Sie ein Document-Objekt
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im PDF-Dokument
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Ersetzen Sie unbedingt „VERZEICHNIS IHRER DOKUMENTE“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

## Schritt 3: Konfigurieren des Header-Bereichs

 Jetzt konfigurieren wir den Kopfbereich des PDF-Dokuments, indem wir eine Instanz davon erstellen`HeaderFooter` Klasse. Hier ist wie:

```csharp
// Erstellen Sie einen Kopfbereich für die PDF-Datei
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definieren Sie den Kopfbereich für die Seite
page. Header = header;

// Legen Sie den oberen Rand des Kopfzeilenabschnitts fest
header. Margin. Top = 20;
```

## Schritt 4: Erstellen der Tabelle

 Jetzt erstellen wir eine Tabelle mit`Table`Klasse und fügen Sie sie der Absatzsammlung des Überschriftenabschnitts hinzu. Hier ist wie:

```csharp
// Instanziieren Sie ein Table-Objekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie die Tabelle zur Absatzsammlung des Kopfzeilenabschnitts hinzu
header.Paragraphs.Add(tab1);

// Definieren Sie die Breite der Spalten der Tabelle
tab1.ColumnWidths = "60,300";
```

Der obige Code erstellt eine Tabelle mit zwei Spalten mit der angegebenen Breite.

## Schritt 5: Fügen Sie der Tabelle Zeilen und Zellen hinzu

 Jetzt fügen wir der Tabelle mithilfe von Zeilen und Zellen hinzu`Row` Klasse und die`Cell` Klasse. Hier ist wie:

```csharp
// Erstellen Sie eine Zeile in der Tabelle und fügen Sie Zellen hinzu
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Führen Sie die erste Zelle der ersten Zeile zusammen
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Erstellen Sie eine weitere Zeile in der Tabelle und fügen Sie eine Zelle mit einem Bild hinzu
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Schritt 6: Speichern des PDF-Dokuments

Sobald die Tabelle zum Kopfbereich hinzugefügt wurde, können wir das PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie die PDF-Datei
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Ersetzen Sie unbedingt „VERZEICHNIS IHRER DOKUMENTE“ durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

### Beispielquellcode für den Abschnitt „Tabelle im Kopf- und Fußbereich“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie eine Dokumentinstanz, indem Sie einen leeren Konstruktor aufrufen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im PDF-Dokument
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Erstellen Sie einen Kopfzeilenabschnitt der PDF-Datei
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Legen Sie den ungeraden Header für die PDF-Datei fest
page.Header = header;

//Legen Sie den oberen Rand für den Kopfbereich fest
header.Margin.Top = 20;

// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
header.Paragraphs.Add(tab1);

// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Mit den Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Legen Sie den Zeilenspannenwert für die erste Zeile auf 2 fest
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Legen Sie die Hintergrundfarbe für Zeile2 fest
row2.BackgroundColor = Color.White;

// Fügen Sie die Zelle hinzu, die das Bild enthält
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Stellen Sie die Bildbreite auf 60 ein
img.FixWidth = 60;

// Fügen Sie das Bild zur Tabellenzelle hinzu
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Stellen Sie die vertikale Ausrichtung des Textes auf zentriert ein
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Speichern Sie die PDF-Datei
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET eine Tabelle in den Kopf- oder Fußzeilenbereich eines PDF-Dokuments einfügen. Sie können jetzt Ihre Kopf- und Fußzeilen anpassen, indem Sie Tabellen hinzufügen, um zusätzliche Informationen in Ihren PDF-Dokumenten anzuzeigen.
