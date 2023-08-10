---
title: Bild in einer Tabellenzelle hinzufügen
linktitle: Bild in einer Tabellenzelle hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ein Bild in eine Tabellenzelle ein, eine Schritt-für-Schritt-Anleitung für die präzise Bearbeitung von Bildern in PDF-Dokumenten.
type: docs
weight: 10
url: /de/net/programming-with-tables/add-image-in-a-table-cell/
---
In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens eines Bilds zu einer Tabellenzelle mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode zeigt, wie diese Funktionalität erreicht wird. Wenn Sie die unten beschriebenen Schritte befolgen, können Sie Bilder effektiv in Ihre Tabellenzellen integrieren.

Bevor wir uns mit dem Code befassen, stellen Sie sicher, dass die Aspose.PDF für .NET-Bibliothek in Ihrem Projekt installiert und referenziert ist.

## Schritt 1: Einrichten des Dokuments

 Zunächst müssen wir eine neue Instanz von erstellen`Document` Klasse aus dem Aspose.Pdf-Namespace. Diese Klasse repräsentiert ein PDF-Dokument.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie ein Document-Objekt
Document pdfDocument = new Document();
```

## Schritt 2: Erstellen einer Seite

Als nächstes müssen wir dem PDF-Dokument eine Seite hinzufügen. Eine Seite dient als Container für die Tabelle und andere Elemente.

```csharp
//Erstellen Sie eine Seite im PDF-Dokument
Page sec1 = pdfDocument.Pages.Add();
```

## Schritt 3: Hinzufügen einer Tabelle

 In diesem Schritt erstellen wir eine Tabelle, indem wir die instanziieren`Table` Klasse aus dem Aspose.Pdf-Namespace.

```csharp
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Schritt 4: Standardzellenrahmen festlegen

 Um die Konsistenz sicherzustellen, können wir mithilfe von einen Standard-Zellenrand festlegen`DefaultCellBorder`Eigenschaft der Tabelle`BorderInfo` Objekt.

```csharp
// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Schritt 5: Spaltenbreiten festlegen

 Um die Breite jeder Spalte in der Tabelle zu definieren, können wir festlegen`ColumnWidths` Eigentum. Geben Sie die Breiten als Zeichenfolge mit durch Leerzeichen getrennten Werten an.

```csharp
// Mit den Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "100 100 120";
```

## Schritt 6: Hinzufügen eines Bildes zu einer Tabellenzelle

Jetzt kommt der spannende Teil: das Hinzufügen eines Bildes zu einer Tabellenzelle. Dazu folgen wir diesen Unterschritten:

## Schritt 6.1: Erstellen eines Bildobjekts

 Erstellen Sie eine Instanz von`Image` Klasse aus dem Aspose.Pdf-Namespace. Stellen Sie die ein`File` -Eigenschaft auf den Pfad der Bilddatei, die Sie hinzufügen möchten.

```csharp
// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Schritt 6.2: Erstellen einer Zeile und Zellen

Um das Bild zur Tabelle hinzuzufügen, müssen wir zunächst eine Zeile und die erforderlichen Zellen erstellen.

```csharp
// Erstellen Sie eine Zeile in der Tabelle
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Fügen Sie der Zeile eine Textzelle hinzu
row1.Cells.Add("Sample text in cell");

// Fügen Sie die Zelle hinzu, die das Bild enthält
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Schritt 6.3: Hinzufügen des Bildes zur Tabellenzelle

Schließlich können wir das Bild zur Tabellenzelle hinzufügen, indem wir es als Absatz innerhalb der Zelle hinzufügen.

```csharp
// Fügen Sie das Bild zur Tabellenzelle hinzu
cell2.Paragraphs.Add(img);
```

## Schritt 6.4: Zusätzliche Zellen hinzufügen

Nachdem wir die Bildzelle hinzugefügt haben, können wir der Zeile bei Bedarf weitere Zellen hinzufügen.

```csharp
//Fügen Sie der Zeile eine weitere Zelle hinzu
row1.Cells.Add("Previous cell with image");

// Passen Sie die vertikale Ausrichtung der dritten Zelle an
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Schritt 7: Speichern des Dokuments

 Schließlich können wir das geänderte Dokument mithilfe von an einem angegebenen Ort speichern`Save` Methode.

```csharp
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET ein Bild zu einer Tabellenzelle hinzufügen. Entdecken Sie gerne weitere Anpassungsmöglichkeiten und integrieren Sie diese Funktionalität in Ihre Projekte.

### Beispielquellcode zum Hinzufügen eines Bildes in einer Tabellenzelle mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie ein Document-Objekt
Document pdfDocument = new Document();
//Erstellen Sie eine Seite im PDF-Dokument
Page sec1 = pdfDocument.Pages.Add();
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in der Absatzsammlung der gewünschten Seite hinzu
sec1.Paragraphs.Add(tab1);
// Legen Sie den Standardzellenrahmen mithilfe des BorderInfo-Objekts fest
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Mit den Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Fügen Sie die Zelle hinzu, die das Bild enthält
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Fügen Sie das Bild zur Tabellenzelle hinzu
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Speichern Sie das Dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Abschluss

In diesem Tutorial haben wir eine Schritt-für-Schritt-Anleitung zum Hinzufügen eines Bilds zu einer Tabellenzelle mit Aspose.PDF für .NET behandelt. Wir begannen damit, das Dokument einzurichten, eine Seite zu erstellen und eine Tabelle hinzuzufügen. Anschließend legen wir den Standard-Zellenrahmen und die Spaltenbreite fest. Wir haben gezeigt, wie man einer Tabellenzelle ein Bild hinzufügt und die vertikale Ausrichtung der Zelle anpasst. Schließlich haben wir das geänderte Dokument gespeichert. Wenn Sie diese Schritte befolgen, können Sie Ihre PDF-Dokumente effizient mit Bildern in Tabellenzellen erweitern.

### FAQs

#### F: Kann ich mit Aspose.PDF für .NET mehrere Bilder zu verschiedenen Zellen innerhalb derselben Tabelle hinzufügen?

A: Ja, Sie können mit Aspose.PDF für .NET mehrere Bilder zu verschiedenen Zellen innerhalb derselben Tabelle hinzufügen. Befolgen Sie einfach für jedes Bild, das Sie der Tabelle hinzufügen möchten, den gleichen Vorgang, der im Tutorial gezeigt wird.

#### F: Kann ich die Bildgröße und Position innerhalb der Tabellenzelle anpassen?

 A: Ja, Sie können die Bildgröße und -position innerhalb der Tabellenzelle anpassen, indem Sie die Eigenschaften anpassen`Image`Objekt. Sie können die Bildbreite und -höhe sowie die Ausrichtung innerhalb der Zelle festlegen.

#### F: Kann ich Bilder zu einer Tabelle mit einer dynamischen Anzahl von Zeilen und Spalten hinzufügen?

A: Ja, Sie können Bilder zu einer Tabelle mit einer dynamischen Anzahl von Zeilen und Spalten hinzufügen. Aspose.PDF für .NET bietet Flexibilität beim Erstellen von Tabellen mit unterschiedlichen Abmessungen. Sie können nach Bedarf Zeilen und Zellen hinzufügen und dann entsprechend Bilder zu bestimmten Zellen hinzufügen.

#### F: Welche Bildformate werden von Aspose.PDF für .NET zum Hinzufügen von Bildern zu Tabellenzellen unterstützt?

A: Aspose.PDF für .NET unterstützt eine Vielzahl von Bildformaten, darunter JPEG, PNG, GIF, BMP und TIFF. Sie können Bilder in jedem dieser Formate verwenden, um sie zu Tabellenzellen hinzuzufügen.

#### F: Kann ich Bilder zu Tabellen in einem vorhandenen PDF-Dokument hinzufügen?

A: Ja, Sie können mit Aspose.PDF für .NET Bilder zu Tabellen in einem vorhandenen PDF-Dokument hinzufügen. Laden Sie einfach das vorhandene Dokument und befolgen Sie die gleichen Schritte, um der Tabelle Bilder hinzuzufügen, wie im Tutorial gezeigt.