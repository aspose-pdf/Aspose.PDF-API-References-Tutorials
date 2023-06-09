---
title: Holen Sie sich Wasserzeichen
linktitle: Holen Sie sich Wasserzeichen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Wasserzeichen aus Ihren PDF-Dokumenten extrahieren.
type: docs
weight: 100
url: /de/net/programming-with-stamps-and-watermarks/get-watermark/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Wasserzeichen aus einem PDF-Dokument erstellen. Wir zeigen Ihnen, wie Sie den bereitgestellten C#-Quellcode verwenden, um die Artefakte einer bestimmten Seite zu durchlaufen und den Typ, den Text und die Position des Wasserzeichens zu ermitteln.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erhalten des Wasserzeichens

Nachdem Sie das PDF-Dokument geladen haben, können Sie die spezifischen Seitenartefakte durchlaufen, um die Wasserzeicheninformationen zu erhalten. Hier ist wie:

```csharp
// Durchsuchen Sie Artefakte und erhalten Sie den Untertyp, den Text und die Position des Wasserzeichens
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Der obige Code durchläuft alle Artefakte auf der ersten Seite des PDF-Dokuments und zeigt den Untertyp, den Text und das Rechteck (Position) jedes gefundenen Wasserzeichens an.

### Beispielquellcode für Get Watermark mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Durchlaufen Sie den Vorgang und ermitteln Sie Wannentyp, Text und Position des Artefakts
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET Wasserzeicheninformationen aus einem PDF-Dokument abrufen. Jetzt können Sie dieses Wissen nutzen, um Wasserzeichen in Ihren PDF-Dokumenten zu analysieren und zu verarbeiten.
