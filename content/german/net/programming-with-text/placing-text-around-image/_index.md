---
title: Platzieren von Text um das Bild in einer PDF-Datei
linktitle: Platzieren von Text um das Bild in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text um ein Bild in einer PDF-Datei platzieren.
type: docs
weight: 260
url: /de/net/programming-with-text/placing-text-around-image/
---
In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einer PDF-Datei platzieren. Wir werden Schritt für Schritt den Prozess der Erstellung einer Tabelle, des Hinzufügens eines Bilds und der Positionierung von Text um das Bild herum mithilfe des bereitgestellten C#-Quellcodes durchgehen.

## Anforderungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zunächst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem Sie die generierte PDF-Datei speichern möchten. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir`Variable mit dem Pfad zu Ihrem gewünschten Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und eine Seite

 Als nächstes erstellen wir eine`Document` Objekt und fügen Sie ihm mithilfe von eine Seite hinzu`Pages.Add()` Methode.

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

## Schritt 4: Legen Sie die Spaltenbreiten und -ränder der Tabelle fest

 Wir legen die Spaltenbreiten der Tabelle fest und erstellen eine`MarginInfo` Objekt zum Festlegen der Ränder.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Schritt 5: Fügen Sie der Tabelle ein Bild hinzu

 Wir erstellen eine`Image` Objekt, geben Sie den Bilddateipfad an und legen Sie die feste Höhe und Breite des Bildes fest. Anschließend fügen wir das Bild zur Absatzsammlung der Tabellenzelle hinzu.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Schritt 6: Fügen Sie Text um das Bild herum hinzu

 Wir erstellen String-Variablen mit HTML-formatiertem Text und erstellen eine`HtmlFragment`Objekt. Anschließend fügen wir den HTML-Text zur Tabellenzelle hinzu, die das Bild enthält.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Schritt 7: Zusätzlichen Text hinzufügen

 Wir erschaffen ein anderes`HtmlFragment` Objekt, das zusätzlichen HTML-formatierten Text enthält, und fügen Sie ihn einer separaten Tabellenzelle hinzu.

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

### Beispielquellcode zum Platzieren von Text um ein Bild mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Erstellen Sie eine Seite im PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Instanziieren Sie ein Tabellenobjekt
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Fügen Sie die Tabelle in der Absatzsammlung des gewünschten Abschnitts hinzu
page.Paragraphs.Add(table1);
// Mit den Spaltenbreiten der Tabelle festlegen
table1.ColumnWidths = "120 270";
// Erstellen Sie ein MarginInfo-Objekt und legen Sie dessen linken, unteren, rechten und oberen Rand fest
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Legen Sie den Standard-Zellenabstand für das MarginInfo-Objekt fest
table1.DefaultCellPadding = margin;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Erstellen Sie ein Bildobjekt
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Geben Sie den Pfad der Bilddatei an
logo.File = dataDir + "aspose-logo.jpg";
// Geben Sie die feste Bildhöhe an
logo.FixHeight = 120;
// Geben Sie die feste Bildbreite an
logo.FixWidth = 110;
row1.Cells.Add();
// Fügen Sie das Bild zur Absatzsammlung der Tabellenzelle hinzu
row1.Cells[0].Paragraphs.Add(logo);
// Erstellen Sie String-Variablen mit Text, der HTML-Tags enthält
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Erstellen Sie ein Textobjekt, das rechts vom Bild hinzugefügt werden soll
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Fügen Sie die Textabsätze mit HTML-Text zur Tabellenzelle hinzu
row1.Cells[1].Paragraphs.Add(TitleText);
// Legen Sie die vertikale Ausrichtung des Zeileninhalts auf „Oben“ fest
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Erstellen Sie Zeilen in der Tabelle und dann Zellen in den Zeilen
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Legen Sie den Zeilenspannenwert für die zweite Zeile auf 2 fest
SecondRow.Cells[0].ColSpan = 2;
// Legen Sie die vertikale Ausrichtung der zweiten Reihe auf „Oben“ fest
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Fügen Sie die Textabsätze mit HTML-Text zur Tabellenzelle hinzu
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Speichern Sie die PDF-Datei
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einem PDF-Dokument platzieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie eine Tabelle erstellen, ein Bild hinzufügen und Text um das Bild herum in einem PDF-Dokument positionieren.

### FAQs

#### F: Was ist der Zweck des Tutorials „Platzieren von Text um ein Bild in einer PDF-Datei“?

A: Das Tutorial „Platzieren von Text um ein Bild in einer PDF-Datei“ zeigt, wie Sie mit der Aspose.PDF-Bibliothek für .NET Text um ein Bild in einem PDF-Dokument platzieren. Das Tutorial bietet eine Schritt-für-Schritt-Anleitung und C#-Quellcode, die Ihnen beim Erstellen einer Tabelle, dem Hinzufügen eines Bilds und der Positionierung von Text um das Bild herum helfen.

#### F: Warum sollte ich in einem PDF-Dokument Text um ein Bild herum platzieren?

A: Das Platzieren von Text um ein Bild verbessert die visuelle Darstellung Ihrer PDF-Dokumente und macht sie ansprechender und informativer. Diese Technik wird häufig in Dokumenten, Broschüren, Berichten und anderen Materialien verwendet, bei denen Sie Bilder und Text auf ästhetisch ansprechende Weise kombinieren möchten.

#### F: Wie richte ich das Dokumentenverzeichnis ein?

A: So richten Sie das Dokumentenverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu dem Verzeichnis, in dem Sie die generierte PDF-Datei speichern möchten.

#### F: Wie erstelle ich eine Tabelle und füge ihr ein Bild hinzu?

 A: Das Tutorial führt Sie durch den Prozess der Erstellung einer Tabelle mit`Table` Klasse und Hinzufügen eines Bildes zur Tabelle mithilfe von`Image` Klasse. Sie geben den Pfad, die Höhe und die Breite der Bilddatei an, bevor Sie sie einer Tabellenzelle hinzufügen.

#### F: Wie positioniere ich Text um das Bild herum?

 A: Um Text um das Bild herum zu positionieren, erstellen Sie mithilfe von HTML-formatierten Text`HtmlFragment` Klasse. Dieser Text enthält sowohl einen Titel als auch einen Textkörper. Anschließend fügen Sie diesen HTML-Text in eine Tabellenzelle ein, die an die Bildzelle angrenzt.

#### F: Kann ich das Erscheinungsbild von Text und Bild anpassen?

A: Ja, Sie können das Erscheinungsbild von Text und Bild mithilfe von HTML-Tags und -Eigenschaften anpassen. Sie können beispielsweise Schriftgrößen, Farben, Stile und Ausrichtung für den Text festlegen. Darüber hinaus können Sie die Größe und Abmessungen des Bildes anpassen.

#### F: Wie speichere ich das PDF-Dokument?

 A: Nachdem Sie das Bild und den Text zur Tabelle hinzugefügt haben, können Sie das PDF-Dokument mit speichern`Save` Methode der`Document` Klasse. Geben Sie den gewünschten Ausgabedateipfad als Argument für an`Save` Methode.

#### F: Was ist das erwartete Ergebnis dieses Tutorials?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, generieren Sie ein PDF-Dokument, das zeigt, wie man Text um ein Bild herum platziert. Das Ausgabedokument enthält eine Tabelle mit einem Bild und Text darum herum.

#### F: Kann ich andere Bildformate als JPG verwenden?

 A: Ja, Sie können verschiedene Bildformate verwenden, die von der Aspose.PDF-Bibliothek unterstützt werden, z. B. PNG, BMP, GIF und mehr. Beim Erstellen der`Image` Geben Sie als Objekt den Dateipfad des gewünschten Bildformats an.

#### F: Ist für dieses Tutorial eine gültige Aspose-Lizenz erforderlich?

A: Ja, eine gültige Aspose-Lizenz ist erforderlich, damit dieses Tutorial ordnungsgemäß funktioniert. Sie können eine Volllizenz erwerben oder eine 30-tägige temporäre Lizenz auf der Aspose-Website erwerben.