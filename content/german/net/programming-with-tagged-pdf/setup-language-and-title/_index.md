---
title: Sprache und Titel einrichten
linktitle: Sprache und Titel einrichten
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konfigurieren der Sprache und des Titels eines PDF-Dokuments mit Aspose.PDF für .NET. Erstellen Sie personalisierte mehrsprachige Dokumente.
type: docs
weight: 140
url: /de/net/programming-with-tagged-pdf/setup-language-and-title/
---
## Einführung

Das Erstellen getaggter PDFs ist eine wichtige Aktivität, um Zugänglichkeit zu gewährleisten und ein strukturiertes Format für Dokumente bereitzustellen. Da wir uns in Richtung einer integrativeren digitalen Umgebung bewegen, wird es immer wichtiger zu verstehen, wie getaggte Dokumente erstellt werden. Diese umfassende Anleitung führt Sie durch den Prozess der Einrichtung von Sprache und Titeln in getaggten PDFs mit Aspose.PDF für .NET. Wir unterteilen es in leicht verständliche Schritte, sodass Sie sich am Ende wie ein Profi fühlen, auch wenn Sie Anfänger sind. 

## Voraussetzungen

Bevor wir in die Welt der getaggten PDFs eintauchen, sammeln wir alles, was Sie brauchen. Folgendes sollten Sie bereithalten:

- Grundlegende Kenntnisse in .NET: Sie müssen zwar kein außergewöhnlicher Programmierer sein, aber Kenntnisse in den Konzepten von .NET erleichtern Ihnen den Einstieg.
-  Aspose.PDF für .NET installiert: Stellen Sie sicher, dass Sie die Bibliothek installiert haben. Sie können sie entweder zur Evaluierung herunterladen oder eine Lizenz erwerben. Überprüfen Sie die[Download-Seite hier](https://releases.aspose.com/pdf/net/).
- Visual Studio: Hier schreiben und testen Sie Ihren Code. Wenn Sie es nicht haben, laden Sie es von der Microsoft-Website herunter.
- C#-Sprachkenntnisse: Dieses Handbuch ist in C# geschrieben. Ein wenig Erfahrung mit C# wird Ihnen sicherlich dabei helfen, die Codierungsteile mühelos zu bewältigen.

## Pakete importieren

Nachdem Sie die Voraussetzungen eingerichtet haben, ist es an der Zeit, die erforderlichen Pakete zu importieren. Sie können dies tun, indem Sie oben in Ihrer C#-Datei die folgende using-Direktive hinzufügen:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Über diese Namespaces können Sie auf die Komponenten zugreifen, die Sie zum Erstellen und Bearbeiten von PDFs mit getaggtem Inhalt benötigen. Sie fragen sich vielleicht: „Warum Pakete importieren?“ Es ist, als ob Sie vor dem Bauen einen Werkzeugkasten vorbereiten – Sie müssen die richtigen Werkzeuge zur Hand haben.

## Schritt 1: Initialisieren Sie das Dokument

Der erste Schritt auf unserer Reise ist die Erstellung eines neuen Dokumentobjekts. Sie können sich das so vorstellen, als würden wir das Fundament für ein Haus legen – alles andere wird darauf gebaut.

```csharp
Document document = new Document();
```

Hier erstellen wir ein neues PDF-Dokument. Hier werden alle Ihre Inhalte gespeichert. 

## Schritt 2: Dokumentverzeichnis festlegen

Als Nächstes müssen Sie festlegen, wo Ihre Dokumente gespeichert werden. Sie benötigen einen Ort, an dem Sie Ihre neu erstellte PDF-Datei speichern können.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad, in dem Sie die PDF-Datei speichern möchten. Das ist vergleichbar mit der Parkplatzsuche für Ihr neues Auto.

## Schritt 3: Markierten Inhalt abrufen

Greifen wir nun auf den getaggten Inhalt unseres Dokuments zu. Getaggter Inhalt dient als Grundlage für die Erstellung barrierefreier PDFs. 

```csharp
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

Auf diese Weise ermöglichen Sie die Strukturierung Ihrer PDF-Datei, ähnlich wie Sie vor dem eigentlichen Schreiben eine Gliederung für ein Buch erstellen.

## Schritt 4: Titel und Sprache festlegen

Wenn Ihr getaggter Inhalt fertig ist, ist es an der Zeit, den Titel des Dokuments und die Hauptsprache anzugeben. 

```csharp
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");
```

Betrachten Sie diesen Schritt als das Verleihen Ihres Dokuments einer Identität. Der Titel stellt die Essenz dessen dar, worum es in dem Dokument geht, während die Sprache den Lesern den primären sprachlichen Kontext vermittelt.

## Schritt 5: Header-Element erstellen

Eine strukturierte PDF-Datei enthält häufig Überschriften, die dem Leser als Orientierung dienen. Lassen Sie uns ein Überschriftenelement erstellen.

```csharp
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);
```

Hier haben wir eine Überschrift (H1) mit Text erstellt. Das ist wie ein Wegweiser, der den Lesern zeigt, was sie als Nächstes lesen werden. 

## Schritt 6: Absätze in mehreren Sprachen hinzufügen

Hier beginnt der spaßige Teil – das Hinzufügen von Inhalten in verschiedenen Sprachen. Wir werden ein paar Absätze hinzufügen, um verschiedene Sprachen darzustellen.

### Englischen Absatz hinzufügen

Beginnen wir mit Englisch:

```csharp
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);
```

Diese Zeile fügt eine freundliche Begrüßung auf Englisch hinzu. Es ist, als würden Sie Ihre Leser in ihrer bevorzugten Sprache begrüßen.

### Deutscher Absatz hinzufügen

Als nächstes fügen wir einen deutschen Absatz hinzu:

```csharp
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);
```

Damit erreichen Sie Ihr deutschsprachiges Publikum und erweitern die Zugänglichkeit Ihres Dokuments.

### Französischen Absatz hinzufügen

Gleiches gilt für Französisch:

```csharp
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);
```

Auch in diesem Fall setzen wir auf Vielfalt, indem wir französische Texte einbinden. 

### Spanischen Absatz hinzufügen

Zum Schluss noch etwas Spanisch:

```csharp
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

Mit dieser Ergänzung zeigen Sie, dass Ihr Dokument mehrere Sprachen spricht und fördern so die Inklusivität.

## Schritt 7: Speichern Sie das getaggte PDF-Dokument

Nachdem Sie Ihr Dokument nun in mehreren Sprachen erstellt haben, ist es Zeit, es zu speichern. 

```csharp
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

Und so ist Ihre Kreation fertig und wird aufbewahrt! Betrachten Sie dies als das Verschließen des Umschlags vor dem Versenden Ihres Briefs.

## Abschluss

Beim Erstellen getaggter PDFs mit Aspose.PDF für .NET geht es nicht nur ums Codieren; es geht darum, Ihre Dokumente für alle Leser zugänglich und benutzerfreundlich zu machen. Sie haben gelernt, wie Sie Titel und Sprachen festlegen und sogar mehrere mehrsprachige Absätze zu Ihrem PDF hinzufügen. Mit diesen Fähigkeiten sind Sie auf dem besten Weg, inklusive digitale Inhalte zu erstellen. 


## Häufig gestellte Fragen

### Was ist ein getaggtes PDF?
Ein getaggtes PDF ist ein PDF-Dokumenttyp, der zusätzliche Informationen enthält, die das strukturierte Lesen des Inhalts ermöglichen. Dies ist insbesondere für unterstützende Technologien von Vorteil.

### Wie hilft Aspose.PDF für .NET beim Erstellen getaggter PDFs?
Aspose.PDF für .NET bietet verschiedene Klassen und Methoden, mit denen Sie problemlos PDFs erstellen und bearbeiten können, einschließlich des Hinzufügens von getaggten Inhalten für die Barrierefreiheit.

### Kann ich ein getaggtes PDF in mehreren Sprachen erstellen?
Ja! Aspose.PDF unterstützt mehrere Sprachen, sodass Sie Inhalte in verschiedenen Sprachen in dasselbe PDF-Dokument einfügen können.

### Benötige ich eine Lizenz, um Aspose.PDF zu verwenden?
Sie können es zwar kostenlos ausprobieren, für den produktiven Einsatz ist jedoch eine Lizenz erforderlich. Besuchen Sie die[Kaufseite](https://purchase.aspose.com/buy) für weitere Informationen.

### Wo finde ich weitere Informationen zu Aspose.PDF?
 Umfassende Dokumentation und Support zu Aspose.PDF finden Sie hier[Hier](https://reference.aspose.com/pdf/net/).