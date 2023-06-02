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

### Beispielquellcode für „Rechteck mit Alphafarbe erstellen“ mit Aspose.Words für .NET 

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
// Legen Sie die Füllfarbe des Diagramms aus der System.Drawing.Color-Struktur anhand eines 32-Bit-ARGB-Werts fest
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
