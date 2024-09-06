---
title: Linienobjekt in PDF-Datei hinzufügen
linktitle: Linienobjekt in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein benutzerdefiniertes Linienobjekt in eine PDF-Datei einfügen.
type: docs
weight: 30
url: /de/net/programming-with-graphs/add-line-object/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein Linienobjekt hinzuzufügen.

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

## Schritt 4: Linienobjekt erstellen und zum Diagramm hinzufügen

Wir erstellen ein Linienobjekt mit den angegebenen Koordinaten und fügen es der Formensammlung des Diagramms hinzu.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Schritt 5: Leitungseinrichtung

Wir können Eigenschaften für die Linie angeben, beispielsweise Strichtyp und Strichphase.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Schritt 6: Speichern der PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „AddLineObject_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Beispielquellcode für „Add Line Object“ mit Aspose.PDF für .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Füllfarbe für Graph-Objekt festlegen
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Fügen Sie der Formensammlung des Graph-Objekts ein rechteckiges Objekt hinzu
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET ein Linienobjekt hinzufügen. Dieses Wissen können Sie nun nutzen, um in Ihren Anwendungen PDF-Dokumente mit benutzerdefinierten Linien zu erstellen.

### FAQs zum Hinzufügen von Linienobjekten in PDF-Dateien

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Hinzufügens eines Linienobjekts mit Aspose.PDF für .NET, um Ihre PDF-Dokumente zu verbessern.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus sind Grundkenntnisse in der C#-Programmierung empfehlenswert.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts?

A: Das Graph-Objekt dient als Container für Zeichenelemente. Es wird mit angegebenen Abmessungen erstellt und der Absatzsammlung der Seite hinzugefügt.

#### F: Wie kann ich dem PDF-Dokument ein Linienobjekt hinzufügen?

A: Um ein Linienobjekt hinzuzufügen, erstellen Sie eine Instanz der Linienklasse mit angegebenen Koordinaten und fügen Sie sie der Formensammlung des Diagramms hinzu.

#### F: Kann ich das Erscheinungsbild der Linie anpassen?

A: Ja, Sie können das Erscheinungsbild der Linie anpassen, indem Sie Eigenschaften wie Strichtyp und Strichphase mithilfe der GraphInfo-Eigenschaft des Linienobjekts festlegen.

#### F: Was ist der Zweck der Angabe des Strich-Arrays und der Strich-Phase?

A: Mit den Eigenschaften „Strichanordnung“ und „Strichphase“ können Sie gestrichelte oder gepunktete Linien mit bestimmten Mustern erstellen.

#### F: Wie kann ich die PDF-Datei nach dem Hinzufügen des Linienobjekts speichern?

 A: Nach dem Hinzufügen des Linienobjekts können Sie die resultierende PDF-Datei mit dem`doc.Save(dataDir + "AddLineObject_out.pdf");` Zeile im bereitgestellten Quellcode.

#### F: Gibt es einen Beispielquellcode?

A: Ja, das Tutorial enthält einen Beispielquellcode, auf den Sie bei der Implementierung der beschriebenen Schritte zurückgreifen können.