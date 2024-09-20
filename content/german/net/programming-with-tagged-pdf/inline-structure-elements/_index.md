---
title: Inline-Strukturelemente
linktitle: Inline-Strukturelemente
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung von Online-Strukturelementen mit Aspose.PDF für .NET. Organisieren Sie Ihre PDFs mit Überschriften und Absätzen.
type: docs
weight: 110
url: /de/net/programming-with-tagged-pdf/inline-structure-elements/
---
## Einführung

Das Erstellen zugänglicher und gut strukturierter Dokumente ist in der heutigen digitalen Landschaft von entscheidender Bedeutung. Wenn Sie schon einmal durch eine PDF-Datei gescrollt sind und sich dabei in einem Meer von Text verloren haben, wissen Sie, wie wichtig eine gute Organisation ist. Das Markieren von Elementen in Ihrer PDF-Datei kann die Zugänglichkeit verbessern und es Bildschirmlesegeräten erleichtern, Inhalte zu interpretieren. In diesem Handbuch befassen wir uns mit der Verwendung von Aspose.PDF für .NET zum Erstellen getaggter PDF-Dokumente und stellen sicher, dass Ihre Arbeit modernen Standards bei der Dokumentstrukturierung entspricht.

## Voraussetzungen

Bevor wir in die Aktion einsteigen, stellen wir sicher, dass Sie alles haben, was Sie zum Mitmachen brauchen:

1. Grundkenntnisse in C#: Vertrautheit mit der C#-Programmierung und den Grundlagen des .NET-Frameworks ist unbedingt erforderlich.
2. Visual Studio installiert: Sie benötigen eine IDE wie Visual Studio, um Ihren Code zu schreiben und auszuführen.
3.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie Aspose.PDF für .NET herunterladen und installieren. Sie können es von der[Downloadlink](https://releases.aspose.com/pdf/net/).
4. Eine temporäre Lizenz: Dies ist optional, aber wenn Sie alle Funktionen ohne Einschränkungen testen möchten, sollten Sie eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/).

Sobald diese Voraussetzungen erfüllt sind, können Sie Ihr erstes getaggtes PDF-Dokument erstellen!

## Pakete importieren

Lassen Sie uns zunächst die erforderlichen Pakete importieren. So kann Ihr Projekt die Funktionen der Aspose.PDF-Bibliothek nutzen.

1. Öffnen Sie Ihr Visual Studio-Projekt.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek hinzu. Wenn Sie sie noch nicht hinzugefügt haben, können Sie sie mit dem NuGet Package Manager installieren.
3. Fügen Sie am Anfang Ihrer C#-Datei die folgenden Namespaces ein:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Wenn diese Importe vorhanden sind, sind Sie für den Erfolg gerüstet.

## Code-Aufschlüsselung: Schritt-für-Schritt-Anleitung zum Erstellen eines getaggten PDF

Nachdem wir nun alles eingerichtet haben, wollen wir den Code Schritt für Schritt aufschlüsseln. Wir erstellen ein getaggtes PDF mit strukturierten Elementen wie Überschriften und Absätzen, um eine bessere Zugänglichkeit zu ermöglichen.

### Schritt 1: Dokumentverzeichnis festlegen

Legen Sie zunächst den Pfad fest, in dem Ihr Dokument gespeichert wird. Es ist eine gute Idee, eine organisierte Dateistruktur beizubehalten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ersetzen Sie es durch Ihren tatsächlichen Pfad.
```

### Schritt 2: Erstellen Sie eine PDF-Dokumentinstanz

 Erstellen Sie als nächstes eine Instanz des`Document` Klasse, die als Container für Ihren PDF-Inhalt dient.

```csharp
Document document = new Document();
```

### Schritt 3: Auf markierte Inhalte zugreifen

Greifen Sie nun auf den getaggten Inhalt des Dokuments zu. Hier geschieht die Magie – indem wir den Inhalt taggen, verbessern wir seine Zugänglichkeit.

```csharp
ITaggedContent taggedContent = document.TaggedContent;    
```

### Schritt 4: Titel und Sprache festlegen

Das Festlegen eines Titels und einer Sprache für Ihr PDF-Dokument ist sowohl für Benutzer als auch für Bildschirmleseprogramme wichtig. Dadurch wird Ihr Dokument informativer und zugänglicher.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

### Schritt 5: Holen Sie sich das Stammstrukturelement

Beginnen wir mit dem Hinzufügen von Elementen zu Ihrem Dokument. Holen Sie sich zunächst das Stammstrukturelement des getaggten Inhalts, das als Grundlage für den Aufbau der Struktur Ihres Dokuments dient.

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

### Schritt 6: Header-Elemente erstellen

Jetzt ist es an der Zeit, Kopfzeilenelemente zu erstellen. Dies hilft dabei, den Inhalt in einer Hierarchie zu organisieren. Wir werden sechs Kopfzeilenebenen erstellen.

```csharp
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
```

### Schritt 7: Header an das Stammelement anhängen

Nachdem Sie Header-Elemente erstellt haben, hängen Sie diese an das Stammelement an. Dadurch wird die Strukturhierarchie des Dokuments erstellt.

```csharp
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
```

### Schritt 8: Fügen Sie jeder Überschrift Text hinzu

Fügen wir nun jeder Überschrift etwas Text hinzu. Dies ist ein einfacher Vorgang, aber wichtig, um Ihr Dokument nützlich zu machen. 

```csharp
// H1
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);

// Wiederholen Sie dies für H2 – H6 wie oben gezeigt
```

### Schritt 9: Erstellen Sie ein Absatzelement

Als Nächstes fügen wir ein Absatzelement hinzu. Dies dient als Hauptinhaltsbereich Ihrer PDF-Datei. 

```csharp
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
```

### Schritt 10: Fügen Sie dem Absatz Text hinzu

Jetzt, da wir unser Absatzelement haben, ist es an der Zeit, es mit Text zu füllen. Sie können mehrere Bereiche hinzufügen, um Ihren Inhalt zusammenzustellen.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
// Fügen Sie bei Bedarf weitere Bereiche hinzu
```

### Schritt 11: Speichern Sie das getaggte PDF-Dokument

Nachdem Sie alle Inhalte hinzugefügt haben, müssen Sie Ihr Dokument abschließend speichern. Fassen wir es zusammen!

```csharp
document.Save(dataDir + "InlineStructureElements.pdf");
```

Und voilà! Sie haben jetzt ein getaggtes PDF-Dokument, das strukturiert und zugänglich ist.

## Abschluss

Das Erstellen getaggter PDF-Dokumente mag entmutigend erscheinen, aber mit Aspose.PDF für .NET ist es ein Kinderspiel! Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, beherrschen Sie die Grundlagen der Dokumentstrukturierung. Denken Sie daran, dass das richtige Taggen Ihrer PDF-Datei deren Zugänglichkeit verbessert und sicherstellt, dass Ihre wertvollen Inhalte ein breiteres Publikum erreichen. Machen Sie Ihre PDF-Dateien also nicht nur hübsch, sondern auch benutzerfreundlich!

## Häufig gestellte Fragen

### Was ist ein getaggtes PDF?
Bei einem getaggten PDF handelt es sich um ein PDF, das Informationen zur Struktur des Dokuments enthält und es dadurch für Benutzer mit Behinderungen leichter zugänglich macht.

### Warum ist Tagging in PDFs wichtig?
Durch Tagging wird die Zugänglichkeit verbessert, da Bildschirmleseprogramme das Dokument klar interpretieren können und dadurch Benutzern mit Behinderungen ein besseres Erlebnis geboten wird.

### Kann ich Aspose.PDF kostenlos nutzen?
 Ja, Sie können Aspose.PDF für .NET über eine[Kostenlose Testversion](https://releases.aspose.com/).

### Wo erhalte ich Support für Aspose.PDF?
 Support erhalten Sie über das[Aspose-Supportforum](https://forum.aspose.com/c/pdf/10).

### Wie kann ich die Aspose.PDF-Lizenz für .NET erwerben?
 Sie können eine Lizenz direkt erwerben bei der[Kaufseite](https://purchase.aspose.com/buy).