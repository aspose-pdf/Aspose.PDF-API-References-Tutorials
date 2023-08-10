---
title: SVG-Objekt in PDF-Datei hinzufügen
linktitle: SVG-Objekt in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Fügen Sie mit Aspose.PDF für .NET ganz einfach SVG-Objekte in eine PDF-Datei ein.
type: docs
weight: 30
url: /de/net/programming-with-tables/add-svg-object/
---
In diesem Tutorial erfahren Sie, wie Sie mit der Bibliothek Aspose.PDF für .NET ein SVG-Objekt in eine PDF-Datei hinzufügen. SVG (Scalable Vector Graphics) ist ein beliebtes Format für Vektorgrafiken, das ohne Qualitätsverlust einfach skaliert werden kann. Mit Aspose.PDF können Sie SVG-Objekte programmgesteuert zu Ihren PDF-Dokumenten hinzufügen.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio installiert
- Aspose.PDF für .NET-Bibliothek installiert

## Schritt 1: Richten Sie die Umgebung ein

Zunächst richten wir die Umgebung ein, indem wir in Visual Studio ein neues C#-Projekt erstellen. Öffnen Sie Visual Studio und führen Sie die folgenden Schritte aus:

1. Klicken Sie auf „Datei“ > „Neu“ > „Projekt“, um ein neues Projekt zu erstellen.
2. Wählen Sie je nach Einrichtung die Vorlage „Konsolen-App (.NET Framework)“ oder „Konsolen-App (.NET Core)“ aus.
3. Wählen Sie einen passenden Namen und Speicherort für Ihr Projekt und klicken Sie dann auf „Erstellen“.

## Schritt 2: Dokument- und Bildobjekte erstellen

In diesem Schritt erstellen wir die notwendigen Objekte für unser PDF-Dokument und SVG-Bild. Öffnen Sie die C#-Datei Ihres Projekts und fügen Sie den folgenden Code hinzu:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instant Document-Objekt
Document doc = new Document();
// Erstellen Sie eine Image-Instanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Schritt 3: Bildeigenschaften festlegen

Als nächstes legen wir die Eigenschaften für unser SVG-Bild fest. Wir geben den Dateityp als SVG, den Pfad zur SVG-Datei und die Abmessungen des Bildes an. Fügen Sie nach dem vorherigen Schritt den folgenden Code hinzu:

```csharp
// Stellen Sie den Bildtyp auf SVG ein
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pfad für die Quelldatei
img.File = dataDir + "SVGToPDF.svg";
// Legen Sie die Breite für die Bildinstanz fest
img. FixWidth = 50;
// Legen Sie die Höhe für die Bildinstanz fest
img.FixHeight = 50;
```

## Schritt 4: Erstellen und konfigurieren Sie die Tabelle

Jetzt erstellen wir ein Tabellenobjekt und legen die Spaltenbreiten fest. Wir erstellen eine Tabelle mit zwei Spalten mit einer Breite von jeweils 100 Einheiten. Fügen Sie den folgenden Code hinzu:

```csharp
// Instanztabelle erstellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Legen Sie die Breite für Tabellenzellen fest
table. ColumnWidths = "100 100";
```

## Schritt 5: Zellen zur Tabelle hinzufügen

In diesem Schritt fügen wir der Tabelle eine Zeile und Zellen hinzu. Jede Zeile stellt eine horizontale Zeile in der Tabelle dar, und den Zeilen werden Zellen hinzugefügt. Fügen Sie den folgenden Code hinzu:

```csharp
//Erstellen Sie ein Zeilenobjekt und fügen Sie es der Tabelleninstanz hinzu
Aspose.Pdf.Row row = table.Rows.Add();
// Erstellen Sie ein Zellobjekt und fügen Sie es der Zeileninstanz hinzu
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Schritt 6: Text und Bild zu Zellen hinzufügen

Als nächstes fügen wir Text und das SVG-Bild zu den Zellen der Tabelle hinzu. Wir werden den Text „Erste Zelle“ zur ersten Zelle und das SVG-Bild zur zweiten Zelle hinzufügen. Fügen Sie den folgenden Code hinzu:

```csharp
// Textfragment zur Absatzsammlung des Zellobjekts hinzufügen
cell.Paragraphs.Add(new TextFragment("First cell"));
// Fügen Sie dem Zeilenobjekt eine weitere Zelle hinzu
cell = row. Cells. Add();
// SVG-Bild zur Absatzsammlung der kürzlich hinzugefügten Zellinstanz hinzufügen
cell.Paragraphs.Add(img);
```

## Schritt 7: Erstellen Sie eine Seite und fügen Sie sie zum Dokument hinzu

Jetzt erstellen wir ein Seitenobjekt und fügen es dem Dokument hinzu. Die Tabelle wird zur Absatzsammlung der Seite hinzugefügt. Fügen Sie den folgenden Code hinzu:

```csharp
// Erstellen Sie ein Seitenobjekt und fügen Sie es der Seitensammlung der Dokumentinstanz hinzu
Page page = doc.Pages.Add();
// Fügen Sie der Absatzsammlung des Seitenobjekts eine Tabelle hinzu
page.Paragraphs.Add(table);
```

## Schritt 8: Speichern Sie die PDF-Datei

Abschließend speichern wir die PDF-Datei am angegebenen Speicherort. Fügen Sie den folgenden Code hinzu:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Hinzufügen eines SVG-Objekts mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentobjekt instanziieren
Document doc = new Document();
// Erstellen Sie eine Image-Instanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Stellen Sie den Bildtyp auf SVG ein
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Pfad für die Quelldatei
img.File = dataDir + "SVGToPDF.svg";
// Legen Sie die Breite für die Bildinstanz fest
img.FixWidth = 50;
// Legen Sie die Höhe für die Bildinstanz fest
img.FixHeight = 50;
// Tabelleninstanz erstellen
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Legen Sie die Breite für Tabellenzellen fest
table.ColumnWidths = "100 100";
//Erstellen Sie ein Zeilenobjekt und fügen Sie es der Tabelleninstanz hinzu
Aspose.Pdf.Row row = table.Rows.Add();
// Erstellen Sie ein Zellobjekt und fügen Sie es der Zeileninstanz hinzu
Aspose.Pdf.Cell cell = row.Cells.Add();
// Textfragment zur Absatzsammlung des Zellobjekts hinzufügen
cell.Paragraphs.Add(new TextFragment("First cell"));
// Fügen Sie dem Zeilenobjekt eine weitere Zelle hinzu
cell = row.Cells.Add();
// SVG-Bild zur Absatzsammlung der kürzlich hinzugefügten Zellinstanz hinzufügen
cell.Paragraphs.Add(img);
// Erstellen Sie ein Seitenobjekt und fügen Sie es der Seitensammlung der Dokumentinstanz hinzu
Page page = doc.Pages.Add();
// Fügen Sie der Absatzsammlung des Seitenobjekts eine Tabelle hinzu
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Bibliothek Aspose.PDF für .NET ein SVG-Objekt zu einer PDF-Datei hinzufügt. Wir haben den Schritt-für-Schritt-Prozess zum Erstellen eines Dokuments, zum Einrichten der Umgebung, zum Hinzufügen eines SVG-Bilds zu einer Tabellenzelle und zum Speichern der PDF-Datei behandelt. Jetzt können Sie SVG-Objekte programmgesteuert in Ihre PDF-Dokumente integrieren.

### FAQs zum Hinzufügen eines SVG-Objekts in einer PDF-Datei

#### F: Kann ich dem PDF-Dokument mehrere SVG-Objekte hinzufügen?

 A: Ja, Sie können dem PDF-Dokument mehrere SVG-Objekte hinzufügen. Einfach weitere erstellen und konfigurieren`Aspose.Pdf.Image` Instanzen für jedes SVG-Bild, das Sie hinzufügen möchten, und fügen Sie sie dann den gewünschten Tabellenzellen oder Absätzen im PDF-Dokument hinzu.

#### F: Wie kann ich die Größe und Position des SVG-Bildes in der Tabellenzelle anpassen?

 A: Um die Größe und Position des SVG-Bildes in der Tabellenzelle anzupassen, können Sie das ändern`FixWidth` Und`FixHeight` Eigenschaften der`Aspose.Pdf.Image`Beispiel. Sie können auch andere Eigenschaften verwenden, z`HorizontalAlignment` Und`VerticalAlignment` der Tabellenzelle, um die Positionierung zu steuern.

#### F: Ist es möglich, Text neben dem SVG-Bild in derselben Tabellenzelle hinzuzufügen?

 A: Ja, es ist möglich, Text neben dem SVG-Bild in derselben Tabellenzelle hinzuzufügen. Du kannst den ... benutzen`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` Methode zum Hinzufügen von Text zur Zelle zusammen mit dem SVG-Bild.

#### F: Kann ich dem SVG-Bild Hyperlinks hinzufügen?

 A: Ja, Sie können Hyperlinks zum SVG-Bild hinzufügen, indem Sie die verwenden`Hyperlink` Eigentum der`Aspose.Pdf.Image` Beispiel. Legen Sie die Hyperlink-URL oder Aktion fest, um das Bild anklickbar zu machen.

#### F: Ist Aspose.PDF für .NET mit .NET Core 3.1 oder späteren Versionen kompatibel?

A: Ja, Aspose.PDF für .NET ist mit .NET Core 3.1 und späteren Versionen kompatibel. Sie können es sowohl in .NET Framework- als auch in .NET Core-Anwendungen verwenden.