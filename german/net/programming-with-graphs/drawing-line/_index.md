---
title: Zeichnungslinie
linktitle: Zeichnungslinie
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Linie über eine Seite zeichnen. Schritt-für-Schritt-Anleitung zum Erstellen benutzerdefinierter Linien.
type: docs
weight: 80
url: /de/net/programming-with-graphs/drawing-line/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET eine Linie zu zeichnen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen einer Dokumentinstanz und Hinzufügen einer Seite

Wir erstellen eine Instanz der Document-Klasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Schritt 3: Seitenränder festlegen

Wir setzen die Seitenränder auf allen Seiten auf 0.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Schritt 4: Erstellen eines Diagrammobjekts und der ersten Zeile

Wir erstellen ein Diagrammobjekt mit Abmessungen, die denen der Seite entsprechen, und zeichnen die erste Linie von der unteren linken Ecke zur oberen rechten Ecke der Seite.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Schritt 5: Zeichnen Sie die zweite Linie

Wir zeichnen die zweite Linie von der oberen linken Ecke zur unteren rechten Ecke der Seite.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Schritt 6: Hinzufügen des Diagrammobjekts zur Seite

Wir fügen das Graph-Objekt zur Absatzsammlung der Seite hinzu.

```csharp
pg.Paragraphs.Add(graph);
```

## Schritt 7: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „DrawingLine_out.pdf“ im angegebenen Verzeichnis.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Beispielquellcode für Drawing Line mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document pDoc = new Document();
// Seite zur Seitensammlung des PDF-Dokuments hinzufügen
Page pg = pDoc.Pages.Add();
// Stellen Sie den Seitenrand auf allen Seiten auf 0 ein
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Erstellen Sie ein Diagrammobjekt mit Breite und Höhe, die den Seitenabmessungen entsprechen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Erstellen Sie ein Objekt für die erste Zeile, beginnend von der unteren linken bis zur oberen rechten Ecke der Seite
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Fügen Sie der Formensammlung des Graph-Objekts eine Linie hinzu
graph.Shapes.Add(line);
// Zeichnen Sie eine Linie von der oberen linken Ecke der Seite zur unteren rechten Ecke der Seite
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Fügen Sie der Formensammlung des Graph-Objekts eine Linie hinzu
graph.Shapes.Add(line2);
// Fügen Sie ein Diagrammobjekt zur Absatzsammlung der Seite hinzu
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF-Datei speichern
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET eine Linie zeichnet. Sie können dieses Wissen nun nutzen, um geometrische Formen mit benutzerdefinierten Linien in Ihren PDF-Dateien zu erstellen.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Der Zweck dieses Tutorials besteht darin, Sie durch den Prozess des Zeichnens von Linien mit Aspose.PDF für .NET zu führen. Sie erfahren, wie Sie Linien auf einer PDF-Seite erstellen und deren Aussehen anpassen.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Grundkenntnisse in der C#-Programmierung werden ebenfalls empfohlen.

#### F: Wie lege ich das Verzeichnis zum Speichern der PDF-Datei fest?

A: Ändern Sie die Variable „dataDir“ im bereitgestellten Quellcode, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Wie erstelle ich Linien auf einer PDF-Seite?

A: Das Tutorial zeigt, wie Sie ein Diagrammobjekt mit den Abmessungen der Seite erstellen und ihm anschließend Linienobjekte hinzufügen. Ändern Sie die Koordinaten und Eigenschaften der Linienobjekte, um die gewünschten Linien zu erstellen.

#### F: Kann ich das Erscheinungsbild der Linien anpassen?

A: Ja, Sie können das Erscheinungsbild der Linien anpassen, indem Sie die Eigenschaften der Linienobjekte ändern. Dazu gehört das Ändern ihrer Koordinaten, Farbe, Dicke und anderer grafischer Attribute.

#### F: Wie speichere ich das PDF-Dokument nach dem Zeichnen der Linien?

A: Nachdem Sie das Graph-Objekt mit Line-Objekten zur Seite hinzugefügt haben, können Sie das resultierende PDF-Dokument mit speichern`pDoc.Save(dataDir + "DrawingLine_out.pdf");` Zeile im bereitgestellten Quellcode.

#### F: Kann ich Linien mit unterschiedlichen Winkeln und Ausrichtungen zeichnen?

A: Ja, Sie können Linien mit unterschiedlichen Winkeln und Ausrichtungen zeichnen, indem Sie die Koordinaten und Eigenschaften der Linienobjekte im Diagramm anpassen.