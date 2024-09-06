---
title: Rechteck mit Alphafarbe erstellen
linktitle: Rechteck mit Alphafarbe erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Rechteck mit transparenter Farbe erstellen. Schritt-für-Schritt-Anleitung zum Anpassen der Transparenz.
type: docs
weight: 60
url: /de/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein Rechteck mit Alphafarbe zu erstellen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Sie benötigen außerdem Grundkenntnisse in der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts und Hinzufügen einer Seite

Wir erstellen eine Instanz der Dokumentklasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Graphobjekts und eines Rechtecks

Wir erstellen ein Graph-Objekt mit bestimmten Abmessungen und ein Rechteck mit bestimmten Abmessungen.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Schritt 4: Einrichten der Alphafarbe für das Rechteck

Wir können mit der Methode FromArgb der Klasse System.Drawing.Color eine Alphafarbe für das Rechteck angeben.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Schritt 5: Hinzufügen des Rechtecks zum Graphobjekt

Wir fügen das Rechteck der Formensammlung des Graph-Objekts hinzu.

```csharp
canvas.Shapes.Add(rect);
```

## Schritt 6: Erstellen eines zweiten Rechtecks mit einer anderen Alphafarbe

Wir erstellen ein zweites Rechteck mit bestimmten Abmessungen und einer anderen Alphafarbe.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Schritt 7: Hinzufügen des Graph-Objekts zur Seite

Wir fügen das Graph-Objekt der Paragraph-Sammlung des Page-Objekts hinzu.

```csharp
page.Paragraphs.Add(canvas);
```

## Schritt 8: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „CreateRectangleWithAlphaColor_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Beispielquellcode zum Erstellen eines Rechtecks mit Alphafarbe unter Verwendung von Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instantiieren
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page = doc.Pages.Add();
// Graph-Instanz erstellen
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Erstellen Sie ein rechteckiges Objekt mit bestimmten Abmessungen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Legen Sie die Füllfarbe des Diagramms aus der System.Drawing.Color-Struktur aus einem 32-Bit-ARGB-Wert fest
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Fügen Sie der Formensammlung der Graph-Instanz ein rechteckiges Objekt hinzu
canvas.Shapes.Add(rect);
// Zweites Rechteckobjekt erstellen
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Fügen Sie der Absatzsammlung des Seitenobjekts eine Diagramminstanz hinzu
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET ein Rechteck mit Alphafarbe erstellt. Dieses Wissen können Sie nun nutzen, um geometrische Formen mit transparenten Farben in Ihren PDF-Dateien zu erstellen.

## Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess der Erstellung eines Rechtecks mit Alphafarbe mithilfe von Aspose.PDF für .NET. Sie erfahren, wie Sie Ihren PDF-Dateien geometrische Formen mit transparenten Farben hinzufügen.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus sind Grundkenntnisse in der C#-Programmierung empfehlenswert.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts und des Rechtecks?

A: Das Graph-Objekt fungiert als Container zum Zeichnen von Elementen, während das Rechteck die geometrische Form darstellt, die Sie der PDF-Datei hinzufügen.

#### F: Wie kann ich eine Alphafarbe für das Rechteck einrichten?

 A: Sie können eine Alphafarbe für das Rechteck festlegen mit dem`FillColor` Eigentum der`GraphInfo` Objekt und die`Color.FromRgb` Methode mit einem ARGB-Wert.

#### F: Kann ich mehrere Rechtecke mit unterschiedlichen Alphafarben erstellen?

A: Ja, Sie können mehrere Rechtecke mit unterschiedlichen Alphafarben erstellen, indem Sie ähnliche Schritte ausführen, wie im Tutorial gezeigt.

#### F: Wie speichere ich die resultierende PDF-Datei, nachdem ich Rechtecke mit Alphafarben erstellt habe?

 A: Nachdem Sie die Rechtecke mit Alphafarben erstellt haben, können Sie die resultierende PDF-Datei mit dem`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` Zeile im bereitgestellten Quellcode.