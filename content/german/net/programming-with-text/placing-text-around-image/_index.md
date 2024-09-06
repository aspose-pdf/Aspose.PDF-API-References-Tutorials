---
title: Platzieren von Text um das Bild in einer PDF-Datei
linktitle: Platzieren von Text um das Bild in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text um ein Bild in einer PDF-Datei platzieren.
type: docs
weight: 260
url: /de/net/programming-with-text/placing-text-around-image/
---
In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einer PDF-Datei platzieren. Wir gehen Schritt für Schritt durch den Prozess der Erstellung einer Tabelle, des Hinzufügens eines Bilds und der Positionierung von Text um das Bild mithilfe des bereitgestellten C#-Quellcodes.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF-Bibliothek für .NET ist installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Zunächst müssen Sie den Pfad zum Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable durch den Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und eine Seite

 Als nächstes erstellen wir eine`Document` Objekt und fügen Sie ihm eine Seite hinzu, indem Sie das`Pages.Add()` Verfahren.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen Sie eine Tabelle

 Wir erstellen eine Tabelle mit dem`Table` Klasse und fügen Sie sie der Absatzsammlung der Seite hinzu.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Schritt 4: Spaltenbreiten und Ränder der Tabelle festlegen

 Wir legen die Spaltenbreiten der Tabelle fest und erstellen eine`MarginInfo` Objekt, um die Ränder festzulegen.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Schritt 5: Ein Bild zur Tabelle hinzufügen

 Wir schaffen eine`Image` Objekt, geben Sie den Bilddateipfad an und legen Sie die feste Höhe und Breite des Bildes fest. Anschließend fügen wir das Bild zur Absatzsammlung der Tabellenzelle hinzu.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Schritt 6: Fügen Sie Text rund um das Bild hinzu

 Wir erstellen String-Variablen mit HTML-formatiertem Text und erstellen eine`HtmlFragment`Objekt. Anschließend fügen wir den HTML-Text der Tabellenzelle hinzu, die das Bild enthält.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Schritt 7: Zusätzlichen Text hinzufügen

 Wir schaffen ein weiteres`HtmlFragment` Objekt mit zusätzlichem HTML-formatiertem Text und fügen Sie es einer separaten Tabellenzelle hinzu.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Schritt 8: Speichern Sie das PDF-Dokument

Abschließend speichern wir das PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Beispiel-Quellcode zum Platzieren von Text um ein Bild mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Erstellen Sie eine Seite im PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Instanziieren eines Tabellenobjekts
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in die Absatzsammlung des gewünschten Abschnitts ein
page.Paragraphs.Add(table1);
// Mit Spaltenbreiten der Tabelle festlegen
table1.ColumnWidths = "120 270";
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Festlegen der Standardzellenpolsterung auf das MarginInfo-Objekt
table1.DefaultCellPadding = margin;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Erstellen eines Bildobjekts
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Geben Sie den Bilddateipfad an
logo.File = dataDir + "aspose-logo.jpg";
// Geben Sie die feste Höhe des Bildes an
logo.FixHeight = 120;
// Geben Sie die feste Breite des Bilds an
logo.FixWidth = 110;
row1.Cells.Add();
// Fügen Sie das Bild zur Absatzsammlung der Tabellenzelle hinzu
row1.Cells[0].Paragraphs.Add(logo);
// Erstellen Sie Zeichenfolgenvariablen mit Text, der HTML-Tags enthält
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Erstellen Sie ein Textobjekt, das rechts neben dem Bild hinzugefügt werden soll
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Fügen Sie der Tabellenzelle die Textabsätze mit HTML-Text hinzu
row1.Cells[1].Paragraphs.Add(TitleText);
// Stellen Sie die vertikale Ausrichtung des Zeileninhalts auf Oben ein.
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Legen Sie den Zeilenspannwert für die zweite Zeile auf 2 fest.
SecondRow.Cells[0].ColSpan = 2;
// Stellen Sie die vertikale Ausrichtung der zweiten Zeile auf Oben ein.
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Fügen Sie der Tabellenzelle die Textabsätze mit HTML-Text hinzu
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Speichern Sie die PDF-Datei
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einem PDF-Dokument platzieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine Tabelle erstellen, ein Bild hinzufügen und Text um das Bild in einem PDF-Dokument platzieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text um Bilder in PDF-Dateien platzieren“?

A: Das Tutorial „Text um ein Bild in einer PDF-Datei platzieren“ zeigt, wie Sie mit der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einem PDF-Dokument platzieren. Das Tutorial enthält eine Schritt-für-Schritt-Anleitung und C#-Quellcode, mit denen Sie eine Tabelle erstellen, ein Bild hinzufügen und Text um das Bild platzieren können.

#### F: Warum sollte ich in einem PDF-Dokument Text um ein Bild herum platzieren?

A: Wenn Sie Text um ein Bild herum platzieren, wird die visuelle Darstellung Ihrer PDF-Dokumente verbessert, sodass sie ansprechender und informativer werden. Diese Technik wird häufig in Dokumenten, Broschüren, Berichten und anderen Materialien verwendet, in denen Sie Bilder und Text auf ästhetisch ansprechende Weise kombinieren möchten.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem Sie die generierte PDF-Datei speichern möchten.

#### F: Wie erstelle ich eine Tabelle und füge ihr ein Bild hinzu?

 A: Das Tutorial führt Sie durch den Prozess der Erstellung einer Tabelle mit dem`Table` Klasse und Hinzufügen eines Bildes zur Tabelle mithilfe der`Image` Klasse. Sie geben den Bilddateipfad, die Höhe und die Breite an, bevor Sie es einer Tabellenzelle hinzufügen.

#### F: Wie positioniere ich Text um das Bild herum?

 A: Um Text um das Bild herum zu platzieren, erstellen Sie HTML-formatierten Text mit dem`HtmlFragment` Klasse. Dieser Text enthält sowohl einen Titel als auch einen Fließtext. Anschließend fügen Sie diesen HTML-Text einer Tabellenzelle hinzu, die neben der Bildzelle liegt.

#### F: Kann ich das Erscheinungsbild von Text und Bild anpassen?

A: Ja, Sie können das Erscheinungsbild von Text und Bild mithilfe von HTML-Tags und -Eigenschaften anpassen. Sie können beispielsweise Schriftgröße, Farben, Stile und Ausrichtung für den Text festlegen. Darüber hinaus können Sie die Größe und Abmessungen des Bildes anpassen.

#### F: Wie speichere ich das PDF-Dokument?

 A: Nachdem Sie das Bild und den Text zur Tabelle hinzugefügt haben, können Sie das PDF-Dokument mit dem`Save` Methode der`Document` Klasse. Geben Sie den gewünschten Ausgabedateipfad als Argument an die`Save` Verfahren.

#### F: Was ist das erwartete Ergebnis dieses Tutorials?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, generieren Sie ein PDF-Dokument, das zeigt, wie Sie Text um ein Bild herum platzieren. Das Ausgabedokument enthält eine Tabelle mit einem Bild und darum herum positioniertem Text.

#### F: Kann ich andere Bildformate als JPG verwenden?

 A: Ja, Sie können verschiedene Bildformate verwenden, die von der Aspose.PDF-Bibliothek unterstützt werden, wie PNG, BMP, GIF und mehr. Beim Erstellen der`Image` Objekt, geben Sie den Dateipfad des gewünschten Bildformats an.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, damit dieses Tutorial richtig funktioniert, ist eine gültige Aspose-Lizenz erforderlich. Sie können eine Volllizenz oder eine 30-tägige temporäre Lizenz von der Aspose-Website erwerben.