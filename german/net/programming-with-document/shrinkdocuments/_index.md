---
title: Dokumente verkleinern
linktitle: Dokumente verkleinern
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.PDF für .NET PDF-Dokumente verkleinern.
type: docs
weight: 350
url: /de/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF für .NET ist eine leistungsstarke Bibliothek, die es Entwicklern ermöglicht, PDF-Dokumente mit C# zu erstellen, zu bearbeiten und zu optimieren. In diesem Tutorial gehen wir ein Beispiel durch, wie man mit Aspose.PDF ein PDF-Dokument verkleinert.

## Schritt 1: Laden des PDF-Dokuments

 Um ein PDF-Dokument zu verkleinern, müssen wir es zunächst mit Aspose.PDF in unsere C#-Anwendung laden. Im folgenden Code geben wir den Pfad zu unserem PDF-Dokument an und erstellen eine neue Instanz davon`Document` Klasse.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Schritt 2: Verkleinern des PDF-Dokuments

 Sobald wir das PDF-Dokument geladen haben, können wir es verwenden`OptimizeResources` Methode der`Document`Klasse, um das Dokument zu optimieren und möglicherweise seine Größe zu verkleinern. Beachten Sie, dass diese Methode keine Dokumentverkleinerung garantieren kann, da einige PDF-Dokumente möglicherweise bereits stark optimiert sind.

```csharp
// PDF-Dokument optimieren. Beachten Sie jedoch, dass diese Methode die Verkleinerung des Dokuments nicht garantieren kann
pdfDocument.OptimizeResources();
```

## Schritt 3: Speichern des aktualisierten PDF-Dokuments

 Nachdem wir das PDF-Dokument optimiert haben, können wir die aktualisierte Version mithilfe von in einer neuen Datei speichern`Save` Methode der`Document` Klasse. Im folgenden Code geben wir den Pfad und Dateinamen der Ausgabedatei an.

```csharp
// Geben Sie den Pfad der Ausgabedatei an
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(outputFilePath);
```

### Beispielquellcode für Shrink Documents mit Aspose.PDF für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
	// PDF-Dokument optimieren. Beachten Sie jedoch, dass diese Methode die Verkleinerung des Dokuments nicht garantieren kann
	pdfDocument.OptimizeResources();
	dataDir = dataDir + "ShrinkDocument_out.pdf";
	// Aktualisiertes Dokument speichern
	pdfDocument.Save(dataDir);
	
```
