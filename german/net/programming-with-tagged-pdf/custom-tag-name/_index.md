---
title: Benutzerdefinierter Tag-Name
linktitle: Benutzerdefinierter Tag-Name
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung eines benutzerdefinierten Tag-Namens mit Aspose.PDF für .NET. Verbessern Sie die Struktur Ihrer PDFs mit benutzerdefinierten Tags.
type: docs
weight: 90
url: /de/net/programming-with-tagged-pdf/custom-tag-name/
---
In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung eines benutzerdefinierten Tag-Namens mit Aspose.PDF für .NET. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert bearbeiten können. Durch die Verwendung benutzerdefinierter Tags können Sie spezifische Strukturinformationen zu Ihrem PDF-Dokument hinzufügen und so die Verwendung und den Zugriff erleichtern.

Lassen Sie uns in den Code eintauchen und lernen, wie Sie mit Aspose.PDF für .NET einen benutzerdefinierten Tag-Namen verwenden.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Aspose.PDF-Bibliothek für .NET installiert.
2. Grundkenntnisse der Programmiersprache C#.

## Schritt 1: Einrichten der Umgebung

Öffnen Sie zunächst Ihre C#-Entwicklungsumgebung und erstellen Sie ein neues Projekt. Stellen Sie sicher, dass Sie in Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzugefügt haben.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments

 Der erste Schritt besteht darin, ein neues PDF-Dokument mit zu erstellen`Document` Klasse.

```csharp
// Erstellen Sie das PDF-Dokument
Document document = new Document();
```

## Schritt 3: Arbeiten Sie mit getaggten Inhalten

Dann erhalten wir den getaggten Inhalt des Dokuments, mit dem wir arbeiten können.

```csharp
// Rufen Sie den getaggten Inhalt des Dokuments ab
ITaggedContent taggedContent = document.TaggedContent;
```

## Schritt 4: Dokumenttitel und Sprache festlegen

Wir können nun den Titel und die Sprache des Dokuments festlegen.

```csharp
// Definieren Sie den Titel und die Sprache des Dokuments
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Schritt 5: Logische Strukturelemente erstellen

Lassen Sie uns nun einige logische Strukturelemente erstellen, um unsere Inhalte zu organisieren.

```csharp
// Erstellen Sie logische Strukturelemente
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Hier erstellen wir Absatzelemente und Spannelemente für unsere Inhalte und weisen ihnen benutzerdefinierte Tags zu.

## Schritt 6: Speichern Sie das getaggte PDF-Dokument

Abschließend speichern wir das getaggte PDF-Dokument.

```csharp
// Speichern Sie das getaggte PDF-Dokument
document.Save(dataDir + "CustomTag.pdf");
```

### Beispielquellcode für einen benutzerdefinierten Tag-Namen mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Erstellen Sie ein PDF-Dokument
Document document = new Document();

// Holen Sie sich Inhalte für die Arbeit mit TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Legen Sie Titel und Sprache für Documentt fest
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Erstellen Sie logische Strukturelemente
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Markiertes PDF-Dokument speichern
document.Save(dataDir + "CustomTag.pdf");

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen benutzerdefinierten Tag-Namen verwenden. Sie können Ihrem PDF-Dokument jetzt mithilfe benutzerdefinierter Tags spezifische Strukturinformationen hinzufügen. Entdecken Sie weitere Funktionen von Aspose.PDF, um sein volles Potenzial zu entdecken.
