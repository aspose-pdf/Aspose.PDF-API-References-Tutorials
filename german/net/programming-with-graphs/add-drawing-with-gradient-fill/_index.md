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

### Beispielquellcode für „Zeichnung mit Farbverlauf hinzufügen“ mit Aspose.Words für .NET 

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