---
title: SVG-Objekt zur PDF-Datei hinzufügen
linktitle: SVG-Objekt zur PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach SVG-Objekte in PDF-Dateien ein.
type: docs
weight: 30
url: /de/net/programming-with-tables/add-svg-object/
---
In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET ein SVG-Objekt in eine PDF-Datei einfügen. SVG (Scalable Vector Graphics) ist ein beliebtes Format für Vektorgrafiken, das sich ohne Qualitätsverlust leicht skalieren lässt. Mit Aspose.PDF können Sie Ihren PDF-Dokumenten programmgesteuert SVG-Objekte hinzufügen.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Visual Studio installiert
- Aspose.PDF für .NET-Bibliothek installiert

## Schritt 1: Einrichten der Umgebung

Richten wir zunächst die Umgebung ein, indem wir in Visual Studio ein neues C#-Projekt erstellen. Öffnen Sie Visual Studio und führen Sie diese Schritte aus:

1. Klicken Sie auf „Datei“ > „Neu“ > „Projekt“, um ein neues Projekt zu erstellen.
2. Wählen Sie je nach Setup die Vorlage „Konsolen-App (.NET Framework)“ oder „Konsolen-App (.NET Core)“.
3. Wählen Sie einen geeigneten Namen und Speicherort für Ihr Projekt und klicken Sie dann auf „Erstellen“.

## Schritt 2: Dokument- und Bildobjekte erstellen

In diesem Schritt erstellen wir die erforderlichen Objekte für unser PDF-Dokument und SVG-Bild. Öffnen Sie die C#-Datei Ihres Projekts und fügen Sie den folgenden Code hinzu:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document-Objekt
Document doc = new Document();
// Erstellen einer Imageinstanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Schritt 3: Bildeigenschaften festlegen

Als Nächstes legen wir die Eigenschaften für unser SVG-Bild fest. Wir geben den Dateityp als SVG an, den Pfad zur SVG-Datei und die Abmessungen des Bildes. Fügen Sie nach dem vorherigen Schritt den folgenden Code hinzu:

```csharp
// Bildtyp als SVG festlegen
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pfad zur Quelldatei
img.File = dataDir + "SVGToPDF.svg";
// Breite für Bildinstanz festlegen
img. FixWidth = 50;
// Höhe für Bildinstanz festlegen
img.FixHeight = 50;
```

## Schritt 4: Erstellen und Konfigurieren der Tabelle

Lassen Sie uns nun ein Tabellenobjekt erstellen und die Spaltenbreiten festlegen. Wir erstellen eine Tabelle mit zwei Spalten, jede mit einer Breite von 100 Einheiten. Fügen Sie den folgenden Code hinzu:

```csharp
// Instanztabelle erstellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breite für Tabellenzellen festlegen
table. ColumnWidths = "100 100";
```

## Schritt 5: Zellen zur Tabelle hinzufügen

In diesem Schritt fügen wir der Tabelle eine Zeile und Zellen hinzu. Jede Zeile stellt eine horizontale Zeile in der Tabelle dar, und den Zeilen werden Zellen hinzugefügt. Fügen Sie den folgenden Code hinzu:

```csharp
//Zeilenobjekt erstellen und zur Tabelleninstanz hinzufügen
Aspose.Pdf.Row row = table.Rows.Add();
// Zellenobjekt erstellen und zur Zeileninstanz hinzufügen
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Schritt 6: Text und Bild zu Zellen hinzufügen

Als nächstes fügen wir den Zellen der Tabelle Text und das SVG-Bild hinzu. Wir fügen der ersten Zelle den Text „Erste Zelle“ und der zweiten Zelle das SVG-Bild hinzu. Fügen Sie den folgenden Code hinzu:

```csharp
// Textfragment zur Absatzsammlung des Zellobjekts hinzufügen
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dem Zeilenobjekt eine weitere Zelle hinzufügen
cell = row. Cells. Add();
// SVG-Bild zur Absatzsammlung der kürzlich hinzugefügten Zellinstanz hinzufügen
cell.Paragraphs.Add(img);
```

## Schritt 7: Erstellen und Hinzufügen einer Seite zum Dokument

Lassen Sie uns nun ein Seitenobjekt erstellen und es dem Dokument hinzufügen. Die Tabelle wird der Absatzsammlung der Seite hinzugefügt. Fügen Sie den folgenden Code hinzu:

```csharp
// Seitenobjekt erstellen und zur Seitensammlung der Dokumentinstanz hinzufügen
Page page = doc.Pages.Add();
// Tabelle zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(table);
```

## Schritt 8: Speichern Sie die PDF-Datei

Zum Schluss speichern wir die PDF-Datei am angegebenen Ort. Fügen Sie den folgenden Code hinzu:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Hinzufügen eines SVG-Objekts mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document-Objekt instanziieren
Document doc = new Document();
// Erstellen einer Imageinstanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Bildtyp als SVG festlegen
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pfad zur Quelldatei
img.File = dataDir + "SVGToPDF.svg";
// Breite für Bildinstanz festlegen
img.FixWidth = 50;
// Höhe für Bildinstanz festlegen
img.FixHeight = 50;
// Tabelleninstanz erstellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Breite für Tabellenzellen festlegen
table.ColumnWidths = "100 100";
//Zeilenobjekt erstellen und zur Tabelleninstanz hinzufügen
Aspose.Pdf.Row row = table.Rows.Add();
// Zellenobjekt erstellen und zur Zeileninstanz hinzufügen
Aspose.Pdf.Cell cell = row.Cells.Add();
// Textfragment zur Absatzsammlung des Zellobjekts hinzufügen
cell.Paragraphs.Add(new TextFragment("First cell"));
// Dem Zeilenobjekt eine weitere Zelle hinzufügen
cell = row.Cells.Add();
// SVG-Bild zur Absatzsammlung der kürzlich hinzugefügten Zellinstanz hinzufügen
cell.Paragraphs.Add(img);
// Seitenobjekt erstellen und zur Seitensammlung der Dokumentinstanz hinzufügen
Page page = doc.Pages.Add();
// Tabelle zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.PDF für .NET-Bibliothek ein SVG-Objekt zu einer PDF-Datei hinzufügt. Wir haben den schrittweisen Prozess des Erstellens eines Dokuments, des Einrichtens der Umgebung, des Hinzufügens eines SVG-Bilds zu einer Tabellenzelle und des Speicherns der PDF-Datei behandelt. Jetzt können Sie SVG-Objekte programmgesteuert in Ihre PDF-Dokumente integrieren.

### FAQs zum Hinzufügen von SVG-Objekten zu PDF-Dateien

#### F: Kann ich dem PDF-Dokument mehrere SVG-Objekte hinzufügen?

 A: Ja, Sie können mehrere SVG-Objekte zum PDF-Dokument hinzufügen. Erstellen und konfigurieren Sie einfach zusätzliche`Aspose.Pdf.Image` Instanzen für jedes SVG-Bild, das Sie hinzufügen möchten, und fügen Sie sie dann den gewünschten Tabellenzellen oder Absätzen im PDF-Dokument hinzu.

#### F: Wie kann ich die Größe und Position des SVG-Bildes in der Tabellenzelle anpassen?

 A: Um die Größe und Position des SVG-Bildes in der Tabellenzelle anzupassen, können Sie die`FixWidth` Und`FixHeight` Eigenschaften der`Aspose.Pdf.Image`Instanz. Sie können auch andere Eigenschaften verwenden wie`HorizontalAlignment` Und`VerticalAlignment` der Tabellenzelle, um die Positionierung zu steuern.

#### F: Ist es möglich, neben dem SVG-Bild in derselben Tabellenzelle Text hinzuzufügen?

 A: Ja, es ist möglich, neben dem SVG-Bild in derselben Tabellenzelle Text hinzuzufügen. Sie können den`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` Methode, um der Zelle zusammen mit dem SVG-Bild Text hinzuzufügen.

#### F: Kann ich dem SVG-Bild Hyperlinks hinzufügen?

 A: Ja, Sie können Hyperlinks zum SVG-Bild hinzufügen, indem Sie den`Hyperlink` Eigentum der`Aspose.Pdf.Image` Instanz. Legen Sie die Hyperlink-URL oder Aktion fest, um das Bild anklickbar zu machen.

#### F: Ist Aspose.PDF für .NET mit .NET Core 3.1 oder späteren Versionen kompatibel?

A: Ja, Aspose.PDF für .NET ist mit .NET Core 3.1 und späteren Versionen kompatibel. Sie können es sowohl in .NET Framework- als auch in .NET Core-Anwendungen verwenden.