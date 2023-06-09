---
title: Bilder verkleinern
linktitle: Bilder verkleinern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Reduzieren der Größe von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 280
url: /de/net/programming-with-images/shrink-images/
---

In diesem Tutorial erklären wir Ihnen, wie Sie mit Aspose.PDF für .NET die Größe von Bildern in einem PDF-Dokument reduzieren. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Initialisierung der Optimierungsoptionen

Als nächstes initialisieren wir die Optimierungsoptionen, um die Größe der Bilder zu reduzieren. Verwenden Sie den folgenden Code:

```csharp
// OptimizationOptions initialisieren
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Aktivieren Sie die Option „CompressImages“.
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Bildqualität einstellen
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

Sie können die Optimierungseinstellungen entsprechend Ihren Bedürfnissen anpassen.

## Schritt 3: Optimierung des PDF-Dokuments

Jetzt optimieren wir das PDF-Dokument, indem wir die Größe der Bilder reduzieren. Verwenden Sie den folgenden Code:

```csharp
// Optimieren Sie das PDF-Dokument mit den OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
// Speichern Sie das aktualisierte Dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das aktualisierte PDF-Dokument an.

### Beispielquellcode für Shrink Images mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// OptimizationOptions initialisieren
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Legen Sie die Option „CompressImages“ fest
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Legen Sie die Option „ImageQuality“ fest
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben die Größe von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET erfolgreich reduziert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um die Größe von Bildern in PDF-Dateien zu optimieren.