---
title: Tabelle im Kopf-/Fußzeilenbereich
linktitle: Tabelle im Kopf-/Fußzeilenbereich
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Tabelle in den Kopf-/Fußzeilenbereich eines PDF-Dokuments einfügen.
type: docs
weight: 170
url: /de/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET eine Tabelle in den Kopf- oder Fußzeilenbereich eines PDF-Dokuments einfügen. Der bereitgestellte C#-Quellcode zeigt Ihnen, wie Sie ein leeres PDF-Dokument erstellen, eine Seite hinzufügen, den Kopfzeilenbereich konfigurieren, eine Tabelle erstellen, der Tabelle Zeilen und Zellen hinzufügen und schließlich das PDF-Dokument speichern.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Erstellen des PDF-Dokuments und der Seite

 Der erste Schritt besteht in der Erstellung einer Instanz des`Document` Klasse und fügen Sie dem Dokument eine Seite hinzu. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanziieren eines Dokumentobjekts
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Erstellen einer Seite im PDF-Dokument
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

## Schritt 3: Konfigurieren des Header-Abschnitts

 Nun konfigurieren wir den Header-Abschnitt des PDF-Dokuments, indem wir eine Instanz des`HeaderFooter` Klasse. So geht's:

```csharp
// Erstellen Sie einen Kopfzeilenabschnitt für die PDF-Datei
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definieren Sie den Kopfbereich für die Seite
page. Header = header;

// Oberen Rand des Header-Abschnitts festlegen
header. Margin. Top = 20;
```

## Schritt 4: Erstellen der Tabelle

 Nun erstellen wir eine Tabelle mit dem`Table` Klasse und fügen Sie sie der Absatzsammlung des Überschriftenabschnitts hinzu. So geht's:

```csharp
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie die Tabelle zur Absatzsammlung des Kopfbereichs hinzu
header.Paragraphs.Add(tab1);

// Definieren Sie die Breite der Spalten der Tabelle
tab1.ColumnWidths = "60,300";
```

Der obige Code erstellt eine Tabelle mit zwei Spalten der angegebenen Breite.

## Schritt 5: Zeilen und Zellen zur Tabelle hinzufügen

 Nun fügen wir der Tabelle Zeilen und Zellen hinzu, indem wir`Row` Klasse und die`Cell` Klasse. So geht's:

```csharp
// Erstellen Sie eine Zeile in der Tabelle und fügen Sie Zellen hinzu
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Die erste Zelle der ersten Zeile zusammenführen
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

Nachdem die Tabelle zum Kopfbereich hinzugefügt wurde, können wir das PDF-Dokument speichern. So geht's:

```csharp
// Speichern Sie die PDF-Datei
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das PDF-Dokument speichern möchten.

### Beispielquellcode für eine Tabelle im Kopf-/Fußzeilenbereich mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanziieren Sie die Document-Instanz, indem Sie einen leeren Konstruktor aufrufen
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Erstellen Sie eine Seite im PDF-Dokument
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Erstellen Sie einen Kopfbereich der PDF-Datei
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Legen Sie den Odd Header für die PDF-Datei fest
page.Header = header;

// Oberen Rand für den Kopfbereich festlegen
header.Margin.Top = 20;

// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
header.Paragraphs.Add(tab1);

// Festlegen des Standardzellenrahmens mithilfe des BorderInfo-Objekts
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Mit Spaltenbreiten der Tabelle festlegen
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Setzen Sie den Zeilenspannwert für die erste Zeile auf 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Legen Sie die Hintergrundfarbe für Zeile 2 fest.
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

### FAQs zur Tabelle im Kopf-/Fußzeilenbereich

#### F: Welchen Zweck hat das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments?

A: Durch das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments können Sie strukturierte und organisierte Informationen wie Titel, Untertitel, Logos oder andere Inhalte anzeigen, die auf jeder Seite des Dokuments einheitlich erscheinen sollen.

#### F: Wie ermöglicht der bereitgestellte C#-Quellcode das Hinzufügen einer Tabelle im Kopf- oder Fußzeilenbereich eines PDF-Dokuments?

A: Der Code demonstriert den Vorgang des Erstellens eines leeren PDF-Dokuments, des Hinzufügens einer Seite, des Konfigurierens des Kopfbereichs, des Erstellens einer Tabelle mit Zeilen und Zellen und des abschließenden Speicherns des PDF-Dokuments. Das Ergebnis ist eine Tabelle, die im Kopfbereich des PDF-Dokuments angezeigt wird.

#### F: Kann ich das Erscheinungsbild der Tabellenzellen, beispielsweise Ränder, Hintergrundfarbe und Textstil, anpassen?

A: Ja, Sie können das Erscheinungsbild der Tabellenzellen anpassen, indem Sie Eigenschaften wie Zellenränder, Hintergrundfarbe, Textstil, Schriftart, Schriftgröße und mehr festlegen.

#### F: Wie wird die Tabelle zum Kopfbereich des PDF-Dokuments hinzugefügt?

A: Der Code fügt die Tabelle der Absatzsammlung des Kopfbereichs hinzu, wodurch sichergestellt wird, dass die Tabelle im Kopf jeder Seite angezeigt wird.

#### F: Kann ich der Tabelle nach Bedarf weitere Zeilen und Zellen hinzufügen?

 A: Natürlich. Sie können der Tabelle weitere Zeilen und Zellen hinzufügen, indem Sie die`Rows.Add()` Und`Cells.Add()` Methoden. Damit können Sie den Tabelleninhalt beliebig strukturieren.

#### F: Ist es möglich, die Breite der Tabellenspalten anzupassen?
 A: Ja, Sie können die Breite der Tabellenspalten anpassen mit dem`ColumnWidths` -Eigenschaft. Dadurch können Sie das Layout der Tabelle steuern.

#### F: Wie kann ich Zellen über mehrere Spalten oder Zeilen innerhalb der Tabelle verteilen?
 A: Um Zellen über mehrere Spalten zu verteilen, können Sie die`ColSpan`Eigenschaft der entsprechenden Zelle. Ebenso können Sie die`RowSpan` -Eigenschaft, um Zellen über mehrere Zeilen zu verteilen.

#### F: Was passiert, wenn ich sowohl zum Kopf- als auch zum Fußzeilenabschnitt des PDF-Dokuments eine Tabelle hinzufügen möchte?

 A: Sie können für Kopf- und Fußzeilenabschnitte einen ähnlichen Ansatz verfolgen. Erstellen Sie einfach eine`HeaderFooter` Instanz für die Fußzeile, konfigurieren Sie sie und fügen Sie die Tabelle ihrer Absatzsammlung hinzu.

#### F: Kann ich Bilder in den Tabellenzellen verwenden und wie wird das erreicht?

 A: Ja, Sie können Bilder in Tabellenzellen einfügen. Das Codebeispiel zeigt das Hinzufügen eines Bilds zu einer Zelle durch Erstellen eines`Image` Objekt, legen Sie seinen Dateipfad und seine Abmessungen fest und fügen Sie es dann den Absätzen einer Zelle hinzu.

#### F: Wie stelle ich sicher, dass die Tabelle auf allen Seiten des PDF-Dokuments einheitlich angezeigt wird?

 A: Wenn Sie die Tabelle mit dem Symbol`HeaderFooter` Beispielsweise sorgt Aspose.PDF dafür, dass die Tabelle auf jeder Seite einheitlich angezeigt wird und sorgt so für ein einheitliches Layout.