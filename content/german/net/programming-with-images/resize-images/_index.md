---
title: Größe von Bildern in PDF-Dateien ändern
linktitle: Größe von Bildern in PDF-Dateien ändern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Ändern der Größe von Bildern in PDF-Dateien mit Aspose.PDF für .NET.
type: docs
weight: 250
url: /de/net/programming-with-images/resize-images/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie die Größe von Bildern in PDF-Dateien mit Aspose.PDF für .NET ändern. Befolgen Sie diese Schritte, um diesen Vorgang problemlos durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können sie von der offiziellen Aspose-Website herunterladen.

## Schritt 1: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
// Initialisieren Sie die Zeit
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Initialisierung der Optimierungsoptionen

Bevor wir die Größe der Bilder ändern, müssen wir die Optimierungsoptionen initialisieren. Verwenden Sie den folgenden Code:

```csharp
// Initialisieren Sie die Optimierungsoptionen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

// Aktivieren Sie die Option CompressImages
optimizeOptions.ImageCompressionOptions.CompressImages = true;

// Bildqualität einstellen
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

// Aktivieren Sie die Option „ResizeImages“
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

// Maximale Auflösung einstellen
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

Sie können die Optimierungseinstellungen entsprechend Ihren Bedürfnissen anpassen.

## Schritt 3: Optimierung des PDF-Dokuments

Nun optimieren wir das PDF-Dokument mit den von uns definierten Optimierungsoptionen. Verwenden Sie den folgenden Code:

```csharp
// Optimieren Sie das PDF-Dokument mit den Optimierungsoptionen
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
// Speichern des aktualisierten Dokuments
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das aktualisierte PDF-Dokument an.

### Beispiel-Quellcode zum Ändern der Bildgröße mit Aspose.PDF für .NET 
```csharp
// Initialisierungszeit
var time = DateTime.Now.Ticks;
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
// Initialisieren Sie die Optimierungsoptionen
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
// Option „CompressImages“ festlegen
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
// Option „Bildqualität festlegen“
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
// Option „ResizeImage“ festlegen
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
// Option „MaxResolution festlegen“
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

### Häufig gestellte Fragen

#### F: Warum sollte ich die Größe von Bildern in einer PDF-Datei mit Aspose.PDF für .NET ändern wollen?

A: Durch die Größenanpassung von Bildern in einer PDF-Datei können Sie die Größe des Dokuments optimieren und seine Leistung verbessern. Dies ist insbesondere dann nützlich, wenn Sie die Dateigröße verringern möchten, um PDF-Dokumente einfacher freigeben oder schneller laden zu können.

#### F: Welchen Einfluss hat die Größenänderung von Bildern auf die Qualität der Bilder im PDF-Dokument?

 A: Bei der Bildgrößenänderung werden die Abmessungen und die Auflösung von Bildern reduziert, was zu einer kleineren Dateigröße führen kann. Dies kann zwar die Bildqualität bis zu einem gewissen Grad reduzieren, aber die`ImageQuality` Parameter (`optimizeOptions.ImageCompressionOptions.ImageQuality`) können Sie das Gleichgewicht zwischen Bildgröße und Qualität steuern.

####  F: Was ist der Zweck der`MaxResolution` option in the optimization settings?

 A: Die`MaxResolution` Option (`optimizeOptions.ImageCompressionOptions.MaxResolution`) legt die maximale Auflösung für Bilder im PDF-Dokument fest. Bilder mit höheren Auflösungen werden während des Optimierungsprozesses auf diesen angegebenen Wert herunterskaliert.

#### F: Wie passe ich die Optimierungseinstellungen für die Bildgrößenänderung an?

 A: Im bereitgestellten Code können Sie die Werte der Optimierungsoptionen ändern, um die gewünschte Bildgröße und -komprimierung zu erreichen. Sie können beispielsweise die`ImageQuality` Und`MaxResolution` Werte, um den Optimierungsprozess Ihren Anforderungen entsprechend anzupassen.

#### F: Kann ich die Größe bestimmter Bilder im PDF-Dokument selektiv ändern?

A: Der bereitgestellte Code optimiert alle Bilder im PDF-Dokument mit denselben Optimierungseinstellungen. Wenn Sie die Größe bestimmter Bilder selektiv ändern möchten, müssen Sie den Code möglicherweise ändern, um diese Bilder einzeln anzusprechen.

####  F: Wie funktioniert das`pdfDocument.OptimizeResources` method work in resizing images?

 A: Die`OptimizeResources` Die Methode wendet die angegebenen Optimierungsoptionen auf das PDF-Dokument an, einschließlich Größenanpassung und Komprimierung des Bilds. Sie trägt dazu bei, die Dateigröße des PDF-Dokuments zu reduzieren, indem sie die definierten Optimierungseinstellungen auf seine Ressourcen anwendet.

#### F: Ist es möglich, eine Vorschau der skalierten Bilder anzuzeigen, bevor das PDF-Dokument gespeichert wird?

A: Der bereitgestellte Code optimiert und speichert das PDF-Dokument direkt mit skalierten Bildern. Wenn Sie die skalierten Bilder vor dem Speichern in der Vorschau anzeigen möchten, müssen Sie möglicherweise den Code ändern, um auch Vorschaubilder zu generieren.

#### F: Wie integriere ich diese Methode zur Bildgrößenänderung in meine eigenen Projekte?

A: Um diese Methode in Ihre Projekte zu integrieren, folgen Sie den beschriebenen Schritten und ändern Sie den Code nach Bedarf. Sie können den Prozess der Größenänderung von Bildern in PDF-Dokumenten automatisieren, indem Sie diesen Code in Ihre Anwendung integrieren.

#### F: Bietet die Aspose.PDF-Bibliothek für .NET weitere Funktionen zur PDF-Optimierung?

A: Ja, die Aspose.PDF-Bibliothek für .NET bietet neben der Bildgrößenanpassung verschiedene Optimierungsoptionen, wie z. B. Schriftart- und Textoptimierung, das Entfernen nicht verwendeter Objekte und die Reduzierung redundanter Daten. Sie können die Dokumentation und Beispiele der Bibliothek erkunden, um die gesamte Palette der Optimierungsfunktionen kennenzulernen.