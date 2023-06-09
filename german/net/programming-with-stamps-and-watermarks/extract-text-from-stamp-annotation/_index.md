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
