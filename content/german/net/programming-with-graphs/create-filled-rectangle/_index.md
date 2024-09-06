---
title: Gefülltes Rechteck erstellen
linktitle: Gefülltes Rechteck erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein gefülltes Rechteck erstellen. Schritt-für-Schritt-Anleitung zum Anpassen der Füllfarbe.
type: docs
weight: 50
url: /de/net/programming-with-graphs/create-filled-rectangle/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein ausgefülltes Rechteck zu erstellen.

Stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben, bevor Sie beginnen. Sie benötigen außerdem Grundkenntnisse in der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im bereitgestellten Quellcode müssen Sie das Verzeichnis angeben, in dem Sie die resultierende PDF-Datei speichern möchten. Ändern Sie die Variable „dataDir“ in das gewünschte Verzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen einer Dokumentinstanz und Hinzufügen einer Seite

Wir erstellen eine Instanz der Dokumentklasse und fügen diesem Dokument eine Seite hinzu.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Graph-Objekts und Hinzufügen zur Seite

Wir erstellen ein Graph-Objekt mit angegebenen Dimensionen und fügen es der Absatzsammlung der Seite hinzu.

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

Wir können die Füllfarbe für das Rechteck mit der FillColor-Eigenschaft des GraphInfo-Objekts angeben.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „CreateFilledRectangle_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Beispielquellcode zum Erstellen eines gefüllten Rechtecks mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz erstellen
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Page page = doc.Pages.Add();
// Graph-Instanz erstellen
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Graph-Objekt zur Absatzsammlung der Seiteninstanz hinzufügen
page.Paragraphs.Add(graph);
// Rechteckinstanz erstellen
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Füllfarbe für Graph-Objekt festlegen
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Fügen Sie der Formensammlung des Graph-Objekts ein rechteckiges Objekt hinzu
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie mit Aspose.PDF für .NET ein gefülltes Rechteck erstellen. Dieses Wissen können Sie nun nutzen, um geometrische Formen mit benutzerdefinierten Füllfarben in Ihren PDF-Dateien zu erstellen.

## Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Der Zweck dieses Tutorials besteht darin, Sie durch den Prozess der Erstellung eines ausgefüllten Rechtecks mit Aspose.PDF für .NET zu führen, sodass Sie Ihren PDF-Dateien benutzerdefinierte geometrische Formen mit Füllfarben hinzufügen können.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus sind Grundkenntnisse in der C#-Programmierung empfehlenswert.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts?

A: Das Graph-Objekt fungiert als Container für Zeichenelemente. Es wird mit angegebenen Abmessungen erstellt und der Absatzsammlung der Seite hinzugefügt.

#### F: Wie kann ich dem PDF-Dokument ein ausgefülltes Rechteck hinzufügen?

A: Um ein ausgefülltes Rechteck hinzuzufügen, erstellen Sie eine Instanz der Rectangle-Klasse mit angegebenen Abmessungen und Füllfarbe und fügen Sie sie der Formensammlung des Diagramms hinzu.

#### F: Kann ich die Abmessungen und die Füllfarbe des Rechtecks anpassen?

 A: Ja, Sie können die Abmessungen und die Füllfarbe des Rechtecks anpassen, indem Sie die an den`Aspose.Pdf.Drawing.Rectangle` Konstruktor und Festlegen der FillColor-Eigenschaft.

#### F: Wie speichere ich die resultierende PDF-Datei, nachdem ich das ausgefüllte Rechteck erstellt habe?

 A: Nach dem Erstellen des ausgefüllten Rechtecks können Sie die resultierende PDF-Datei mit dem`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` Zeile im bereitgestellten Quellcode.