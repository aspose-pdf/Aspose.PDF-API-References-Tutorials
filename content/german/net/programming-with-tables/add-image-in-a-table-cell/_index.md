---
title: Bild in eine Tabellenzelle einfügen
linktitle: Bild in eine Tabellenzelle einfügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ein Bild in eine Tabellenzelle ein, eine Schritt-für-Schritt-Anleitung zur präzisen Bearbeitung von Bildern in PDF-Dokumenten.
type: docs
weight: 10
url: /de/net/programming-with-tables/add-image-in-a-table-cell/
---
In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens eines Bilds zu einer Tabellenzelle mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode zeigt, wie diese Funktion erreicht wird. Wenn Sie die unten beschriebenen Schritte befolgen, können Sie Bilder effektiv in Ihre Tabellenzellen einfügen.

Bevor wir uns in den Code vertiefen, stellen Sie sicher, dass Sie die Bibliothek Aspose.PDF für .NET installiert und in Ihrem Projekt referenziert haben.

## Schritt 1: Einrichten des Dokuments

 Zunächst müssen wir eine neue Instanz des`Document` Klasse aus dem Aspose.Pdf-Namespace. Diese Klasse stellt ein PDF-Dokument dar.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren eines Dokumentobjekts
Document pdfDocument = new Document();
```

## Schritt 2: Erstellen einer Seite

Als Nächstes müssen wir dem PDF-Dokument eine Seite hinzufügen. Eine Seite dient als Container für die Tabelle und andere Elemente.

```csharp
// Erstellen Sie eine Seite im PDF-Dokument
Page sec1 = pdfDocument.Pages.Add();
```

## Schritt 3: Hinzufügen einer Tabelle

 In diesem Schritt erstellen wir eine Tabelle durch Instanziierung der`Table` Klasse aus dem Aspose.Pdf-Namespace.

```csharp
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Schritt 4: Standard-Zellenrahmen festlegen

 Um Konsistenz zu gewährleisten, können wir einen Standardzellenrahmen festlegen mit dem`DefaultCellBorder` Eigenschaft der Tabelle`BorderInfo` Objekt.

```csharp
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Schritt 5: Spaltenbreiten festlegen

 Um die Breite jeder Spalte in der Tabelle zu definieren, können wir Folgendes festlegen:`ColumnWidths` Eigenschaft. Geben Sie die Breiten als Zeichenfolge mit durch Leerzeichen getrennten Werten an.

```csharp
// Mit Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "100 100 120";
```

## Schritt 6: Hinzufügen eines Bildes zu einer Tabellenzelle

Jetzt kommt der spannende Teil, das Hinzufügen eines Bildes zu einer Tabellenzelle. Dazu führen wir diese Teilschritte aus:

## Schritt 6.1: Erstellen eines Bildobjekts

 Erstellen Sie eine Instanz des`Image` Klasse aus dem Aspose.Pdf-Namespace. Setzen Sie die`File` -Eigenschaft auf den Pfad der Bilddatei, die Sie hinzufügen möchten.

```csharp
// Erstellen eines Image-Objekts
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Schritt 6.2: Erstellen einer Zeile und von Zellen

Um das Bild zur Tabelle hinzuzufügen, müssen wir zuerst eine Zeile und die erforderlichen Zellen erstellen.

```csharp
// Erstellen Sie eine Zeile in der Tabelle
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Fügen Sie der Zeile eine Textzelle hinzu
row1.Cells.Add("Sample text in cell");

// Fügen Sie die Zelle hinzu, die das Bild enthält
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Schritt 6.3: Hinzufügen des Bildes zur Tabellenzelle

Schließlich können wir das Bild der Tabellenzelle hinzufügen, indem wir es als Absatz innerhalb der Zelle einfügen.

```csharp
//Fügen Sie das Bild zur Tabellenzelle hinzu
cell2.Paragraphs.Add(img);
```

## Schritt 6.4: Zusätzliche Zellen hinzufügen

Nachdem wir die Bildzelle hinzugefügt haben, können wir der Zeile bei Bedarf weitere Zellen hinzufügen.

```csharp
// Der Zeile eine weitere Zelle hinzufügen
row1.Cells.Add("Previous cell with image");

// Passen Sie die vertikale Ausrichtung der dritten Zelle an
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Schritt 7: Speichern des Dokuments

 Schließlich können wir das geänderte Dokument an einem bestimmten Ort speichern, indem wir`Save` Verfahren.

```csharp
//Speichern des Dokuments
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET ein Bild zu einer Tabellenzelle hinzufügen. Erkunden Sie gerne weitere Anpassungsoptionen und integrieren Sie diese Funktionalität in Ihre Projekte.

### Beispielquellcode zum Hinzufügen eines Bildes in eine Tabellenzelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren eines Dokumentobjekts
Document pdfDocument = new Document();
// Erstellen Sie eine Seite im PDF-Dokument
Page sec1 = pdfDocument.Pages.Add();
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in die Absatzsammlung der gewünschten Seite ein
sec1.Paragraphs.Add(tab1);
// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Mit Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
//Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Fügen Sie die Zelle hinzu, die das Bild enthält
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
//Fügen Sie das Bild zur Tabellenzelle hinzu
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
//Speichern des Dokuments
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Abschluss

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET ein Bild zu einer Tabellenzelle hinzufügen. Wir haben damit begonnen, das Dokument einzurichten, eine Seite zu erstellen und eine Tabelle hinzuzufügen. Dann haben wir die Standardzellenränder und Spaltenbreiten festgelegt. Wir haben gezeigt, wie Sie einer Tabellenzelle ein Bild hinzufügen und die vertikale Ausrichtung der Zelle anpassen. Abschließend haben wir das geänderte Dokument gespeichert. Indem Sie diese Schritte befolgen, können Sie Ihre PDF-Dokumente effizient mit Bildern in Tabellenzellen verbessern.

### Häufig gestellte Fragen

#### F: Kann ich mit Aspose.PDF für .NET mehrere Bilder zu verschiedenen Zellen in derselben Tabelle hinzufügen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Bilder zu verschiedenen Zellen in derselben Tabelle hinzufügen. Folgen Sie einfach dem im Tutorial gezeigten Vorgang für jedes Bild, das Sie der Tabelle hinzufügen möchten.

#### F: Kann ich die Bildgröße und -position innerhalb der Tabellenzelle anpassen?

 A: Ja, Sie können die Bildgröße und -position innerhalb der Tabellenzelle anpassen, indem Sie die Eigenschaften des`Image` Objekt. Sie können die Bildbreite und -höhe sowie die Ausrichtung innerhalb der Zelle festlegen.

#### F: Kann ich einer Tabelle mit einer dynamischen Anzahl von Zeilen und Spalten Bilder hinzufügen?

A: Ja, Sie können einer Tabelle mit einer dynamischen Anzahl von Zeilen und Spalten Bilder hinzufügen. Aspose.PDF für .NET bietet Flexibilität beim Erstellen von Tabellen mit unterschiedlichen Abmessungen. Sie können nach Bedarf Zeilen und Zellen hinzufügen und dann entsprechend Bilder zu bestimmten Zellen hinzufügen.

#### F: Welche Bildformate werden von Aspose.PDF für .NET zum Hinzufügen von Bildern zu Tabellenzellen unterstützt?

A: Aspose.PDF für .NET unterstützt eine Vielzahl von Bildformaten, darunter JPEG, PNG, GIF, BMP und TIFF. Sie können Bilder in jedem dieser Formate verwenden, um sie zu Tabellenzellen hinzuzufügen.

#### F: Kann ich in einem vorhandenen PDF-Dokument Bilder zu Tabellen hinzufügen?

A: Ja, Sie können mit Aspose.PDF für .NET Bilder zu Tabellen in einem vorhandenen PDF-Dokument hinzufügen. Laden Sie einfach das vorhandene Dokument und befolgen Sie die gleichen Schritte, um Bilder zur Tabelle hinzuzufügen, wie im Tutorial gezeigt.