---
title: Erstellen Sie ein gefülltes Rechteck
linktitle: Erstellen Sie ein gefülltes Rechteck
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein gefülltes Rechteck erstellen. Schritt-für-Schritt-Anleitung zum Anpassen der Füllfarbe.
type: docs
weight: 50
url: /de/net/programming-with-graphs/create-filled-rectangle/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein gefülltes Rechteck zu erstellen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Außerdem verfügen Sie über Grundkenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen einer Dokumentinstanz und Hinzufügen einer Seite

Wir erstellen eine Instanz der Document-Klasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Diagrammobjekts und Hinzufügen zur Seite

Wir erstellen ein Graph-Objekt mit angegebenen Abmessungen und fügen es der Absatzsammlung der Seite hinzu.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Schritt 4: Rechteckobjekt erstellen und zum Diagramm hinzufügen

Wir erstellen ein Rechteckobjekt mit den angegebenen Abmessungen und fügen es der Formensammlung des Diagramms hinzu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Schritt 5: Füllfarbe festlegen

Wir können die Füllfarbe für das Rechteck mithilfe der FillColor-Eigenschaft des GraphInfo-Objekts angeben.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „CreateFilledRectangle_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Beispielquellcode für „Gefülltes Rechteck erstellen“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
// Erstellen Sie eine Graph-Instanz
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Diagrammobjekt zur Absatzsammlung der Seiteninstanz hinzufügen
page.Paragraphs.Add(graph);
// Erstellen Sie eine Rechteckinstanz
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Geben Sie die Füllfarbe für das Diagrammobjekt an
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Fügen Sie ein Rechteckobjekt zur Formensammlung des Diagrammobjekts hinzu
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie man mit Aspose.PDF für .NET ein gefülltes Rechteck erstellt. Sie können dieses Wissen nun nutzen, um geometrische Formen mit benutzerdefinierten Füllfarben in Ihren PDF-Dateien zu erstellen.
