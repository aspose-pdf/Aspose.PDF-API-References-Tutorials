---
title: Erstellen Sie ein Rechteck mit Alpha-Farbe
linktitle: Erstellen Sie ein Rechteck mit Alpha-Farbe
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Rechteck mit transparenter Farbe erstellen. Schritt-für-Schritt-Anleitung zum Anpassen der Transparenz.
type: docs
weight: 60
url: /de/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein Rechteck mit Alphafarbe zu erstellen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Instanziieren eines Dokumentobjekts und Hinzufügen einer Seite

Wir erstellen eine Instanz der Document-Klasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Diagrammobjekts und eines Rechtecks

Wir erstellen ein Graph-Objekt mit bestimmten Abmessungen und ein Rechteck mit bestimmten Abmessungen.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Schritt 4: Einrichten der Alphafarbe für das Rechteck

Mit der FromArgb-Methode der System.Drawing.Color-Klasse können wir eine Alphafarbe für das Rechteck angeben.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Schritt 5: Hinzufügen des Rechtecks zum Diagrammobjekt

Wir fügen das Rechteck zur Formensammlung des Graph-Objekts hinzu.

```csharp
canvas.Shapes.Add(rect);
```

## Schritt 6: Erstellen eines zweiten Rechtecks mit einer anderen Alpha-Farbe

Wir erstellen ein zweites Rechteck mit bestimmten Abmessungen und einer anderen Alpha-Farbe.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Schritt 7: Hinzufügen des Diagrammobjekts zur Seite

Wir fügen das Graph-Objekt zur Paragraph-Sammlung des Page-Objekts hinzu.

```csharp
page.Paragraphs.Add(canvas);
```

## Schritt 8: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „CreateRectangleWithAlphaColor_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Beispielquellcode für „Rechteck mit Alphafarbe erstellen“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instanziieren
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page = doc.Pages.Add();
// Erstellen Sie eine Graph-Instanz
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Erstellen Sie ein rechteckiges Objekt mit bestimmten Abmessungen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Legen Sie die Füllfarbe des Diagramms aus der System.Drawing.Color-Struktur anhand eines 32-Bit-ARGB-Werts fest
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Fügen Sie ein rechteckiges Objekt zur Formensammlung der Graph-Instanz hinzu
canvas.Shapes.Add(rect);
// Erstellen Sie ein zweites Rechteckobjekt
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Diagramminstanz zur Absatzsammlung des Seitenobjekts hinzufügen
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET ein Rechteck mit Alphafarbe erstellt. Mit diesem Wissen können Sie nun geometrische Formen mit transparenten Farben in Ihren PDF-Dateien erstellen.

## FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess der Erstellung eines Rechtecks mit Alpha-Farbe mit Aspose.PDF für .NET führen. Sie erfahren, wie Sie Ihren PDF-Dateien geometrische Formen mit transparenten Farben hinzufügen.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus werden grundlegende Kenntnisse der C#-Programmierung empfohlen.

#### F: Wie lege ich das Verzeichnis zum Speichern der PDF-Datei fest?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts und des Rechtecks?

A: Das Graph-Objekt fungiert als Container für Zeichenelemente, während das Rechteck die geometrische Form darstellt, die Sie der PDF-Datei hinzufügen.

#### F: Wie kann ich eine Alphafarbe für das Rechteck einrichten?

A: Sie können mithilfe von eine Alphafarbe für das Rechteck festlegen`FillColor` Eigentum der`GraphInfo` Objekt und das`Color.FromRgb` Methode mit einem ARGB-Wert.

#### F: Kann ich mehrere Rechtecke mit unterschiedlichen Alphafarben erstellen?

A: Ja, Sie können mehrere Rechtecke mit unterschiedlichen Alphafarben erstellen, indem Sie ähnliche Schritte ausführen, wie im Tutorial gezeigt.

#### F: Wie speichere ich die resultierende PDF-Datei, nachdem ich Rechtecke mit Alphafarben erstellt habe?

 A: Nachdem Sie die Rechtecke mit Alphafarben erstellt haben, können Sie die resultierende PDF-Datei mit speichern`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` Zeile im bereitgestellten Quellcode.