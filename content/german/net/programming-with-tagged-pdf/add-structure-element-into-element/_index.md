---
title: Strukturelement zum Element hinzufügen
linktitle: Strukturelement zum Element hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Hinzufügen von Strukturelementen zu Elementen in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
In diesem Tutorial stellen wir Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, wie Sie mit Aspose.PDF für .NET ein Strukturelement zu einem Element in einem PDF-Dokument hinzufügen. Aspose.PDF ist eine leistungsstarke Bibliothek, mit der Sie PDF-Dokumente programmgesteuert erstellen, bearbeiten und konvertieren können. Mit den markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie eine hierarchische Struktur in Ihrem PDF-Dokument erstellen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Visual Studio mit .NET Framework installiert.
2. Die Aspose.PDF-Bibliothek für .NET.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Sie können die Bibliothek von der offiziellen Website von Aspose herunterladen und auf Ihrem Computer installieren.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Importieren Sie in Ihre C#-Codedatei die Namespaces, die für den Zugriff auf die von Aspose.PDF bereitgestellten Klassen und Methoden erforderlich sind:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Schritt 3: Erstellen des PDF-Dokuments und Definieren der strukturierten Elemente

Verwenden Sie den folgenden Code, um ein PDF-Dokument zu erstellen und die strukturierten Elemente zu definieren:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Dieser Code erstellt ein leeres PDF-Dokument und fügt strukturierte Elemente wie Absätze und Bereiche hinzu. Jedes Strukturelement wird mit den von Aspose.PDF bereitgestellten Methoden erstellt.

## Schritt 4: Speichern des PDF-Dokuments

Verwenden Sie den folgenden Code, um das PDF-Dokument zu speichern:

```csharp
document. Save(outFile);
```

Dieser Code speichert das PDF-Dokument mit den strukturierten Elementen in einer angegebenen Datei.

### Beispielquellcode für „Strukturelement zu Element hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Erstellungsdokument und Abrufen getaggter PDF-Inhalte
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Festlegen der Titel- und Natursprache für das Dokument
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Root-Strukturelement (Dokumentstrukturelement) abrufen
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Markiertes PDF-Dokument speichern
document.Save(outFile);
// Überprüfung der PDF/UA-Konformität
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET ein Strukturelement zu einem Element in einem PDF-Dokument hinzufügen. Mit den markierten Inhaltsstrukturfunktionen von Aspose.PDF können Sie eine hierarchische Struktur in Ihrem PDF-Dokument erstellen, die die Verwaltung und Navigation durch Inhalte erleichtert.

### FAQs

#### F: Was ist der Zweck des Hinzufügens eines Strukturelements zu einem Element in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Hinzufügen eines Strukturelements zu einem Element in einem PDF-Dokument mit Aspose.PDF für .NET können Sie eine hierarchische Struktur innerhalb des Dokumentinhalts erstellen. Diese hierarchische Struktur verbessert die Organisation und Navigation des Inhalts und erleichtert die Verwaltung und den Zugriff auf bestimmte Elemente.

#### F: Wie unterstützt die Aspose.PDF-Bibliothek das Hinzufügen von Strukturelementen zu einem PDF-Dokument?

A: Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die Funktionen zum programmgesteuerten Erstellen, Bearbeiten und Konvertieren von PDF-Dokumenten bietet. In diesem Tutorial werden die markierten Inhaltsstrukturfunktionen der Bibliothek genutzt, um Strukturelemente zu erstellen und an den Inhalt des PDF-Dokuments anzuhängen.

#### F: Was sind die Voraussetzungen für das Hinzufügen von Strukturelementen zu einem PDF-Dokument mit Aspose.PDF für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Visual Studio mit dem .NET Framework installiert ist und dass in Ihrem Projekt auf die Aspose.PDF-Bibliothek für .NET verwiesen wird.

#### F: Wie erstellt der bereitgestellte C#-Code Strukturelemente und hängt sie an den Inhalt des PDF-Dokuments an?

A: Der Code zeigt, wie man ein PDF-Dokument erstellt, ein Stammstrukturelement definiert und verschiedene strukturierte Elemente wie Absätze und Bereiche daran anhängt. Jedes strukturierte Element wird mit den von Aspose.PDF bereitgestellten Methoden erstellt, sodass Sie eine hierarchische Struktur aufbauen können.

#### F: Kann ich die Arten von Strukturelementen anpassen, die ich an das PDF-Dokument anhänge?

A: Ja, Sie können die Arten von Strukturelementen anpassen, indem Sie verschiedene Methoden erkunden, die von der Aspose.PDF-Bibliothek bereitgestellt werden. Der Code zeigt Absätze und Abschnitte als Beispiele, Sie können jedoch bei Bedarf auch andere Arten strukturierter Elemente erstellen und anhängen.

#### F: Wie definiere ich die hierarchische Beziehung zwischen den hinzugefügten Strukturelementen?

 A: Die hierarchische Beziehung zwischen Strukturelementen wird durch die Reihenfolge definiert, in der Sie sie an ihre übergeordneten Elemente anhängen. Im Code werden die Eltern-Kind-Beziehungen mithilfe von hergestellt`AppendChild` Methode.

#### F: Welche Vorteile bietet die Erstellung einer hierarchischen Struktur in einem PDF-Dokument?

A: Das Erstellen einer hierarchischen Struktur in einem PDF-Dokument verbessert dessen Zugänglichkeit, Navigation und Organisation. Es ermöglicht unterstützenden Technologien, den Inhalt des Dokuments besser zu interpretieren und zu vermitteln, wodurch es für Menschen mit Behinderungen benutzerfreundlicher wird.

#### F: Wie kann ich die PDF/UA-Konformität überprüfen, nachdem ich Strukturelemente hinzugefügt habe?

 A: Der im Tutorial bereitgestellte Code zeigt, wie die PDF/UA-Konformität mithilfe von validiert wird`Validate` Methode. Durch die Validierung des Dokuments anhand des PDF/UA-Standards können Sie sicherstellen, dass die hinzugefügten Strukturelemente den Barrierefreiheitsrichtlinien entsprechen.

#### F: Kann ich mit diesem Ansatz Strukturelemente zu einem vorhandenen PDF-Dokument hinzufügen?

A: Ja, Sie können den bereitgestellten Ansatz ändern, um Strukturelemente zu einem vorhandenen PDF-Dokument hinzuzufügen. Anstatt ein neues Dokument zu erstellen, würden Sie das vorhandene Dokument mit Aspose.PDF laden und dann ähnliche Schritte zum Anhängen von Strukturelementen ausführen.