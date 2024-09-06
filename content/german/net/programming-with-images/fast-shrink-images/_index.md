---
title: Schnell verkleinerte Bilder
linktitle: Schnell verkleinerte Bilder
second_title: Aspose.PDF für .NET API-Referenz
description: Reduzieren Sie schnell die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 130
url: /de/net/programming-with-images/fast-shrink-images/
---
Diese Anleitung zeigt Ihnen Schritt für Schritt, wie Sie die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET schnell reduzieren können. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Initialisieren Sie die Zeit

Bevor wir beginnen, initialisieren wir die Zeit, um die Komprimierungsleistung zu messen. Fügen Sie den folgenden Code hinzu, um die Startzeit aufzuzeichnen:

```csharp
var time = DateTime.Now.Ticks;
```

## Schritt 2: Dokumentverzeichnis festlegen

 Stellen Sie sicher, dass Sie das richtige Dokumentverzeichnis angeben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 3: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Verwenden Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## Schritt 4: Optimierungsoptionen initialisieren

 In diesem Schritt initialisieren wir die Optimierungsoptionen für die Bildkomprimierung. Erstellen Sie eine Instanz von`OptimizationOptions` und legen Sie die entsprechenden Optionen fest. In diesem Beispiel aktivieren wir die Bildkomprimierung, setzen die Bildqualität auf 75 und verwenden die schnelle Komprimierungsversion.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## Schritt 5: Optimieren Sie das PDF-Dokument

In diesem Schritt optimieren wir das PDF-Dokument mit den zuvor definierten Optimierungsoptionen. Rufen Sie die`OptimizeResources` Methode der`pdfDocument` Objekt und übergeben Sie die Optimierungsoptionen.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Schritt 6: Speichern Sie das aktualisierte PDF-Dokument

 Speichern Sie das aktualisierte PDF-Dokument mit dem`Save` Methode der`pdfDocument` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispiel-Quellcode für Fast Shrink Images mit Aspose.PDF für .NET 
```csharp
// Initialisierungszeit
var time = DateTime.Now.Ticks;
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
// Initialisieren Sie die Optimierungsoptionen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
// Option „CompressImages“ festlegen
optimizeOptions.ImageCompressionOptions.CompressImages = true;
// Option „Bildqualität festlegen“
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
// Stellen Sie die Bildkomprimierungsversion auf „schnell“ ein.
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

Glückwunsch! Sie haben die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET schnell reduziert. Die optimierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei mit verkleinerten Bildern jetzt für effizientere Speicher- oder Freigabezwecke verwenden.

### Häufig gestellte Fragen

#### F: Warum sollte ich die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET schnell reduzieren wollen?

A: Durch eine schnelle Reduzierung der Bildgröße in einer PDF-Datei können Sie die Datei für die Speicherung, Freigabe oder Übertragung optimieren. Dies führt zu einer verbesserten Leistung und einem geringeren Ressourcenverbrauch.

#### F: Welche Vorteile bietet die Bildkomprimierung in einem PDF-Dokument?

A: Durch die Bildkomprimierung in einem PDF-Dokument wird die Dateigröße bei gleichzeitiger Beibehaltung einer akzeptablen Bildqualität minimiert, was zu schnelleren Ladezeiten, geringerem Speicherbedarf und einer verbesserten Effizienz der Datenübertragung führt.

#### F: Wie ermöglicht Aspose.PDF für .NET eine schnelle Bildgrößenreduzierung in einer PDF-Datei?

A: Aspose.PDF für .NET bietet einen optimierten Prozess zum Öffnen eines PDF-Dokuments, Anwenden von Bildkomprimierungsoptionen und Speichern der optimierten PDF-Datei mit reduzierter Bildgröße.

####  F: Welche Bedeutung hat das`OptimizationOptions` class in fast image size reduction?

 A: Die`OptimizationOptions` Mit der Klasse können Sie verschiedene Optimierungseinstellungen, einschließlich Bildkomprimierungsoptionen, definieren, um die Größe von Bildern im PDF-Dokument effektiv zu reduzieren.

#### F: Kann ich die Bildkomprimierungseinstellungen anpassen, um das Gleichgewicht zwischen Dateigröße und Bildqualität zu steuern?

A: Ja, Sie können die Bildkomprimierungseinstellungen anpassen, indem Sie Parameter wie Bildqualität und Komprimierungsversion verändern, um das gewünschte Gleichgewicht zwischen Dateigröße und Bilddarstellung zu erreichen.

####  F: Wie funktioniert das`pdfDocument.OptimizeResources` method work to reduce image sizes?

 A: Die`OptimizeResources` Die Methode analysiert das PDF-Dokument und wendet die angegebenen Optimierungsoptionen an, einschließlich Bildkomprimierungseinstellungen, um die Größe von Bildern und anderen Ressourcen zu reduzieren.

#### F: Ist es möglich, eine schnelle Bildgrößenreduzierung auf einen bestimmten Seitenbereich innerhalb eines PDF-Dokuments anzuwenden?

 A: Die`OptimizeResources` Methode wendet Optimierungsoptionen auf das gesamte PDF-Dokument an. Wenn Sie die Optimierung auf bestimmte Seiten anwenden möchten, müssen Sie diese Seiten vor der Optimierung in ein neues Dokument extrahieren.

#### F: In welchen Szenarien kann eine schnelle Bildgrößenreduzierung von Vorteil sein?

A: Eine schnelle Bildgrößenreduzierung kann von Vorteil sein, wenn Sie PDF-Dateien für die Online-Verteilung, als E-Mail-Anhang oder zur Archivierung vorbereiten oder wenn Sie mit großen Dokumenten mit vielen Bildern arbeiten.

#### F: Hat die Reduzierung der Bildgröße Auswirkungen auf die visuelle Qualität der Bilder im PDF-Dokument?

A: Die Reduzierung der Bildgröße durch Komprimierung kann sich in gewissem Maße auf die Bildqualität auswirken. Es ist wichtig, ein Gleichgewicht zwischen Größenreduzierung und akzeptabler Bildqualität zu finden.

#### F: Wie kann ich die Leistung des schnellen Bildgrößenreduzierungsprozesses messen?

 A: Sie können die Leistung messen, indem Sie die Startzeit mit dem`DateTime.Now.Ticks` Methode vor dem Optimierungsprozess und Berechnung der nach dem Prozess verstrichenen Zeit.