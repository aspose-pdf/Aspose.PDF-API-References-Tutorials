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

Herzlichen Glückwunsch! Mit Aspose.PDF für .NET haben Sie die Größe von Bildern in einer PDF schnell reduziert. Die optimierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei jetzt mit reduzierten Bildern für eine effizientere Speicherung oder Freigabe verwenden.

### FAQs

#### F: Warum sollte ich die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET schnell reduzieren wollen?

A: Das schnelle Reduzieren der Größe von Bildern in einer PDF-Datei kann dazu beitragen, die Datei für die Speicherung, Freigabe oder Übertragung zu optimieren, was zu einer verbesserten Leistung und einem geringeren Ressourcenverbrauch führt.

#### F: Welche Vorteile bietet die Bildkomprimierung in einem PDF-Dokument?

A: Die Bildkomprimierung in einem PDF-Dokument trägt dazu bei, die Dateigröße zu minimieren und gleichzeitig eine akzeptable Bildqualität beizubehalten, was zu schnelleren Ladezeiten, geringeren Speicheranforderungen und einer verbesserten Datenübertragungseffizienz führt.

#### F: Wie ermöglicht Aspose.PDF für .NET eine schnelle Reduzierung der Bildgröße in einer PDF-Datei?

A: Aspose.PDF für .NET bietet einen optimierten Prozess zum Öffnen eines PDF-Dokuments, zum Anwenden von Bildkomprimierungsoptionen und zum Speichern der optimierten PDF-Datei mit reduzierten Bildgrößen.

####  F: Welche Bedeutung hat das?`OptimizationOptions` class in fast image size reduction?

 A: Die`OptimizationOptions`Mit der Klasse können Sie verschiedene Optimierungseinstellungen definieren, einschließlich Bildkomprimierungsoptionen, um die Größe von Bildern im PDF-Dokument effektiv zu reduzieren.

#### F: Kann ich die Bildkomprimierungseinstellungen anpassen, um das Gleichgewicht zwischen Dateigröße und Bildqualität zu steuern?

A: Ja, Sie können die Bildkomprimierungseinstellungen anpassen, indem Sie Parameter wie Bildqualität und Komprimierungsversion anpassen, um das gewünschte Gleichgewicht zwischen Dateigröße und Bilderscheinung zu erreichen.

####  F: Wie funktioniert das?`pdfDocument.OptimizeResources` method work to reduce image sizes?

 A: Die`OptimizeResources` Die Methode analysiert das PDF-Dokument und wendet die angegebenen Optimierungsoptionen an, einschließlich Bildkomprimierungseinstellungen, um die Größe von Bildern und anderen Ressourcen zu reduzieren.

#### F: Ist es möglich, eine schnelle Bildgrößenreduzierung auf einen bestimmten Seitenbereich in einem PDF-Dokument anzuwenden?

 A: Die`OptimizeResources` Die Methode wendet Optimierungsoptionen auf das gesamte PDF-Dokument an. Wenn Sie die Optimierung auf bestimmte Seiten anwenden möchten, müssen Sie diese Seiten vor der Optimierung in ein neues Dokument extrahieren.

#### F: In welchen Szenarien kann eine schnelle Reduzierung der Bildgröße von Vorteil sein?

A: Eine schnelle Reduzierung der Bildgröße kann bei der Vorbereitung von PDF-Dateien für die Online-Verteilung, E-Mail-Anhänge, Archivierung oder bei der Arbeit mit großen Dokumenten mit vielen Bildern von Vorteil sein.

#### F: Hat die Reduzierung der Bildgröße Auswirkungen auf die visuelle Qualität der Bilder im PDF-Dokument?

A: Die Reduzierung der Bildgröße durch Komprimierung kann sich in gewissem Maße auf die Bildqualität auswirken. Es ist wichtig, ein Gleichgewicht zwischen Größenreduzierung und akzeptabler Bildqualität zu finden.

#### F: Wie kann ich die Leistung des schnellen Bildgrößenreduzierungsprozesses messen?

 A: Sie können die Leistung messen, indem Sie die Startzeit mit aufzeichnen`DateTime.Now.Ticks` Methode vor dem Optimierungsprozess und Berechnung der nach dem Prozess verstrichenen Zeit.