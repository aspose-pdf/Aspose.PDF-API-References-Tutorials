---
title: Erstellen Sie ein mehrspaltiges PDF
linktitle: Erstellen Sie ein mehrspaltiges PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein mehrspaltiges PDF erstellen.
type: docs
weight: 110
url: /de/net/programming-with-text/create-multi-column-pdf/
---
Dieses Tutorial führt Sie durch den Prozess der Erstellung einer mehrspaltigen PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in der Sie eine mehrspaltige PDF-Datei erstellen möchten, die folgenden using-Anweisungen am Anfang der Datei hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Erstellen Sie eine neue Dokumentinstanz
 Instanziieren Sie eine neue`Document` Objekt durch Hinzufügen der folgenden Codezeile:

```csharp
Document doc = new Document();
```

## Schritt 5: Legen Sie die Seitenränder fest
 Geben Sie die Informationen zum linken und rechten Rand für die PDF-Datei mithilfe von an`PageInfo.Margin` Eigentum der`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Schritt 6: Fügen Sie dem Dokument eine Seite hinzu
 Fügen Sie mit dem eine neue Seite zum Dokument hinzu`Add` Methode der`Pages`Sammlung. Im bereitgestellten Code wird die neue Seite der Variablen zugewiesen`page`.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 7: Erstellen Sie ein Graph-Objekt und fügen Sie eine Linie hinzu
 Erstelle eine neue`Graph` Objekt mit bestimmten Abmessungen und fügen Sie eine Linie hinzu. Fügen Sie dann die hinzu`Graph` Einspruch gegen die`Paragraphs` Sammlung der Seite.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Schritt 8: Überschriftentext mit HTML-Formatierung hinzufügen
 Erstelle ein`HtmlFragment` Objekt und setzen Sie dessen Inhalt auf den gewünschten HTML-Text. Fügen Sie dann das Fragment hinzu`Paragraphs` Sammlung der Seite.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Schritt 9: Erstellen Sie eine FloatingBox mit mehreren Spalten
 Ein ... kreieren`FloatingBox` Objekt und legen Sie die Anzahl der Spalten und den Spaltenabstand fest. Fügen Sie dann Textfragmente und eine Zeile hinzu`Paragraphs` Sammlung der`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Schritt 10: Speichern Sie das PDF-Dokument
 Speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt.

```csharp
doc.Save(dataDir);
```

### Beispielquellcode für die Erstellung mehrspaltiger PDFs mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Geben Sie die Informationen zum linken Rand für die PDF-Datei an
doc.PageInfo.Margin.Left = 40;
//Geben Sie die Informationen zum rechten Rand für die PDF-Datei an
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Fügen Sie die Zeile zur paraphraphs-Sammlung des Abschnittsobjekts hinzu
page.Paragraphs.Add(graph1);
// Geben Sie die Koordinaten für die Linie an
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Erstellen Sie String-Variablen mit Text, der HTML-Tags enthält
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Erstellen Sie Textabsätze mit HTML-Text
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Fügen Sie dem Abschnitt vier Spalten hinzu
box.ColumnInfo.ColumnCount = 2;
// Legen Sie den Abstand zwischen den Spalten fest
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Erstellen Sie ein Diagrammobjekt, um eine Linie zu zeichnen
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Geben Sie die Koordinaten für die Linie an
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Fügen Sie die Zeile zur Absatzsammlung des Abschnittsobjekts hinzu
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich ein mehrspaltiges PDF erstellt. Die resultierende PDF-Datei befindet sich nun im angegebenen Ausgabedateipfad.

### FAQs

#### F: Was ist der Schwerpunkt dieses Tutorials?

Der Schwerpunkt dieses Tutorials liegt darauf, Sie durch den Prozess der Erstellung einer mehrspaltigen PDF-Datei mit der Aspose.PDF für .NET-Bibliothek zu führen. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte, um dies zu erreichen.

#### F: Welche Namespaces sollte ich für dieses Tutorial importieren?

A: Importieren Sie in der Codedatei, in der Sie eine mehrspaltige PDF-Datei erstellen möchten, die folgenden Namespaces am Anfang der Datei:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie im Code die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie erstelle ich eine neue Dokumentinstanz?

 A: In Schritt 4 instanziieren Sie eine neue`Document` Objekt mithilfe des bereitgestellten Codes.

#### F: Wie stelle ich die Seitenränder ein?

 A: In Schritt 5 verwenden Sie die`PageInfo.Margin` Eigentum der`Document` , um die Informationen zum linken und rechten Rand für die PDF-Datei anzugeben.

#### F: Wie füge ich dem Dokument eine Seite hinzu?

 A: In Schritt 6 fügen Sie dem Dokument eine neue Seite hinzu`Add` Methode der`Pages` Sammlung.

#### F: Wie erstelle ich ein Graph-Objekt und füge eine Linie hinzu?

 A: In Schritt 7 erstellen Sie ein neues`Graph` Objekt, fügen Sie eine Linie hinzu und fügen Sie dann das hinzu`Graph` Einspruch gegen die`Paragraphs` Sammlung der Seite.

#### F: Wie füge ich Überschriftentext mit HTML-Formatierung hinzu?

 A: In Schritt 8 erstellen Sie eine`HtmlFragment` Objekt und setzen Sie seinen Inhalt auf den gewünschten HTML-Text und fügen Sie dann das Fragment zum hinzu`Paragraphs` Sammlung der Seite.

#### F: Wie erstelle ich eine FloatingBox mit mehreren Spalten?

 A: In Schritt 9 erstellen Sie eine`FloatingBox` Objekt mit mehreren Spalten und Spaltenabstand, fügen Sie dann Textfragmente und eine Zeile hinzu`Paragraphs` Sammlung der`FloatingBox`.

#### F: Wie speichere ich das PDF-Dokument?

 A: In Schritt 10 speichern Sie das PDF-Dokument mit`Save` Methode der`Document` Objekt.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch Befolgen dieses Tutorials haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein mehrspaltiges PDF-Dokument erstellen. Dies kann nützlich sein, um Inhalte in einem strukturierten und organisierten Layout anzuzeigen.