---
title: Ändern Sie die Größe von Bildern in einer PDF-Datei
linktitle: Ändern Sie die Größe von Bildern in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Größe von Bildern in PDF-Dateien mit Aspose.PDF für .NET.
type: docs
weight: 250
url: /de/net/programming-with-images/resize-images/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Größe von Bildern in PDF-Dateien mit Aspose.PDF für .NET ändern. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

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

### FAQs

#### F: Warum sollte ich die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET ändern?

A: Die Größenänderung von Bildern in einer PDF-Datei kann dazu beitragen, die Größe des Dokuments zu optimieren und seine Leistung zu verbessern. Dies ist besonders nützlich, wenn Sie die Dateigröße reduzieren möchten, um PDF-Dokumente einfacher zu teilen oder schneller zu laden.

#### F: Wie wirkt sich die Größenänderung von Bildern auf die Qualität der Bilder im PDF-Dokument aus?

 A: Bei der Größenänderung von Bildern werden die Abmessungen und die Auflösung der Bilder reduziert, was zu einer kleineren Dateigröße führen kann. Dies kann zwar die Bildqualität bis zu einem gewissen Grad beeinträchtigen, die`ImageQuality` Parameter (`optimizeOptions.ImageCompressionOptions.ImageQuality`) ermöglicht Ihnen die Steuerung des Gleichgewichts zwischen Bildgröße und -qualität.

####  F: Was ist der Zweck des`MaxResolution` option in the optimization settings?

 A: Die`MaxResolution` Möglichkeit (`optimizeOptions.ImageCompressionOptions.MaxResolution`) legt die maximale Auflösung für Bilder im PDF-Dokument fest. Bilder mit höheren Auflösungen werden während des Optimierungsprozesses auf diesen angegebenen Wert verkleinert.

#### F: Wie passe ich die Optimierungseinstellungen für die Bildgrößenänderung an?

 A: Im bereitgestellten Code können Sie die Werte der Optimierungsoptionen ändern, um die gewünschte Bildgröße und -komprimierung zu erreichen. Sie können beispielsweise die ändern`ImageQuality` Und`MaxResolution` Werte, um den Optimierungsprozess entsprechend Ihren Anforderungen anzupassen.

#### F: Kann ich die Größe bestimmter Bilder im PDF-Dokument gezielt ändern?

A: Der bereitgestellte Code optimiert alle Bilder im PDF-Dokument mit denselben Optimierungseinstellungen. Wenn Sie die Größe bestimmter Bilder selektiv ändern möchten, müssen Sie möglicherweise den Code ändern, um diese Bilder einzeln anzusprechen.

####  F: Wie funktioniert das?`pdfDocument.OptimizeResources` method work in resizing images?

 A: Die`OptimizeResources` Die Methode wendet die angegebenen Optimierungsoptionen auf das PDF-Dokument an, einschließlich Bildgrößenänderung und Komprimierung. Es hilft, die Dateigröße des PDF-Dokuments zu reduzieren, indem es die definierten Optimierungseinstellungen auf seine Ressourcen anwendet.

#### F: Ist es möglich, eine Vorschau der verkleinerten Bilder anzuzeigen, bevor das PDF-Dokument gespeichert wird?

A: Der bereitgestellte Code optimiert und speichert das PDF-Dokument direkt mit geänderter Bildgröße. Wenn Sie vor dem Speichern eine Vorschau der verkleinerten Bilder anzeigen möchten, müssen Sie möglicherweise den Code ändern, um auch Vorschaubilder zu generieren.

#### F: Wie integriere ich diese Methode zur Bildgrößenänderung in meine eigenen Projekte?

A: Um diese Methode in Ihre Projekte zu integrieren, befolgen Sie die beschriebenen Schritte und ändern Sie den Code nach Bedarf. Sie können den Prozess der Größenänderung von Bildern in PDF-Dokumenten automatisieren, indem Sie diesen Code in Ihre Anwendung integrieren.

#### F: Bietet die Aspose.PDF für .NET-Bibliothek weitere Funktionen zur PDF-Optimierung?

A: Ja, die Aspose.PDF für .NET-Bibliothek bietet über die Größenänderung von Bildern hinaus verschiedene Optimierungsoptionen, z. B. Schriftart- und Textoptimierung, Entfernen nicht verwendeter Objekte und Reduzieren redundanter Daten. Sie können die Dokumentation und Beispiele der Bibliothek erkunden, um die gesamte Bandbreite an Optimierungsfunktionen zu entdecken.