---
title: Entfernen Sie nicht verwendete Streams
linktitle: Entfernen Sie nicht verwendete Streams
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nicht verwendete Streams aus PDF-Dateien entfernen. Unsere Schritt-für-Schritt-Anleitung.
type: docs
weight: 270
url: /de/net/programming-with-document/removeunusedstreams/
---
In diesem Beispiel besprechen wir, wie Sie mithilfe von Aspose.PDF für .NET nicht verwendete Streams aus PDF-Dokumenten entfernen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, einschließlich des vollständigen Quellcodes mit Erläuterungen.

## Schritt 1: Der Pfad zum Dokumentenverzeichnis

Die erste Zeile des Codes legt den Pfad zu dem Verzeichnis fest, in dem sich Ihr PDF-Dokument befindet. Stellen Sie sicher, dass Sie „IHR DOKUMENTVERZEICHNIS“ durch den tatsächlichen Verzeichnispfad ersetzen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

Die nächste Codezeile öffnet das PDF-Dokument mithilfe der Aspose.PDF for .NET-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Schritt 3: Legen Sie die Option „RemoveUnusedStreams“ fest

Der nächste Schritt besteht darin, die Option RemoveUnusedStreams auf true zu setzen. Dadurch werden alle nicht verwendeten Streams aus dem PDF-Dokument entfernt.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Schritt 4: Optimieren Sie das PDF-Dokument mit OptimizationOptions

Nachdem wir nun die Optimierungsoptionen festgelegt haben, können wir das PDF-Dokument mit der folgenden Codezeile optimieren.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 5: Aktualisiertes Dokument speichern

Schließlich können wir das aktualisierte Dokument mit der Save-Methode der Document-Klasse speichern.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Entfernen nicht verwendeter Streams mit Aspose.PDF für .NET

Unten finden Sie den Beispielquellcode zum Entfernen nicht verwendeter Streams mit Aspose.PDF für .NET.

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Legen Sie die Option „RemoveUsedStreams“ fest
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// Optimieren Sie PDF-Dokumente mit OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Aktualisiertes Dokument speichern
	pdfDocument.Save(dataDir);

```
