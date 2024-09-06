---
title: Strichlänge
linktitle: Strichlänge
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET die Länge von Strichen festlegen. Schritt-für-Schritt-Anleitung zum Anpassen von Strichmustern.
type: docs
weight: 70
url: /de/net/programming-with-graphs/dash-length/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um die Länge von Strichen mit Aspose.PDF für .NET festzulegen.

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
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Graph-Objekts und Hinzufügen zur Seite

Wir erstellen ein Graph-Objekt mit angegebenen Dimensionen und fügen es der Absatzsammlung der Seite hinzu.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Schritt 4: Linienobjekt erstellen und konfigurieren

Wir erstellen ein Linienobjekt mit den angegebenen Koordinaten und konfigurieren die Farbe und Länge der Striche.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Schritt 5: Hinzufügen der Linie zum Graphobjekt

Wir fügen die Linie der Formensammlung des Graph-Objekts hinzu.

```csharp
canvas.Shapes.Add(line);
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „DashLength_out.pdf“ im angegebenen Verzeichnis ab.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Beispiel-Quellcode für Dash Length mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instantiieren
Document doc = new Document();
// Seite zur Seitensammlung des Dokumentobjekts hinzufügen
Page page = doc.Pages.Add();
// Zeichenobjekt mit bestimmten Abmessungen erstellen
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Zeichenobjekt zur Absatzsammlung der Seiteninstanz hinzufügen
page.Paragraphs.Add(canvas);
// Linienobjekt erstellen
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Farbe für Linienobjekt festlegen
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Strich-Array für Linienobjekt festlegen
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Festlegen der Strichphase für die Linieninstanz
line.GraphInfo.DashPhase = 1;
// Linie zur Formensammlung des Zeichenobjekts hinzufügen
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Länge von Strichen mit Aspose.PDF für .NET festlegen. Jetzt können Sie dieses Wissen nutzen, um Linien mit benutzerdefinierten Strichmustern in Ihren PDF-Dateien zu erstellen.

## FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess zum Festlegen der Strichlänge für Linien mit Aspose.PDF für .NET. Sie erfahren, wie Sie Linien mit benutzerdefinierten Strichmustern in Ihren PDF-Dateien erstellen.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Grundlegende Kenntnisse der C#-Programmierung werden ebenfalls empfohlen.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Ändern Sie die Variable „dataDir“ im bereitgestellten Quellcode, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Wie erstelle ich eine Linie mit benutzerdefinierten Strichmustern?

 A: Das Tutorial zeigt die Erstellung eines Linienobjekts und die Konfiguration seiner Farbe, Strichanordnung und Strichphase mithilfe des`GraphInfo` Objekt. Ändern Sie diese Einstellungen, um das gewünschte Strichmuster zu erhalten.

#### F: Kann ich die Farbe der Linie anpassen?

 A: Ja, Sie können die Farbe der Linie anpassen, indem Sie die`Color` Eigentum der`GraphInfo` Objekt, das mit der Linie verknüpft ist.

#### F: Wie speichere ich das PDF-Dokument, nachdem ich die Strichlänge festgelegt habe?

 A: Nachdem Sie das Linienobjekt mit dem gewünschten Strichmuster konfiguriert haben, können Sie das resultierende PDF-Dokument mit dem`doc.Save(dataDir + "DashLength_out.pdf");` Zeile im bereitgestellten Quellcode.