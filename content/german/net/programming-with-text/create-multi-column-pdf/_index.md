---
title: Mehrspaltiges PDF erstellen
linktitle: Mehrspaltiges PDF erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mehrspaltige PDFs erstellen. Eine Schritt-für-Schritt-Anleitung mit Codebeispielen und ausführlichen Erklärungen. Perfekt für Profis.
type: docs
weight: 110
url: /de/net/programming-with-text/create-multi-column-pdf/
---
## Einführung

Das Erstellen mehrspaltiger PDFs ist eine großartige Möglichkeit, Text in einem besser organisierten und lesbaren Format darzustellen. Ob Sie nun einen Bericht, einen Artikel oder ein Layout für eine Veröffentlichung erstellen, mehrspaltige Strukturen können Ihren Inhalt ansprechender machen. In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein mehrspaltiges PDF erstellen. Keine Sorge, wir unterteilen alles in einfache Schritte, die es leicht nachvollziehbar machen, selbst wenn Sie neu auf der Plattform sind.

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen Sie ein paar Dinge vorbereitet haben, damit Sie problemlos mitmachen können:

1.  Aspose.PDF für .NET: Sie müssen diese Bibliothek installiert haben. Sie können sie herunterladen von[Hier](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Richten Sie Ihre bevorzugte IDE wie Visual Studio zum Schreiben und Ausführen von C#-Code ein.
3. .NET Framework: Stellen Sie sicher, dass Sie eine kompatible Version von .NET installiert haben.
4. Grundlegende Kenntnisse in C#: Kenntnisse der C#-Syntax sind hilfreich, wir erklären jedoch jeden Schritt im Detail.
5.  Temporäre Lizenz: Aspose.PDF erfordert eine Lizenz, um Wasserzeichen oder Einschränkungen zu vermeiden. Sie können eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) falls erforderlich.

## Pakete importieren

Bevor Sie mit dem Codieren beginnen, müssen Sie die erforderlichen Namespaces importieren, die Ihnen die Interaktion mit Aspose.PDF ermöglichen. Folgendes müssen Sie importieren:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Diese Namespaces bieten Zugriff auf die Klassen, die zum Erstellen von PDFs, Zeichnen von Formen und Verwalten der Textformatierung erforderlich sind.

Lassen Sie uns den Prozess der Erstellung einer mehrspaltigen PDF-Datei in einfache, überschaubare Schritte aufteilen.

## Schritt 1: Einrichten des Dokuments

Zu Beginn müssen Sie ein neues PDF-Dokument erstellen. Dazu müssen Sie die Ränder definieren und eine Seite hinzufügen, auf der Ihr Inhalt erscheinen soll.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Neues PDF-Dokument erstellen
Document doc = new Document();

// Legen Sie die Ränder für die PDF-Datei fest
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Dem Dokument eine Seite hinzufügen
Page page = doc.Pages.Add();
```

 Hier haben wir ein`Document`Objekt und stellen Sie die linken und rechten Ränder auf 40 Einheiten ein. Dann haben wir diesem Dokument eine neue Seite hinzugefügt, die unser mehrspaltiges Layout enthalten wird.

## Schritt 2: Hinzufügen einer Zeile zum Trennen von Abschnitten

Als Nächstes fügen wir der Seite zur optischen Trennung eine horizontale Linie hinzu. Dies trägt zu einem sauberen und professionellen Erscheinungsbild bei.

```csharp
// Erstellen Sie ein Diagrammobjekt zum Halten der Linie
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Fügen Sie die Zeile zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(graph1);

// Definieren Sie die Koordinaten für die Linie
float[] posArr = new float[] { 1, 2, 500, 2 };

// Erstellen Sie eine Linie und fügen Sie sie dem Diagramm hinzu
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 Hier erstellen wir eine horizontale Linie mit dem`Graph` Und`Line` Klassen. Diese Zeile wird zur Seite hinzugefügt`Paragraphs` Sammlung, die alle visuellen Elemente enthält.

## Schritt 3: Hinzufügen von HTML-Text mit Formatierung

Als Nächstes fügen wir einen Text mit HTML-Tags ein, um zu zeigen, wie Sie Text im PDF dynamisch formatieren können.

```csharp
// Erstellen Sie eine Zeichenfolge mit HTML-Inhalt
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Erstellen Sie ein neues HtmlFragment mit dem formatierten Text
HtmlFragment heading_text = new HtmlFragment(s);

// Fügen Sie den HTML-Text zur Seite hinzu
page.Paragraphs.Add(heading_text);
```

 Mit dem`HtmlFragment`Klasse können wir formatierten Text hinzufügen, der HTML-Tags wie Schriftgröße, -stil und Fettschrift enthält. Dies ist nützlich, um das Erscheinungsbild Ihres PDF-Inhalts zu verbessern.

## Schritt 4: Erstellen eines mehrspaltigen Layouts

Jetzt erstellen wir ein mehrspaltiges Layout. Hier geschieht die Magie – Sie können angeben, wie viele Spalten Sie möchten und wie breit sie sein sollen.

```csharp
// Erstellen Sie eine schwebende Box, um die Spalten aufzunehmen
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Legen Sie die Anzahl der Spalten und den Abstand zwischen ihnen fest
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Fügen Sie das Feld zur Seite hinzu
page.Paragraphs.Add(box);
```

Hier erstellen wir eine schwebende Box, die zwei Spalten enthalten soll. Wir legen den Abstand zwischen den Spalten fest und geben an, dass jede Spalte 105 Einheiten breit sein soll. Dadurch können wir das gewünschte Spaltenlayout innerhalb der PDF-Datei erstellen.

## Schritt 5: Text zu den Spalten hinzufügen

 Füllen wir nun die Spalten mit Textinhalten. Sie können verschiedene`TextFragment` Objekte zu jeder Spalte hinzufügen.

```csharp
// Erstellen und formatieren Sie das erste Textfragment
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Fügen Sie eine weitere Linie zur Trennung hinzu
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//Erstellen und Hinzufügen eines zweiten Textfragments
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 Wir fügen ein`TextFragment` zur schwebenden Box, gefolgt von einer weiteren horizontalen Linie. Die zweite`TextFragment` enthält weiteren Text, um die zweite Spalte zu füllen. Diese Fragmente ermöglichen es uns, der PDF-Datei verschiedene Textelemente mit unterschiedlichen Formatierungsoptionen hinzuzufügen.

## Schritt 6: Speichern der PDF

Nachdem Sie alle Inhalte hinzugefügt haben, besteht der letzte Schritt darin, das Dokument als PDF-Datei zu speichern.

```csharp
// Definieren Sie den Ausgabepfad für die PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Speichern des PDF-Dokuments
doc.Save(dataDir);

// Erfolgsmeldung ausgeben
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

Dieser Block speichert die PDF-Datei im angegebenen Verzeichnis und gibt eine Erfolgsmeldung in der Konsole aus. Das PDF ist nun zur Anzeige bereit!

## Abschluss

Wenn Sie diese einfachen Schritte befolgen, können Sie mit Aspose.PDF für .NET ganz einfach ein professionell aussehendes mehrspaltiges PDF erstellen. Ob für einen Bericht, einen Artikel oder einen Newsletter, diese Technik hilft dabei, Inhalte in ein optisch ansprechendes Format zu bringen. Aspose.PDF bietet leistungsstarke Tools zum Anpassen Ihrer PDFs, von Rändern und Layout bis hin zur Textformatierung und zum Zeichnen von Formen. Jetzt sind Sie an der Reihe, es auszuprobieren und Ihre Fähigkeiten zur PDF-Erstellung auf die nächste Stufe zu heben!

## Häufig gestellte Fragen

### Kann ich in einer PDF mehr als zwei Spalten erstellen?
 Ja, Sie können so viele Spalten erstellen, wie Sie benötigen. Passen Sie einfach die`ColumnCount` -Eigenschaft, um die gewünschte Spaltenanzahl anzupassen.

### Wie ändere ich die Breite jeder Spalte?
 Sie können die`ColumnWidths` -Eigenschaft, um für jede Spalte eine andere Breite anzugeben. Diese Eigenschaft akzeptiert eine Zeichenfolge mit durch Leerzeichen getrennten Werten.

### Ist es möglich, den Spalten Bilder hinzuzufügen?
 Auf jeden Fall! Sie können Bilder hinzufügen mit dem`Image` Klasse und fügen Sie sie in die schwebende Box oder ein anderes Layoutelement in Ihrem PDF ein.

### Kann ich Text mit HTML-Tags in den Spalten formatieren?
 Ja, Sie können HTML-Tags verwenden innerhalb`HtmlFragment` Objekte, um Ihren Text zu gestalten. Dazu gehört das Hinzufügen von Schriftarten, Größen, Farben und mehr.

### Wie kann ich weitere Seiten mit demselben Spaltenlayout hinzufügen?
 Sie können weitere Seiten hinzufügen mit`doc.Pages.Add()` und wiederholen Sie den Vorgang des Hinzufügens von Spalten und Inhalten für jede Seite.