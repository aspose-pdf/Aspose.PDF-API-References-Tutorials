---
title: Strukturelement zu Element hinzufügen
linktitle: Strukturelement zu Element hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in diesem umfassenden Schritt-für-Schritt-Tutorial, wie Sie mit Aspose.PDF für .NET Barrierefreiheitsstrukturelemente in PDFs einfügen.
type: docs
weight: 20
url: /de/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## Einführung

In der heutigen digitalen Welt ist Zugänglichkeit von entscheidender Bedeutung. Jeder sollte den gleichen Zugang zu Informationen haben, und es ist entscheidend, diese in einem Format bereitzustellen, in dem alle Personen problemlos navigieren können. In diesem Tutorial erfahren Sie, wie Sie die Zugänglichkeit von PDFs verbessern können, indem Sie mithilfe von Aspose.PDF für .NET Strukturelemente hinzufügen. Diese leistungsstarke Bibliothek ermöglicht Entwicklern die nahtlose Arbeit mit PDF-Dokumenten und ermöglicht ihnen die Erstellung getaggter PDFs, die den Zugänglichkeitsstandards entsprechen.

## Voraussetzungen

Bevor wir unsere Reise in die Welt der PDF-Strukturelemente beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1.  Visual Studio: Dies ist Ihre IDE, in der Sie Ihren C#-Code schreiben und ausführen. Sie können es herunterladen von[Visual Studio](https://visualstudio.microsoft.com/) falls Sie das nicht bereits getan haben.
2.  Aspose.PDF für .NET-Bibliothek: Sie benötigen die Bibliothek, um PDFs zu bearbeiten. Laden Sie die neueste Version von der[Aspose-Website](https://releases.aspose.com/pdf/net/). Diese Bibliothek ist für unser Projekt von zentraler Bedeutung.
3. Grundkenntnisse in C#: Kenntnisse der C#-Syntax und der objektorientierten Programmierung sind von Vorteil. Wenn Sie problemlos ein paar Zeilen in C# schreiben können, sind Sie startklar!
4. Ein PDF-Dokumentverzeichnis: Erstellen Sie auf Ihrem System ein Verzeichnis, in dem Sie die Eingabe- und Ausgabe-PDF-Dateien für dieses Tutorial speichern.

Nachdem wir nun unsere Werkzeuge und Kenntnisse beisammen haben, können wir mit den erforderlichen Paketen loslegen!

## Pakete importieren

Als Erstes importieren wir die erforderlichen Namespaces. Stellen Sie sicher, dass sich am Anfang Ihrer C#-Datei Folgendes befindet:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Über diese Namespaces haben Sie Zugriff auf die Klassen und Methoden, die Sie zum Arbeiten mit Ihren PDF-Dokumenten und zum Erstellen getaggter Inhalte benötigen. Kommen wir nun zum Kern der Sache und beginnen mit dem Programmieren!

## Schritt 1: Richten Sie Ihr Dokumentverzeichnis ein

Bevor wir mit der Codierung beginnen, müssen wir festlegen, wo wir unsere Dateien speichern. Dies ist entscheidend, damit unser Skript reibungslos ausgeführt werden kann.

```csharp
// Definieren Sie den Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem Sie Ihre PDF-Dateien speichern möchten. Dies könnte etwa so aussehen:`C:\\PDFs\\`.

## Schritt 2: Ein neues PDF-Dokument erstellen

Nachdem wir nun unser Verzeichnis festgelegt haben, erstellen wir ein PDF-Dokument, in das wir unsere Strukturelemente einfügen.

```csharp
Document document = new Document();
```

 Diese Zeile initialisiert eine neue Instanz des`Document` Klasse, sodass wir mit der Arbeit an unseren PDF-Inhalten beginnen können.

## Schritt 3: Auf getaggte Inhalte zugreifen und diese einrichten

Sobald Ihr Dokument fertig ist, ist es an der Zeit, getaggte Inhalte einzurichten, die für die Barrierefreiheit unerlässlich sind.

### Markierten Inhalt initialisieren

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Über diese Zeile erhalten Sie Zugriff auf den getaggten Inhalt Ihrer PDF-Datei. Dieser ist für Screenreader erforderlich, damit diese Ihr Dokument richtig interpretieren können.

### Dokumentmetadaten festlegen

Sie möchten Ihrem Dokument einen passenden Titel geben und die Sprache festlegen.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

Dadurch werden die Metadaten des Dokuments erweitert und seine Zugänglichkeit verbessert.

## Schritt 4: Strukturelemente erstellen und anfügen

Lassen Sie uns etwas Struktur hinzufügen! Dazu gehört das Erstellen von Absätzen und Span-Elementen, um ein richtig formatiertes und getaggtes Dokument zu erstellen.

### Stammstrukturelement erstellen

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Jetzt erstellen wir unseren ersten Satz Absätze und Spannelemente.

### Erstes Absatzelement erstellen

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Hier initialisieren wir ein neues Absatzelement und hängen es an das Stammstrukturelement an. Dies ist der Ausgangspunkt Ihres Inhalts!

### Hinzufügen von Span-Elementen zu Absätzen

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 Der`span` Elemente sind wie Miniabsätze innerhalb unseres größeren Absatzes. Sie ermöglichen eine feinere Kontrolle über die Textformatierung.

### Kombinieren Sie alles

Lassen Sie uns nun den vollständigen Absatz mit allen Elementen zusammen konstruieren:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Wiederholen Sie dies für weitere Absätze.

Sie wiederholen diesen Vorgang für weitere Absätze:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Erschaffe einfach weiter`ParagraphElement` s und`SpanElement` s, und hängen Sie sie an die`rootElement` auf die gleiche Weise wie oben gezeigt für`p1`.

## Schritt 5: Speichern Sie Ihr Dokument

Wenn alle Strukturelemente vorhanden sind, ist es Zeit, Ihr PDF-Dokument zu speichern.

### Geben Sie den Ausgabedateipfad an

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Speichern des Dokuments

```csharp
document.Save(outFile);
```

Hier geschieht die Magie! Ihr Dokument wird im angegebenen Ausgabedateipfad gespeichert.

## Schritt 6: PDF/UA-Konformität validieren

Im letzten Schritt prüfen Sie, ob Ihr Dokument den PDF/UA-Standards für Barrierefreiheit entspricht.

Um die Konformität zu prüfen, verwenden Sie den folgenden Code:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Dadurch wird ausgegeben, ob Ihr Dokument den PDF/UA-Standards entspricht, was für die Barrierefreiheit von entscheidender Bedeutung ist.

## Abschluss

Und da haben Sie es! Sie haben gerade gelernt, wie Sie mit Aspose.PDF für .NET Strukturelemente in ein PDF-Dokument einfügen. Indem Sie diese Schritte befolgen, können Sie jedes PDF in ein zugängliches, standardkonformes Format umwandeln und so sicherstellen, dass jeder den gleichen Zugriff auf Informationen hat. 

## Häufig gestellte Fragen

### Was ist Aspose.PDF für .NET?
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert zu erstellen, zu bearbeiten und zu konvertieren.

### Wie überprüfe ich, ob mein PDF barrierefrei ist?
Sie können Ihr PDF mithilfe der Aspose.PDF-Bibliothek anhand von PDF/UA-Standards validieren, um sicherzustellen, dass es den Richtlinien zur Barrierefreiheit entspricht.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen kostenlos testen können. Sie können sie herunterladen[Hier](https://releases.aspose.com/).

### Wo finde ich die Dokumentation für Aspose.PDF?
Eine umfassende Dokumentation zu Aspose.PDF finden Sie hier[Hier](https://reference.aspose.com/pdf/net/).

### Wie erwerbe ich eine Lizenz für Aspose.PDF?
 Sie können eine Lizenz direkt von der Aspose-Website kaufen[Hier](https://purchase.aspose.com/buy).