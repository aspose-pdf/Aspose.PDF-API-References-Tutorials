---
title: Extrahieren Sie Text aus Stempelanmerkungen
linktitle: Extrahieren Sie Text aus Stempelanmerkungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach Text aus einer Stempelanmerkung in Ihren PDF-Dokumenten extrahieren.
type: docs
weight: 80
url: /de/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in einem PDF-Dokument extrahieren. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um den Text aus einer bestimmten Stempelanmerkung auf einer bestimmten Seite des PDF-Dokuments zu extrahieren.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument
Document doc = new Document(dataDir + "test.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Extrahieren Sie Text aus der Stempelanmerkung

Nachdem Sie das PDF-Dokument geladen haben, können Sie den Text aus der spezifischen Stempelanmerkung extrahieren. Hier ist wie:

```csharp
// Pufferanmerkung abrufen
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Erstellen Sie einen Textabsorber
TextAbsorber ta = new TextAbsorber();

// Sehen Sie sich das Erscheinungsbild der Anmerkung an
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// Zeigen Sie den extrahierten Text an
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

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Text aus einer Stempelanmerkung in einem PDF-Dokument extrahieren. Mit dieser Methode können Sie jetzt Text aus anderen Anmerkungen in Ihren PDF-Dokumenten extrahieren.

### FAQs zum Extrahieren von Text aus Stempelanmerkungen

#### F: Was ist eine Stempelanmerkung in einem PDF-Dokument und warum sollte ich Text daraus extrahieren?

A: Eine Stempelanmerkung in einem PDF-Dokument ist ein grafisches Element, das zur Bereitstellung zusätzlicher Informationen verwendet werden kann, beispielsweise ein Wasserzeichen oder ein Gummistempel. Das Extrahieren von Text aus einer Stempelanmerkung ist nützlich, wenn Sie textbasierten Inhalt aus diesen Anmerkungen abrufen möchten, zu dem Notizen, Beschriftungen oder andere Textinformationen gehören können.

#### F: Wie extrahiert der bereitgestellte C#-Quellcode Text aus einer Stempelanmerkung?

 A: Der bereitgestellte Quellcode zeigt, wie Text aus einer bestimmten Stempelanmerkung auf einer bestimmten Seite eines PDF-Dokuments extrahiert wird. Es verwendet die Aspose.PDF-Bibliothek, um die Stempelanmerkung abzurufen und ihr Erscheinungsbild mithilfe von a zu überprüfen`TextAbsorber`und zeigt dann den extrahierten Text in der Ausgabe an.

#### F: Kann ich mit einem ähnlichen Ansatz Text aus verschiedenen Arten von Anmerkungen extrahieren?

A: Ja, Sie können einen ähnlichen Ansatz verwenden, um Text aus anderen Arten von Anmerkungen zu extrahieren, z. B. Textanmerkungen oder Popup-Anmerkungen. Sie müssten den Code so ändern, dass er auf den spezifischen Anmerkungstyp abzielt, aus dem Sie Text extrahieren möchten.

####  F: Was ist der Zweck des`TextAbsorber` class in the code?

 A: Die`TextAbsorber` Die Klasse wird verwendet, um Text aus verschiedenen Teilen eines PDF-Dokuments zu extrahieren, einschließlich Stempelanmerkungen. Es „absorbiert“ oder erfasst den Textinhalt, der im angegebenen Bereich oder Element der PDF-Datei gefunden wird.

#### F: Wie identifiziere ich die spezifische Stempelanmerkung, aus der ich Text extrahieren möchte?

 A: Im bereitgestellten Code wird die Stempelanmerkung durch Zugriff auf identifiziert`Annotations` Sammlung einer bestimmten Seite und Verwendung des Index zum Abrufen der gewünschten Anmerkung. Sie können den Index anpassen oder andere Kriterien verwenden, um die Zielanmerkung zu identifizieren.

#### F: Kann ich Text aus mehreren Stempelanmerkungen auf derselben Seite extrahieren?

 A: Ja, Sie können den Code so ändern, dass er die Schleife durchläuft`Annotations`Sammlung einer Seite, Filtern Sie Stempelanmerkungen heraus und extrahieren Sie Text aus jeder Seite.

#### F: Was passiert, wenn die Stempelanmerkung keinen Textinhalt hat? Funktioniert der Code weiterhin?

A: Der Code funktioniert weiterhin, extrahiert jedoch eine leere Zeichenfolge und zeigt sie an, wenn das Erscheinungsbild der Stempelanmerkung keinen Textinhalt enthält.

#### F: Wie kann ich den extrahierten Text in einer Datei speichern, anstatt ihn in der Ausgabe anzuzeigen?

 A: Sie können den Code ändern, um den extrahierten Text in einer Datei zu speichern, anstatt ihn in der Konsole anzuzeigen. Ersetzen Sie einfach die`Console.WriteLine` Anweisung mit Code zum Schreiben des Textes in eine Datei.

#### F: Wie kann ich den extrahierten Text zur weiteren Verarbeitung oder Analyse verwenden?

A: Sobald Sie den Text mit der bereitgestellten Methode extrahiert haben, können Sie ihn bei Bedarf in einer Variablen speichern, manipulieren, analysieren oder in andere Teile Ihrer Anwendung integrieren.