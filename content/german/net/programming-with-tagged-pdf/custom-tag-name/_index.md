---
title: Benutzerdefinierter Tag-Name
linktitle: Benutzerdefinierter Tag-Name
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zur Verwendung eines benutzerdefinierten Tag-Namens mit Aspose.PDF für .NET. Verbessern Sie die Struktur Ihrer PDFs mit benutzerdefinierten Tags.
type: docs
weight: 90
url: /de/net/programming-with-tagged-pdf/custom-tag-name/
---
## Einführung

Im heutigen digitalen Zeitalter sind PDFs allgegenwärtig. Von Berichten bis zu Handbüchern dienen sie einer Vielzahl von Zwecken in verschiedenen Branchen. Es ist jedoch von entscheidender Bedeutung, sicherzustellen, dass diese Dokumente für alle zugänglich sind, auch für Menschen mit Behinderungen. Hier kommen getaggte PDFs ins Spiel. Sie erleichtern Bildschirmleseprogrammen und anderen unterstützenden Technologien die effektive Interpretation von Dokumentinhalten.

## Voraussetzungen

Bevor wir mit dem Programmieren beginnen, müssen Sie sicherstellen, dass Sie alles bereit haben. Folgendes benötigen Sie:

1. Visual Studio – Jede aktuelle Version ist geeignet, für optimale Funktionalität ist es jedoch am besten, die neueste Version zu verwenden.
2.  Aspose.PDF für .NET - Sie können die neueste Version ganz einfach herunterladen von der[Downloadlink](https://releases.aspose.com/pdf/net/).
3. Grundkenntnisse in C# – Kenntnisse der Grundlagen der C#-Programmierung sind bei der Implementierung des Codes von Vorteil.

## Pakete importieren

Sobald Sie Ihre Umgebung eingerichtet haben, besteht der nächste Schritt darin, die erforderlichen Pakete zur Verwendung von Aspose.PDF zu importieren. Sie können dies tun, indem Sie Ihrem Projekt die Aspose.PDF-Bibliothek hinzufügen.

### Installieren Sie Aspose.PDF über NuGet

1. Öffnen Sie Ihr Visual Studio-Projekt: Wenn Sie noch kein Projekt erstellt haben, erstellen Sie ein neues.
2. Greifen Sie auf den NuGet-Paket-Manager zu: Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Ihr Projekt und wählen Sie „NuGet-Pakete verwalten“ aus.
3. Suchen Sie nach Aspose.PDF: Geben Sie „Aspose.PDF“ in die Suchleiste ein.
4. Installieren Sie das Paket: Klicken Sie auf „Installieren“, um das Paket zu Ihrem Projekt hinzuzufügen. Nach der Installation können Sie loslegen!

### Using-Direktive hinzufügen

Um die Aspose-Funktionalität in Ihrem Code zu nutzen, müssen Sie die erforderliche using-Direktive oben in Ihrer Datei hinzufügen:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Wenn Sie diese Schritte abgeschlossen haben, können Sie mit der Erstellung Ihres getaggten PDFs beginnen!

Nachdem Sie nun alles eingerichtet haben, können wir uns an die Hauptaufgabe machen: das Erstellen eines getaggten PDF-Dokuments. Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Verwendung von Aspose.PDF für .NET.

## Schritt 1: Definieren Sie das Dokumentverzeichnis

Zunächst müssen Sie den Pfad angeben, in dem Ihr PDF gespeichert wird. Hier definieren Sie Ihr Datenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Erklärung: Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Pfad, in dem Sie die PDF-Datei speichern möchten. Es ist wichtig, Schreibberechtigung für dieses Verzeichnis zu haben, um Laufzeitausnahmen zu vermeiden.

## Schritt 2: Ein neues PDF-Dokument erstellen

 Als nächstes erstellen wir eine Instanz des`Document` Klasse.

```csharp
Document document = new Document();
```

Erklärung: Diese Zeile initialisiert ein neues PDF-Dokument. Stellen Sie sich das so vor, als würden Sie eine leere Leinwand erstellen, auf die Sie den Inhalt Ihres PDFs malen.

## Schritt 3: Markierten Inhalt erstellen

Jetzt ist es an der Zeit, zum Kern des Taggings zu kommen. Wir werden den getaggten Inhalt des Dokuments abrufen.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Erläuterung: Die`TaggedContent` -Objekt ermöglicht es uns, die logische Struktur und Zugänglichkeit des PDF zu manipulieren, indem wir den Inhalt hierarchisch organisieren.

## Schritt 4: Titel und Sprache festlegen

Als nächstes können Sie den Titel und das Sprachattribut des Dokuments festlegen. Dies hilft Screenreadern, das Dokument richtig zu verarbeiten.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Erklärung: Hier informieren wir jeden, der dieses PDF liest, über seinen Titel und die Sprache, was das Verständnis erleichtert, insbesondere bei Eingabehilfen.

## Schritt 5: Erstellen der logischen Strukturelemente

Jetzt ist es an der Zeit, strukturierte Elemente in Ihrem PDF zu erstellen.

```csharp
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
```

 Erklärung: Dieser Schritt führt ein Abschnittselement ein, in dem Sie Inhalte hinzufügen können. Das`RootElement` ist Ihre Heimatbasis.

## Schritt 6: Absatzelemente erstellen

Nun erstellen wir verschiedene Absatzelemente und legen deren Textinhalte fest.

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
```

Erklärung: Jeder Absatz ist mit einem Satz in einer Geschichte vergleichbar, er beschreibt die Szene und verleiht Ihrem Dokument Bedeutung.

## Schritt 7: Absätzen Tags zuweisen

Für die Barrierefreiheit Ihrer PDF-Datei ist es wichtig, jeden Absatz entsprechend zu kennzeichnen.

```csharp
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
```

Erklärung: Durch die Kennzeichnung mit Tags ermöglichen wir unterstützenden Technologien, die Struktur des Inhalts zu verstehen – es ist, als würden wir ihnen eine Straßenkarte zur Navigation durch das Gebiet geben.

## Schritt 8: Absätze an den Abschnitt anhängen

Wir werden diese Absätze nun an den zuvor erstellten Abschnitt anhängen.

```csharp
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
```

Erklärung: Diese Aktion organisiert die Absätze innerhalb des Abschnitts und sorgt dafür, dass der Ablauf logisch und leicht nachvollziehbar wird.

## Schritt 9: Span-Elemente erstellen

Genau wie Absätze fügen Bereiche unserem Textinhalt detaillierte Details hinzu.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
```

Erklärung: Spannen sind wie die Feinabstimmung von Details; sie verleihen dem, was Sie in jedem Absatz vermitteln möchten, Spezifität.

## Schritt 10: Span-Elementen Tags zuweisen

Genau wie bei den Absätzen sollten wir unsere Span-Elemente mit Tags versehen, um das Verständnis zu erleichtern.

```csharp
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
```

Erklärung: Durch die ordnungsgemäße Kennzeichnung von Bereichen wird sichergestellt, dass alle Nuancen genau dargestellt werden, sodass für jeden, der darauf stößt, ein aussagekräftiges Dokument entsteht.

## Schritt 11: Abschnitte an Absätze anhängen

Hängen wir nun unsere Span-Elemente an die entsprechenden Absätze an.

```csharp
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Erklärung: Diese Integration verbessert Ihre Absätze durch die Einblendung zusätzlicher Informationen, genau wie Sie einem Buch Fußnoten zum tieferen Verständnis hinzufügen.

## Schritt 12: Speichern Sie das getaggte PDF-Dokument

Endlich ist es Zeit, Ihr Meisterwerk zu speichern!

```csharp
document.Save(dataDir + "CustomTag.pdf");
```

Erklärung: Mit dieser Zeile wird Ihr getaggtes PDF im angegebenen Verzeichnis gespeichert. Damit ist die Erstellung Ihres getaggten PDF-Dokuments abgeschlossen!

## Abschluss

Beim Erstellen getaggter PDF-Dokumente mit Aspose.PDF für .NET geht es nicht nur darum, Inhalte hinzuzufügen; es geht darum, ein barrierefreies Erlebnis für alle Benutzer zu schaffen. Mit nur wenigen Schritten können Sie sicherstellen, dass Ihre Dokumente jeden ansprechen, Barrieren abbauen und das Verständnis verbessern. 

## Häufig gestellte Fragen

### Was ist ein getaggtes PDF?  
Ein getaggtes PDF enthält zusätzliche Metadaten, die die Struktur und Zugänglichkeit des Dokumentinhalts beschreiben und so die Interpretation durch unterstützende Technologien erleichtern.

### Warum brauche ich Aspose.PDF für .NET?  
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente programmgesteuert mit umfangreichen Funktionen zu erstellen, zu ändern und zu bearbeiten.

### Wie kann ich eine Testversion von Aspose.PDF erhalten?  
 Sie können eine kostenlose Testversion von Aspose.PDF erhalten, indem Sie[dieser Link](https://releases.aspose.com/).

### Kann ich Support für Aspose.PDF erhalten?  
 Ja, Sie können Support über erreichen[das Aspose-Forum](https://forum.aspose.com/c/pdf/10).

### Wo finde ich eine ausführliche Aspose.PDF-Dokumentation?  
 Die vollständige Dokumentation finden Sie[Hier](https://reference.aspose.com/pdf/net/).