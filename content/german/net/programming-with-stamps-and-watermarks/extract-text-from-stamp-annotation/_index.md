---
title: Text aus Stempelanmerkung extrahieren
linktitle: Text aus Stempelanmerkung extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach Text aus einer Stempelanmerkung in Ihren PDF-Dokumenten extrahieren.
type: docs
weight: 80
url: /de/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in einem PDF-Dokument extrahieren. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode den Text aus einer bestimmten Stempelanmerkung auf einer bestimmten Seite des PDF-Dokuments extrahieren.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. So geht's:

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "test.pdf");
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Text aus Stempelanmerkung extrahieren

Nachdem Sie das PDF-Dokument geladen haben, können Sie den Text aus der jeweiligen Stempelanmerkung extrahieren. So geht's:

```csharp
// Pufferanmerkung abrufen
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Erstellen Sie einen Textabsorber
TextAbsorber ta = new TextAbsorber();

// Besuchen Sie das Erscheinungsbild der Anmerkung
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Den extrahierten Text anzeigen
Console.WriteLine(ta.Text);
```

Der obige Code ruft die Stempelanmerkung von der angegebenen Seite des PDF-Dokuments ab und verwendet dann einen Textabsorber, um den Text aus dem Erscheinungsbild der Anmerkung zu extrahieren. Der extrahierte Text wird dann in der Ausgabe angezeigt.

### Beispielquellcode zum Extrahieren von Text aus Stempelanmerkungen mit Aspose.PDF für .NET 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in einem PDF-Dokument extrahieren. Sie können diese Methode jetzt verwenden, um Text aus anderen Anmerkungen in Ihren PDF-Dokumenten zu extrahieren.

### FAQs zum Extrahieren von Text aus Stempelanmerkungen

#### F: Was ist eine Stempelanmerkung in einem PDF-Dokument und warum muss ich Text daraus extrahieren?

A: Eine Stempelanmerkung in einem PDF-Dokument ist ein grafisches Element, das verwendet werden kann, um zusätzliche Informationen bereitzustellen, z. B. ein Wasserzeichen oder ein Stempel. Das Extrahieren von Text aus einer Stempelanmerkung ist nützlich, wenn Sie textbasierten Inhalt aus diesen Anmerkungen abrufen möchten, der Notizen, Beschriftungen oder andere Textinformationen enthalten kann.

#### F: Wie extrahiert der bereitgestellte C#-Quellcode Text aus einer Stempelanmerkung?

 A: Der bereitgestellte Quellcode zeigt, wie man Text aus einer bestimmten Stempelanmerkung auf einer bestimmten Seite eines PDF-Dokuments extrahiert. Er verwendet die Aspose.PDF-Bibliothek, um die Stempelanmerkung abzurufen, und besucht ihr Erscheinungsbild mithilfe eines`TextAbsorber`und zeigt dann den extrahierten Text in der Ausgabe an.

#### F: Kann ich mit einem ähnlichen Ansatz Text aus verschiedenen Arten von Anmerkungen extrahieren?

A: Ja, Sie können einen ähnlichen Ansatz verwenden, um Text aus anderen Arten von Anmerkungen zu extrahieren, z. B. Textanmerkungen oder Popup-Anmerkungen. Sie müssen den Code ändern, um den spezifischen Anmerkungstyp anzusprechen, aus dem Sie Text extrahieren möchten.

####  F: Was ist der Zweck der`TextAbsorber` class in the code?

 A: Die`TextAbsorber` Die Klasse wird verwendet, um Text aus verschiedenen Teilen eines PDF-Dokuments zu extrahieren, einschließlich Stempelanmerkungen. Sie „absorbiert“ oder erfasst den Textinhalt, der im angegebenen Bereich oder Element des PDF gefunden wird.

#### F: Wie identifiziere ich die spezifische Stempelanmerkung, aus der ich Text extrahieren möchte?

 A: Im bereitgestellten Code wird die Stempelanmerkung durch den Zugriff auf die`Annotations` Sammlung einer bestimmten Seite und Verwendung des Index zum Abrufen der gewünschten Annotation. Sie können den Index anpassen oder andere Kriterien verwenden, um die Zielannotation zu identifizieren.

#### F: Kann ich Text aus mehreren Stempelanmerkungen auf derselben Seite extrahieren?

 A: Ja, Sie können den Code so ändern, dass er durch die`Annotations`Sammlung einer Seite, Filtern Sie Stempelanmerkungen heraus und extrahieren Sie aus jeder davon Text.

#### F: Was ist, wenn die Stempelanmerkung keinen Textinhalt hat? Funktioniert der Code trotzdem?

A: Der Code funktioniert weiterhin, aber er extrahiert und zeigt eine leere Zeichenfolge an, wenn das Erscheinungsbild der Stempelanmerkung keinen Textinhalt enthält.

#### F: Wie kann ich den extrahierten Text in einer Datei speichern, anstatt ihn in der Ausgabe anzuzeigen?

 A: Sie können den Code ändern, um den extrahierten Text in einer Datei zu speichern, anstatt ihn in der Konsole anzuzeigen. Ersetzen Sie einfach die`Console.WriteLine` Anweisung mit Code zum Schreiben des Textes in eine Datei.

#### F: Wie kann ich den extrahierten Text zur weiteren Verarbeitung oder Analyse verwenden?

A: Nachdem Sie den Text mit der bereitgestellten Methode extrahiert haben, können Sie ihn in einer Variablen speichern, bearbeiten, analysieren oder nach Bedarf in andere Teile Ihrer Anwendung integrieren.