---
title: Linienobjekt in PDF-Datei hinzufügen
linktitle: Linienobjekt in PDF-Datei hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein benutzerdefiniertes Linienobjekt in eine PDF-Datei hinzufügen.
type: docs
weight: 30
url: /de/net/programming-with-graphs/add-line-object/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET ein Linienobjekt hinzuzufügen.

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

## Schritt 4: Linienobjekt erstellen und zum Diagramm hinzufügen

Wir erstellen ein Linienobjekt mit den angegebenen Koordinaten und fügen es der Formensammlung des Diagramms hinzu.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Schritt 5: Leitungseinrichtung

Wir können Eigenschaften für die Linie angeben, z. B. den Strichtyp und die Strichphase.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Schritt 6: Speichern der PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „AddLineObject_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Beispielquellcode für „Linienobjekt hinzufügen“ mit Aspose.PDF für .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Geben Sie die Füllfarbe für das Diagrammobjekt an
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Fügen Sie ein Rechteckobjekt zur Formensammlung des Diagrammobjekts hinzu
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF-Datei speichern
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Abschluss

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie man mit Aspose.PDF für .NET ein Linienobjekt hinzufügt. Dieses Wissen können Sie nun nutzen, um PDF-Dokumente mit benutzerdefinierten Zeilen in Ihren Anwendungen zu erstellen.

### FAQs zum Hinzufügen eines Linienobjekts in einer PDF-Datei

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess des Hinzufügens eines Linienobjekts mit Aspose.PDF für .NET führen, um Ihre PDF-Dokumente zu verbessern.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus werden grundlegende Kenntnisse der C#-Programmierung empfohlen.

#### F: Wie lege ich das Verzeichnis zum Speichern der PDF-Datei fest?

A: Im bereitgestellten Quellcode können Sie die Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts?

A: Das Graph-Objekt dient als Container für Zeichenelemente. Es wird mit den angegebenen Abmessungen erstellt und der Absatzsammlung der Seite hinzugefügt.

#### F: Wie kann ich dem PDF-Dokument ein Linienobjekt hinzufügen?

A: Um ein Linienobjekt hinzuzufügen, erstellen Sie eine Instanz der Line-Klasse mit angegebenen Koordinaten und fügen Sie sie der Formensammlung des Diagramms hinzu.

#### F: Kann ich das Erscheinungsbild der Linie anpassen?

A: Ja, Sie können das Erscheinungsbild der Linie anpassen, indem Sie Eigenschaften wie Strichtyp und Strichphase mithilfe der GraphInfo-Eigenschaft des Line-Objekts festlegen.

#### F: Was ist der Zweck der Angabe des Dash-Arrays und der Dash-Phase?

A: Mit den Eigenschaften Strich-Array und Strich-Phase können Sie gestrichelte oder gepunktete Linien mit bestimmten Mustern erstellen.

#### F: Wie kann ich die PDF-Datei speichern, nachdem ich das Linienobjekt hinzugefügt habe?

 A: Nachdem Sie das Linienobjekt hinzugefügt haben, können Sie die resultierende PDF-Datei mit speichern`doc.Save(dataDir + "AddLineObject_out.pdf");` Zeile im bereitgestellten Quellcode.

#### F: Ist ein Beispielquellcode verfügbar?

A: Ja, das Tutorial enthält einen Beispielquellcode, auf den Sie zur Implementierung der beschriebenen Schritte zurückgreifen können.