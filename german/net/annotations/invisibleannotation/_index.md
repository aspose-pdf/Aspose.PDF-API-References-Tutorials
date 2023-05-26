---
title: Unsichtbare Anmerkung
linktitle: Unsichtbare Anmerkung
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie PDFs mithilfe von C#-Quellcode mit Aspose.PDF für .NET unsichtbar mit Anmerkungen versehen. Schritt für Schritt Anleitung.
type: docs
weight: 100
url: /de/net/annotations/invisibleannotation/
---
## Anmerkungen in PDF-Dokumenten verstehen

Anmerkungen in PDF-Dokumenten sind eine leistungsstarke Funktion, mit der Sie einem Dokument zusätzliche Informationen oder Notizen hinzufügen können, ohne den eigentlichen Inhalt zu ändern. Sie können verwendet werden, um Text hervorzuheben, die Aufmerksamkeit auf bestimmte Bereiche eines Dokuments zu lenken oder Kommentare oder Feedback hinzuzufügen.

Es gibt viele verschiedene Arten von Anmerkungen, die Sie in PDF-Dokumenten verwenden können, darunter:

- Textanmerkungen
- Linkanmerkungen
- Stempelanmerkungen
- Tonanmerkungen
- Anmerkungen zu Dateianhängen
- und viele mehr

## Erstellen einer unsichtbaren Anmerkung in einem PDF-Dokument mit Aspose.PDF für .NET

 Um mit Aspose.PDF für .NET eine unsichtbare Anmerkung in einem PDF-Dokument zu erstellen, müssen wir zunächst eine erstellen`FreeTextAnnotation` Objekt und geben Sie die Position und Größe der Anmerkung an.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Im obigen Code erstellen wir eine`FreeTextAnnotation`Objekt und geben Sie die Position der Anmerkung auf Seite 2 des PDF-Dokuments an. Wir legen außerdem Schriftart, -größe und -farbe für den Text fest, der in der Anmerkung angezeigt wird.

## Hinzufügen von Merkmalen zur unsichtbaren Anmerkung

Als Nächstes können wir der Anmerkung einige Eigenschaften hinzufügen, beispielsweise eine Rahmenfarbe, Hintergrundfarbe oder Deckkraft.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Im obigen Code setzen wir die Rahmenfarbe der Anmerkung auf Rot.

## Festlegen der Anmerkungsflags

Nachdem wir die Annotation erstellt und ihre Eigenschaften festgelegt haben, können wir die Annotations-Flags festlegen. In diesem Tutorial möchten wir, dass die Anmerkung druckbar, aber nicht sichtbar ist.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## Speichern des geänderten PDF-Dokuments

Schließlich können wir das geänderte PDF-Dokument mit der neuen unsichtbaren Anmerkung speichern.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Beispielquellcode für die Anleitung zur unsichtbaren Annotation mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1