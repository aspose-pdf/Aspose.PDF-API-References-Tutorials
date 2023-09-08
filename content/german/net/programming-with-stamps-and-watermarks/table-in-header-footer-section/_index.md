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

 Jetzt erstellen wir eine Tabelle mit`Table` Klasse und fügen Sie sie der Absatzsammlung des Überschriftenabschnitts hinzu. Hier ist wie:

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

//Legen Sie den ungeraden Header für die PDF-Datei fest
page.Header = header;

// Legen Sie den oberen Rand für den Kopfbereich fest
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

### FAQs zur Tabelle im Kopf- und Fußbereich

#### F: Welchen Zweck hat das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments?

A: Durch das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments können Sie strukturierte und organisierte Informationen wie Titel, Untertitel, Logos oder andere Inhalte anzeigen, die konsistent auf jeder Seite des Dokuments angezeigt werden sollen.

#### F: Wie erreicht der bereitgestellte C#-Quellcode das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments?

A: Der Code demonstriert den Prozess des Erstellens eines leeren PDF-Dokuments, des Hinzufügens einer Seite, des Konfigurierens des Kopfbereichs, des Erstellens einer Tabelle mit Zeilen und Zellen und schließlich des Speicherns des PDF-Dokuments. Das Ergebnis ist eine Tabelle, die im Kopfbereich des PDF-Dokuments angezeigt wird.

#### F: Kann ich das Erscheinungsbild der Tabellenzellen anpassen, z. B. Ränder, Hintergrundfarbe und Textstil?

A: Ja, Sie können das Erscheinungsbild der Tabellenzellen anpassen, indem Sie Eigenschaften wie Zellränder, Hintergrundfarbe, Textstil, Schriftart, Schriftgröße und mehr festlegen.

#### F: Wie wird die Tabelle zum Kopfbereich des PDF-Dokuments hinzugefügt?

A: Der Code fügt die Tabelle zur Absatzsammlung des Kopfzeilenabschnitts hinzu, wodurch sichergestellt wird, dass die Tabelle in der Kopfzeile jeder Seite angezeigt wird.

#### F: Kann ich der Tabelle nach Bedarf weitere Zeilen und Zellen hinzufügen?

 A: Auf jeden Fall können Sie der Tabelle weitere Zeilen und Zellen hinzufügen, indem Sie die verwenden`Rows.Add()` Und`Cells.Add()` Methoden. Dadurch können Sie den Tabelleninhalt nach Ihren Wünschen strukturieren.

#### F: Ist es möglich, die Breite der Tabellenspalten anzupassen?
 A: Ja, Sie können die Breite der Tabellenspalten mit anpassen`ColumnWidths` Eigentum. Dadurch können Sie das Layout der Tabelle steuern.

#### F: Wie kann ich Zellen über mehrere Spalten oder Zeilen innerhalb der Tabelle verteilen?
 A: Um Zellen über mehrere Spalten zu verteilen, können Sie die verwenden`ColSpan` Eigenschaft der entsprechenden Zelle. Ebenso können Sie die verwenden`RowSpan` Eigenschaft, um Zellen über mehrere Zeilen zu erstrecken.

#### F: Was passiert, wenn ich sowohl im Kopf- als auch im Fußzeilenbereich des PDF-Dokuments eine Tabelle hinzufügen möchte?

A: Sie können für die Kopf- und Fußzeilen einen ähnlichen Ansatz verfolgen. Erstellen Sie einfach eine`HeaderFooter` Instanz für die Fußzeile, konfigurieren Sie sie und fügen Sie die Tabelle zu ihrer Absatzsammlung hinzu.

#### F: Kann ich Bilder in den Tabellenzellen verwenden und wie wird das erreicht?

 A: Ja, Sie können Bilder in Tabellenzellen hinzufügen. Das Codebeispiel veranschaulicht das Hinzufügen eines Bilds zu einer Zelle durch Erstellen eines`Image` Objekt hinzufügen, seinen Dateipfad und seine Abmessungen festlegen und es dann den Absätzen einer Zelle hinzufügen.

#### F: Wie stelle ich sicher, dass die Tabelle auf allen Seiten des PDF-Dokuments einheitlich angezeigt wird?

 A: Wenn Sie die Tabelle mit dem zum Kopf- oder Fußzeilenabschnitt hinzufügen`HeaderFooter` Aspose.PDF stellt beispielsweise sicher, dass die Tabelle auf jeder Seite konsistent erscheint und ein einheitliches Layout bietet.