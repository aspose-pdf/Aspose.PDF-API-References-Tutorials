---
title: Flate-Decode-Komprimierung
linktitle: Flate-Decode-Komprimierung
second_title: Aspose.PDF für .NET API-Referenz
description: Komprimieren Sie Bilder in einer PDF-Datei effizient mit der Flate-Decode-Komprimierung mit Aspose.PDF für .NET.
type: docs
weight: 140
url: /de/net/programming-with-images/flate-decode-compression/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie Bilder mithilfe der Flate-Decode-Komprimierung mit Aspose.PDF für .NET in eine PDF-Datei komprimieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Stellen Sie sicher, dass Sie das richtige Dokumentverzeichnis festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## Schritt 3: Optimierungsoptionen initialisieren

 In diesem Schritt initialisieren wir die Optimierungsoptionen für die Bildkomprimierung. Erstellen Sie eine Instanz von`OptimizationOptions` und stellen Sie die entsprechenden Optionen ein. In diesem Beispiel verwenden wir die Flate-Decode-Komprimierung, um die Bilder zu optimieren.

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## Schritt 4: Optimieren Sie das PDF-Dokument

 In diesem Schritt optimieren wir das PDF-Dokument mithilfe der zuvor definierten Optimierungsoptionen. Ruf den`OptimizeResources` Methode der`doc` Objekt und übergeben Sie die Optimierungsoptionen.

```csharp
doc.OptimizeResources(optimizationOptions);
```

## Schritt 5: Speichern Sie das aktualisierte PDF-Dokument

 Speichern Sie das aktualisierte PDF-Dokument mit`Save` Methode der`doc` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### Beispielquellcode für die Flate-Decode-Komprimierung mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document doc = new Document(dataDir + "AddImage.pdf");
// OptimizationOptions initialisieren
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//Um das Bild mithilfe der FlateDecode-Komprimierung zu optimieren, stellen Sie die Optimierungsoptionen auf Flate ein
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
// Legen Sie Optimierungsoptionen fest
doc.OptimizeResources(optimizationOptions);
// Dokument speichern
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben Bilder mithilfe der Flate-Decode-Komprimierung mit Aspose.PDF für .NET erfolgreich in eine PDF-Datei komprimiert. Die optimierte PDF-Datei wird im angegebenen Verzeichnis gespeichert. Sie können diese PDF-Datei jetzt für eine effizientere Speicherung oder Freigabe verwenden.