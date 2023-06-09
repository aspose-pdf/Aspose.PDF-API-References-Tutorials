---
title: Bilder schnell verkleinern
linktitle: Bilder schnell verkleinern
second_title: Aspose.PDF für .NET API-Referenz
description: Reduzieren Sie schnell die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 130
url: /de/net/programming-with-images/fast-shrink-images/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET schnell die Größe von Bildern in einer PDF-Datei reduzieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Initialisieren Sie die Uhrzeit

Bevor wir beginnen, initialisieren wir die Zeit zum Messen der Komprimierungsleistung. Fügen Sie den folgenden Code hinzu, um die Startzeit aufzuzeichnen:

```csharp
var time = DateTime.Now.Ticks;
```

## Schritt 2: Definieren Sie das Dokumentenverzeichnis

 Stellen Sie sicher, dass Sie das richtige Dokumentverzeichnis festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Schritt 4: Optimierungsoptionen initialisieren

 In diesem Schritt initialisieren wir die Optimierungsoptionen für die Bildkomprimierung. Erstellen Sie eine Instanz von`OptimizationOptions` und stellen Sie die entsprechenden Optionen ein. In diesem Beispiel aktivieren wir die Bildkomprimierung, stellen die Bildqualität auf 75 ein und verwenden die schnelle Komprimierungsversion.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Schritt 5: Optimieren Sie das PDF-Dokument

 In diesem Schritt optimieren wir das PDF-Dokument mithilfe der zuvor definierten Optimierungsoptionen. Ruf den`OptimizeResources` Methode der`pdfDocument` Objekt und übergeben Sie die Optimierungsoptionen.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 6: Speichern Sie das aktualisierte PDF-Dokument

 Speichern Sie das aktualisierte PDF-Dokument mit`Save` Methode der`pdfDocument` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode für Fast Shrink Images mit Aspose.PDF für .NET 
```csharp
// Zeit initialisieren
var time = DateTime.Now.Ticks;
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// OptimizationOptions initialisieren
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Legen Sie die Option „CompressImages“ fest
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Legen Sie die Option „ImageQuality“ fest
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Stellen Sie die Image-Komprimierungsversion auf „Schnell“ ein
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Mit Aspose.PDF für .NET haben Sie die Größe von Bildern in einer PDF-Datei schnell reduziert. Die optimierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei jetzt mit reduzierten Bildern für eine effizientere Speicherung oder Freigabe verwenden.