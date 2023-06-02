---
title: Verknüpfen Sie doppelte Streams
linktitle: Verknüpfen Sie doppelte Streams
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie die Funktion „Aspose.PDF for .NET Link Duplicate Streams“ verwenden, um Ihre PDF-Dokumente zu optimieren.
type: docs
weight: 230
url: /de/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF für .NET ist eine umfassende und leistungsstarke Bibliothek, die eine Vielzahl von Funktionen für die Arbeit mit PDF-Dateien bietet. Eine seiner Hauptfunktionen ist die Möglichkeit, PDF-Dateien zu optimieren. In diesem Artikel erklären wir, wie Sie die Funktion „Link Duplicate Streams“ von Aspose.PDF für .NET verwenden, um PDF-Dateien zu optimieren. Wir stellen Schritt-für-Schritt-Anleitungen zur Verfügung und fügen ein vollständiges Quellcode-Beispiel bei, um es den Entwicklern zu erleichtern, mitzumachen.

## Schritt 1: Öffnen des PDF-Dokuments

Gehen Sie folgendermaßen vor, um das PDF-Dokument mit Aspose.PDF für .NET zu öffnen:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Ersetzen Sie im obigen Code „IHR DOKUMENTVERZEICHNIS“ durch den Pfad zu Ihrem Projektverzeichnis.

## Schritt 2: Festlegen der LinkDuplicateStreams-Option

Gehen Sie folgendermaßen vor, um die Option LinkDuplicateStreams festzulegen:

```csharp
// Legen Sie die LinkDupcateStreams-Option fest
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Im obigen Code haben wir eine neue Instanz von OptimizationOptions erstellt und die Option LinkDuplicateStreams auf true gesetzt.

## Schritt 3: Optimieren des PDF-Dokuments

Um das PDF-Dokument zu optimieren, gehen Sie folgendermaßen vor:

```csharp
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Im obigen Code haben wir die OptimizeResources-Methode des pdfDocument-Objekts verwendet, um das PDF-Dokument mithilfe der zuvor erstellten OptimizationOptions zu optimieren.

## Schritt 4: Speichern des aktualisierten Dokuments

Um das aktualisierte Dokument zu speichern, gehen Sie folgendermaßen vor:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
```

Im obigen Code haben wir die Save-Methode des pdfDocument-Objekts verwendet, um das aktualisierte Dokument in einer neuen Datei mit dem Namen „OptimizeDocument_out.pdf“ im Projektverzeichnis zu speichern.

### Beispielquellcode für Link Duplicate Streams mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Legen Sie die LinkDupcateStreams-Option fest
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
```
