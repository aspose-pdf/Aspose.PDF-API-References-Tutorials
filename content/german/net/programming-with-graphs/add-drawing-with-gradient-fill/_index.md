---
title: Zeichnung mit Verlaufsfüllung hinzufügen
linktitle: Zeichnung mit Verlaufsfüllung hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET eine Zeichnung mit Verlaufsfüllung hinzufügen. Schritt-für-Schritt-Anleitung zum Erstellen attraktiver PDF-Dokumente.
type: docs
weight: 20
url: /de/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
In diesem Tutorial führen wir Sie Schritt für Schritt durch den folgenden C#-Quellcode, um der Programmierung mit Grafiken mithilfe von Aspose.PDF für .NET eine Zeichnung mit Verlaufsfüllung hinzuzufügen.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Schritt 4: Rechteckobjekt erstellen und zum Diagramm hinzufügen

Wir erstellen ein Rechteckobjekt mit angegebenen Abmessungen und fügen es der Formensammlung des Diagramms hinzu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Schritt 5: Konfigurieren der Verlaufsfüllung

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

Dadurch entsteht eine Verlaufsfüllung von Rot nach Blau, vom Punkt (0, 0) zum Punkt (300, 300).

## Schritt 6: Speichern der PDF-Datei

Abschließend speichern wir die entstandene PDF-Datei unter dem Namen „AddDrawingWithGradientFill_out.pdf“ im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Beispielquellcode zum Hinzufügen einer Zeichnung mit Farbverlaufsfüllung unter Verwendung von Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentverzeichnis.
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

In diesem Tutorial haben wir Schritt für Schritt erklärt, wie Sie mit Aspose.PDF für .NET eine Zeichnung mit Verlaufsfüllung in die Programmierung mit Grafiken einfügen. Jetzt können Sie dieses Wissen nutzen, um attraktive PDF-Dokumente mit benutzerdefinierten Designs und Verlaufsfüllungen zu erstellen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Hinzufügens einer Zeichnung mit Verlaufsfüllung zur Programmierung mit Grafiken unter Verwendung von Aspose.PDF für .NET.

#### F: Welche Voraussetzungen müssen vor dem Start erfüllt sein?

A: Stellen Sie vor dem Start sicher, dass Sie die Aspose.PDF-Bibliothek installiert und Ihre Entwicklungsumgebung eingerichtet haben. Darüber hinaus sind Grundkenntnisse in der C#-Programmierung empfehlenswert.

#### F: Wie gebe ich das Verzeichnis zum Speichern der PDF-Datei an?

A: Im bereitgestellten Quellcode können Sie den Wert der Variable „dataDir“ ändern, um das Verzeichnis anzugeben, in dem Sie die resultierende PDF-Datei speichern möchten.

#### F: Was ist der Zweck des Graph-Objekts?

A: Das Graph-Objekt dient als Container für die Zeichenelemente. Es wird mit angegebenen Abmessungen erstellt und der Absatzsammlung der Seite hinzugefügt.

#### F: Wie kann ich die Verlaufsfüllung für eine Form konfigurieren?

A: Um die Farbverlaufsfüllung zu konfigurieren, können Sie die FillColor-Eigenschaft der GraphInfo einer Form mithilfe der GradientAxialShading-Klasse festlegen. Auf diese Weise können Sie die Start- und Endpunkte des Farbverlaufs sowie die Farben für den Übergang definieren.

#### F: Kann ich die Farben und die Richtung der Verlaufsfüllung anpassen?

A: Ja, Sie können die Farben und die Richtung der Verlaufsfüllung anpassen, indem Sie die Farbobjekte anpassen und die Start- und Endpunkte der GradientAxialShading angeben.

#### F: Was ist der letzte Schritt des Tutorials?

A: Im letzten Schritt wird die resultierende PDF-Datei unter dem Namen „AddDrawingWithGradientFill_out.pdf“ im angegebenen Verzeichnis gespeichert.

#### F: Gibt es einen Beispielquellcode?

A: Ja, das Tutorial bietet einen Beispielquellcode, den Sie als Referenz für die Implementierung der beschriebenen Schritte verwenden können.

#### F: Kann ich eine Verlaufsfüllung auch auf andere Formen als Rechtecke anwenden?

A: Ja, Sie können Farbverlaufsfüllungen auch auf andere Formen anwenden. Dazu konfigurieren Sie die FillColor-Eigenschaft der GraphInfo der Form mithilfe der GradientAxialShading-Klasse.