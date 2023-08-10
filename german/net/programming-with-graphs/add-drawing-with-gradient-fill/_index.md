---
title: Zeichnung mit Verlaufsfüllung hinzufügen
linktitle: Zeichnung mit Verlaufsfüllung hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Zeichnung mit Farbverlaufsfüllung hinzufügen. Schritt-für-Schritt-Anleitung zum Erstellen attraktiver PDF-Dokumente.
type: docs
weight: 20
url: /de/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um mit Aspose.PDF für .NET eine Zeichnung mit Farbverlaufsfüllung zur Programmierung mit Grafiken hinzuzufügen.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Schritt 4: Rechteckobjekt erstellen und zum Diagramm hinzufügen

Wir erstellen ein Rechteckobjekt mit angegebenen Abmessungen und fügen es der Formensammlung des Diagramms hinzu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Schritt 5: Verlaufsfüllung konfigurieren

Wir konfigurieren die Verlaufsfüllung für das Rechteck mithilfe der Klasse GradientAxialShading.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Dadurch wird eine Farbverlaufsfüllung von Rot nach Blau vom Punkt (0, 0) zum Punkt (300, 300) erstellt.

## Schritt 6: Speichern der PDF-Datei

Abschließend speichern wir die resultierende PDF-Datei mit dem Namen „AddDrawingWithGradientFill_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Beispielquellcode für „Zeichnung mit Farbverlauf hinzufügen“ mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Abschluss

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET eine Zeichnung mit einer Verlaufsfüllung zur Programmierung mit Grafiken hinzufügen. Jetzt können Sie dieses Wissen nutzen, um attraktive PDF-Dokumente mit benutzerdefinierten Designs und Farbverlaufsfüllungen zu erstellen.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial soll Sie durch den Prozess des Hinzufügens einer Zeichnung mit Farbverlaufsfüllung zur Programmierung mit Grafiken mit Aspose.PDF für .NET führen.

#### F: Welche Voraussetzungen sind vor dem Start erforderlich?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus werden grundlegende Kenntnisse der C#-Programmierung empfohlen.

#### F: Wie lege ich das Verzeichnis zum Speichern der PDF-Datei fest?

A: Im bereitgestellten Quellcode können Sie den Wert der Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts?

A: Das Graph-Objekt dient als Container für die Zeichenelemente. Es wird mit den angegebenen Abmessungen erstellt und der Absatzsammlung der Seite hinzugefügt.

#### F: Wie kann ich die Verlaufsfüllung für eine Form konfigurieren?

A: Um die Verlaufsfüllung zu konfigurieren, können Sie die FillColor-Eigenschaft der GraphInfo einer Form mithilfe der GradientAxialShading-Klasse festlegen. Auf diese Weise können Sie die Start- und Endpunkte des Farbverlaufs sowie die Farben für den Übergang definieren.

#### F: Kann ich die Farben und die Richtung der Verlaufsfüllung anpassen?

A: Ja, Sie können die Farben und die Richtung der Verlaufsfüllung anpassen, indem Sie die Farbobjekte anpassen und die Start- und Endpunkte des GradientAxialShading angeben.

#### F: Was ist der letzte Schritt des Tutorials?

A: Der letzte Schritt besteht darin, die resultierende PDF-Datei mit dem Namen „AddDrawingWithGradientFill_out.pdf“ im angegebenen Verzeichnis zu speichern.

#### F: Ist ein Beispielquellcode verfügbar?

A: Ja, das Tutorial stellt einen Beispielquellcode bereit, den Sie als Referenz für die Implementierung der beschriebenen Schritte verwenden können.

#### F: Kann ich eine Farbverlaufsfüllung auch auf andere Formen als Rechtecke anwenden?

A: Ja, Sie können eine Verlaufsfüllung auch auf andere Formen anwenden. Der Prozess umfasst das Konfigurieren der FillColor-Eigenschaft der GraphInfo der Form mithilfe der GradientAxialShading-Klasse.