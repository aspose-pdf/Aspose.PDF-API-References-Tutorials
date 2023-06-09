---
title: Ebenen hinzufügen
linktitle: Ebenen hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Ebenen zu PDF-Dateien hinzufügen. Schritt-für-Schritt-Anleitung mit Code-Tutorials zum Erstellen und Speichern von PDFs mit Ebenen.
type: docs
weight: 20
url: /de/net/programming-with-document/addlayers/
---

Um Ebenen zu einer PDF-Datei hinzuzufügen, verwenden wir Aspose.PDF für .NET. Mit dieser Bibliothek können wir effektiv mit PDF-Dateien in .NET-Anwendungen arbeiten. Befolgen Sie die nachstehenden Schritt-für-Schritt-Anweisungen, um Ebenen mit Aspose.PDF für .NET hinzuzufügen.

## Schritt 1: Erstellen Sie ein neues PDF-Dokument

 Beginnen Sie mit der Erstellung einer neuen Instanz von`Document` Von Aspose.PDF für .NET bereitgestellte Klasse. Dies dient als PDF-Dokument, in dem wir die Ebenen hinzufügen.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Schritt 2: Fügen Sie dem Dokument eine Seite hinzu

Fügen Sie als Nächstes mithilfe von eine Seite zum Dokument hinzu`Add` Methode der`Pages` Sammlung in der`Document` Klasse.

```csharp
Page page = doc.Pages.Add();
```

## Schritt 3: Erstellen Sie Ebenen und fügen Sie sie zur Seite hinzu

 Erstellen Sie Instanzen von`Layer` Klasse für jede Ebene, die Sie der PDF-Datei hinzufügen möchten. Geben Sie für jede Ebene eine eindeutige Kennung und einen Namen an.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

In diesem Tutorial haben wir der Seite drei Ebenen mit unterschiedlichen Farben und Namen hinzugefügt.

## Schritt 4: Speichern Sie die PDF-Datei

 Speichern Sie die geänderte PDF-Datei mit`Save` Methode der`Document` Klasse.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Dieser Code speichert die geänderte PDF-Datei im angegebenen Verzeichnis.

### Beispielquellcode für das Hinzufügen von Ebenen zu PDF-Seiten mit Aspose.PDF für .NET

```csharp            
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Abschluss

In diesem Artikel haben wir eine Schritt-für-Schritt-Anleitung zum Hinzufügen von Ebenen zu PDF-Dateien mit Aspose.PDF für .NET bereitgestellt. Indem Sie den Anweisungen folgen und die bereitgestellten Code-Tutorials nutzen, können Sie ganz einfach Ebenen in Ihre PDF-Dokumente integrieren. Mit Ebenen können Sie die Sichtbarkeit von Inhalten organisieren und steuern und so Ihren Benutzern ein interaktiveres und anpassbareres Erlebnis bieten.