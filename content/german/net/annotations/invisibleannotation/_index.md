---
title: Unsichtbare Anmerkung in PDF-Datei
linktitle: Unsichtbare Anmerkung in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Anmerkungen in PDF-Dateien mithilfe von C#-Quellcode unsichtbar machen. Schritt für Schritt Anleitung.
type: docs
weight: 100
url: /de/net/annotations/invisibleannotation/
---
Anmerkungen in PDF-Dateien sind eine leistungsstarke Funktion, mit der Sie einem Dokument zusätzliche Informationen oder Notizen hinzufügen können, ohne den eigentlichen Inhalt zu ändern. Sie können verwendet werden, um Text hervorzuheben, die Aufmerksamkeit auf bestimmte Bereiche eines Dokuments zu lenken oder Kommentare oder Feedback hinzuzufügen.

Es gibt viele verschiedene Arten von Anmerkungen, die Sie in PDF-Dokumenten verwenden können, darunter:

- Textanmerkungen
- Linkanmerkungen
- Stempelanmerkungen
- Tonanmerkungen
- Anmerkungen zu Dateianhängen
- und viele mehr

## Schritt 1: Erstellen einer unsichtbaren Anmerkung in einem PDF-Dokument mit Aspose.PDF für .NET

 Um mit Aspose.PDF für .NET eine unsichtbare Anmerkung in einem PDF-Dokument zu erstellen, müssen wir zunächst eine erstellen`FreeTextAnnotation` Objekt und geben Sie die Position und Größe der Anmerkung an.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Im obigen Code erstellen wir eine`FreeTextAnnotation`Objekt und geben Sie die Position der Anmerkung auf Seite 2 des PDF-Dokuments an. Wir legen außerdem Schriftart, -größe und -farbe für den Text fest, der in der Anmerkung angezeigt wird.

## Schritt 2: Merkmale zur unsichtbaren Anmerkung hinzufügen

Als Nächstes können wir der Anmerkung einige Eigenschaften hinzufügen, beispielsweise eine Rahmenfarbe, Hintergrundfarbe oder Deckkraft.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Im obigen Code setzen wir die Rahmenfarbe der Anmerkung auf Rot.

## Schritt 3: Festlegen der Anmerkungsflags

Nachdem wir die Annotation erstellt und ihre Eigenschaften festgelegt haben, können wir die Annotations-Flags festlegen. In diesem Tutorial möchten wir, dass die Anmerkung druckbar, aber nicht sichtbar ist.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Schritt 4: Speichern des geänderten PDF-Dokuments

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
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Ausgabedatei speichern
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET eine unsichtbare Anmerkung in einem PDF-Dokument erstellt. Unsichtbare Anmerkungen sind eine nützliche Funktion, wenn Sie einem Dokument zusätzliche Informationen oder Notizen hinzufügen möchten, ohne diese dem Leser anzuzeigen. Indem Entwickler der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Quellcode verwenden, können sie ganz einfach unsichtbare Anmerkungen in ihren PDF-Dokumenten erstellen und anpassen. Aspose.PDF für .NET bietet einen umfassenden Satz an Tools für die Arbeit mit Anmerkungen, mit denen Sie die Interaktivität und Benutzerfreundlichkeit Ihrer PDF-Dateien verbessern können.

### FAQs

#### F: Was ist eine unsichtbare Anmerkung in einem PDF-Dokument?

A: Eine unsichtbare Anmerkung in einem PDF-Dokument ist eine Anmerkung, die auf der Seite nicht sichtbar ist, aber zusätzliche Informationen oder Notizen enthält. Es ermöglicht Ihnen, Kommentare oder Feedback hinzuzufügen, ohne diese dem Leser anzuzeigen.

#### F: Welche Arten von Merkmalen können einer unsichtbaren Anmerkung hinzugefügt werden?

A: Einer unsichtbaren Anmerkung können verschiedene Eigenschaften hinzugefügt werden, z. B. Rahmenfarbe, Hintergrundfarbe, Deckkraft, Schriftart, Größe und Farbe für den angezeigten Text.

#### F: Kann ich für eine unsichtbare Anmerkung unterschiedliche Anmerkungsflags festlegen?

A: Ja, Sie können je nach Ihren Anforderungen unterschiedliche Anmerkungsflags für eine unsichtbare Anmerkung festlegen. Sie können beispielsweise festlegen, dass die Anmerkung druckbar, aber nicht sichtbar ist.

#### F: Wie kann ich einer bestimmten Seite des PDF-Dokuments eine unsichtbare Anmerkung hinzufügen?

 A: Um einer bestimmten Seite des PDF-Dokuments eine unsichtbare Anmerkung hinzuzufügen, müssen Sie eine erstellen`FreeTextAnnotation` Objekt und geben Sie die Position und Größe der Anmerkung auf dieser Seite an.

#### F: Kann ich die Eigenschaften einer vorhandenen unsichtbaren Anmerkung in einer PDF-Datei ändern?

A: Ja, Sie können die Eigenschaften einer vorhandenen unsichtbaren Anmerkung in einer PDF-Datei mit Aspose.PDF für .NET ändern. Sie können Schriftart, Größe, Farbe, Rahmenfarbe, Hintergrundfarbe, Deckkraft und andere Eigenschaften der Anmerkung ändern.