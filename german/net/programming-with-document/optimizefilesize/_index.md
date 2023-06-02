---
title: Optimieren Sie die Dateigröße
linktitle: Optimieren Sie die Dateigröße
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie die Dateigröße Ihrer PDF-Dokumente mit Aspose.PDF für .NET optimieren.
type: docs
weight: 250
url: /de/net/programming-with-document/optimizefilesize/
---
Aspose.PDF für .NET ist eine Bibliothek, die es Entwicklern ermöglicht, PDF-Dateien in ihren .NET-Anwendungen zu erstellen, zu bearbeiten und zu bearbeiten. Eine der nützlichsten Funktionen dieser Bibliothek ist die Möglichkeit, die Dateigröße eines PDF-Dokuments zu optimieren. In diesem Artikel stellen wir eine Schritt-für-Schritt-Anleitung zur Optimierung der Dateigröße eines PDF-Dokuments mit Aspose.PDF für .NET bereit.

## Schritt 1: Laden Sie das PDF-Dokument

 Der erste Schritt zur Optimierung der Dateigröße eines PDF-Dokuments besteht darin, das Dokument in Ihre Anwendung zu laden. Sie können dies mit dem tun`Document`Klasse, die von der Aspose.PDF für .NET-Bibliothek bereitgestellt wird. Hier ist ein Beispiel für das Laden eines PDF-Dokuments:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Unbedingt austauschen`YOUR DOCUMENT DIRECTORY` mit dem Pfad zu dem Verzeichnis, das Ihr PDF-Dokument enthält.

## Schritt 2: Optimierungsoptionen festlegen

 Sobald Sie das PDF-Dokument geladen haben, können Sie die Optimierungsoptionen festlegen, um festzulegen, welche Teile des Dokuments Sie optimieren möchten. Der`OptimizationOptions` Mit der von der Aspose.PDF for .NET-Bibliothek bereitgestellten Klasse können Sie verschiedene Optionen zum Optimieren der Dateigröße des PDF-Dokuments angeben. Hier ist ein Beispiel für das Festlegen einiger Optimierungsoptionen:

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

In diesem Beispiel legen wir die folgenden Optionen fest:
- `LinkDuplcateStreams`: Diese Option ermöglicht das Entfernen doppelter Streams im PDF-Dokument, was zur Reduzierung der Dateigröße beitragen kann.
- `RemoveUnusedObjects`: Diese Option ermöglicht das Entfernen aller nicht verwendeten Objekte im PDF-Dokument, was auch zur Reduzierung der Dateigröße beitragen kann.
- `RemoveUnusedStreams`Diese Option ermöglicht das Entfernen aller nicht verwendeten Streams im PDF-Dokument, wodurch die Dateigröße weiter reduziert werden kann.
- `CompressImages`: Diese Option ermöglicht die Komprimierung von Bildern im PDF-Dokument, wodurch die Dateigröße deutlich reduziert werden kann.
- `ImageQuality`: Diese Option legt die Qualität der komprimierten Bilder fest. Eine niedrigere Qualitätseinstellung führt zu einer kleineren Dateigröße, kann aber auch zu einer geringeren Bildqualität führen.

## Schritt 4: Optimieren Sie das PDF-Dokument

 Nachdem Sie nun die Optimierungsoptionen festgelegt haben, können Sie das PDF-Dokument mit optimieren`OptimizeResources` Methode, die von der bereitgestellt wird`Document` Klasse. Hier ist ein Beispiel für die Optimierung des PDF-Dokuments:

```csharp
// Optimieren Sie die Dateigröße, indem Sie nicht verwendete Objekte entfernen
pdfDocument.OptimizeResources(optimizationOptions);
```

## Schritt 5: Speichern Sie das optimierte PDF-Dokument

Sobald Sie das PDF-Dokument optimiert haben, können Sie die optimierte Version in einer neuen Datei speichern. Hier ist ein Beispiel, wie das optimierte PDF-Dokument gespeichert wird:

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);
```

### Beispielquellcode zur Optimierung der Dateigröße mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
// Optimieren Sie die Dateigröße, indem Sie nicht verwendete Objekte entfernen
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
// Ausgabedokument speichern
pdfDocument.Save(dataDir);
```
