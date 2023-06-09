---
title: Größe von Bildern ändern
linktitle: Größe von Bildern ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Größe von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 250
url: /de/net/programming-with-images/resize-images/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Größe von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET ändern. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
// Initialisieren Sie die Uhrzeit
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Initialisierung der Optimierungsoptionen

Bevor wir die Größe der Bilder ändern, müssen wir die Optimierungsoptionen initialisieren. Verwenden Sie den folgenden Code:

```csharp
// OptimizationOptions initialisieren
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Aktivieren Sie die Option „CompressImages“.
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Bildqualität einstellen
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Aktivieren Sie die Option „ResizeImages“.
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Stellen Sie die maximale Auflösung ein
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Sie können die Optimierungseinstellungen entsprechend Ihren Bedürfnissen anpassen.

## Schritt 3: Optimierung des PDF-Dokuments

Jetzt optimieren wir das PDF-Dokument mit den von uns definierten Optimierungsoptionen. Verwenden Sie den folgenden Code:

```csharp
// Optimieren Sie das PDF-Dokument mit den OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Speichern Sie das aktualisierte Dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das aktualisierte PDF-Dokument an.

### Beispielquellcode für die Größenänderung von Bildern mit Aspose.PDF für .NET 
```csharp
// Zeit initialisieren
var time = DateTime.Now.Ticks;
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// OptimizationOptions initialisieren
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Legen Sie die Option „CompressImages“ fest
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Legen Sie die Option „ImageQuality“ fest
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Legen Sie die Option „ResizeImage“ fest
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Legen Sie die Option „MaxResolution“ fest
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
// Optimieren Sie PDF-Dokumente mit OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben die Größe von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET erfolgreich geändert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um die Größe von Bildern in PDF-Dateien zu ändern.