---
title: Strichlänge
linktitle: Strichlänge
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie die Länge von Bindestrichen mit Aspose.PDF für .NET festlegen. Schritt-für-Schritt-Anleitung zum Anpassen von Strichmustern.
type: docs
weight: 70
url: /de/net/programming-with-graphs/dash-length/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um die Länge von Bindestrichen mithilfe von Aspose.PDF für .NET festzulegen.

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
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen eines Diagrammobjekts und Hinzufügen zur Seite

Wir erstellen ein Graph-Objekt mit angegebenen Abmessungen und fügen es der Absatzsammlung der Seite hinzu.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Schritt 4: Erstellen eines Linienobjekts und Konfigurieren

Wir erstellen ein Linienobjekt mit den angegebenen Koordinaten und konfigurieren die Farbe und Länge der Striche.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Schritt 5: Hinzufügen der Linie zum Diagrammobjekt

Wir fügen die Linie zur Formensammlung des Graph-Objekts hinzu.

```csharp
canvas.Shapes.Add(line);
```

## Schritt 6: Speichern der resultierenden PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „DashLength_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Beispielquellcode für Dash-Länge mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentinstanz instanziieren
Document doc = new Document();
// Seite zur Seitensammlung des Dokumentobjekts hinzufügen
Page page = doc.Pages.Add();
// Erstellen Sie ein Zeichnungsobjekt mit bestimmten Abmessungen
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Zeichnungsobjekt zur Absatzsammlung der Seiteninstanz hinzufügen
page.Paragraphs.Add(canvas);
// Linienobjekt erstellen
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Legen Sie die Farbe für das Linienobjekt fest
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Geben Sie das Strich-Array für das Linienobjekt an
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Legen Sie die Strichphase für die Linieninstanz fest
line.GraphInfo.DashPhase = 1;
// Fügen Sie der Formensammlung des Zeichnungsobjekts eine Linie hinzu
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF-Dokument speichern
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir erklärt, wie Sie die Länge von Bindestrichen mit Aspose.PDF für .NET festlegen. Jetzt können Sie dieses Wissen nutzen, um Linien mit benutzerdefinierten Strichmustern in Ihren PDF-Dateien zu erstellen.

## FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Der Zweck dieses Tutorials besteht darin, Sie durch den Prozess zum Festlegen der Länge von Strichen für Linien mit Aspose.PDF für .NET zu führen. Sie erfahren, wie Sie in Ihren PDF-Dateien Linien mit benutzerdefinierten Strichmustern erstellen.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Ein grundlegendes Verständnis der C#-Programmierung wird ebenfalls empfohlen.

#### F: Wie lege ich das Verzeichnis zum Speichern der PDF-Datei fest?

A: Ändern Sie die Variable „dataDir“ im bereitgestellten Quellcode, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Wie erstelle ich eine Linie mit benutzerdefinierten Strichmustern?

 A: Das Tutorial zeigt das Erstellen eines Linienobjekts und das Konfigurieren seiner Farbe, seines Stricharrays und seiner Strichphase mithilfe von`GraphInfo` Objekt. Ändern Sie diese Einstellungen, um das gewünschte Strichmuster zu erzielen.

#### F: Kann ich die Farbe der Linie anpassen?

 A: Ja, Sie können die Farbe der Linie anpassen, indem Sie festlegen`Color` Eigentum der`GraphInfo` Objekt, das der Linie zugeordnet ist.

#### F: Wie speichere ich das PDF-Dokument, nachdem ich die Strichlänge festgelegt habe?

 A: Nachdem Sie das Linienobjekt mit dem gewünschten Strichmuster konfiguriert haben, können Sie das resultierende PDF-Dokument mit speichern`doc.Save(dataDir + "DashLength_out.pdf");` Zeile im bereitgestellten Quellcode.