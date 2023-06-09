---
title: CGM-Bild in PDF
linktitle: CGM-Bild in PDF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie CGM-Bilder ganz einfach in PDF mit Aspose.PDF für .NET.
type: docs
weight: 40
url: /de/net/programming-with-images/cgm-image-to-pdf/
---

In dieser Schritt-für-Schritt-Anleitung wird erläutert, wie Sie mit Aspose.PDF für .NET ein CGM-Bild in PDF konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihre CGM-Datei befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Definieren Sie die Eingabe- und Ausgabedatei

 Legen Sie den Namen der CGM-Eingabedatei und den Namen der PDF-Ausgabedatei fest. Ersetzen`"corvette.cgm"` mit dem Namen Ihrer CGM-Datei und aktualisieren Sie sie`dataDir`mit dem gewünschten Ausgabeverzeichnis und PDF-Dateinamen.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Schritt 3: CGM-Bild in PDF konvertieren

 Benutzen Sie die`Produce` Methode von`PdfProducer` um die CGM-Datei in das PDF-Format zu konvertieren`ImportFormat.Cgm`. Geben Sie die CGM-Eingabedatei und die PDF-Ausgabedatei an.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Beispielquellcode für CGMImage zu PDF mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Speichern Sie CGM im PDF-Format
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben eine CGM-Datei mit Aspose.PDF für .NET erfolgreich in PDF konvertiert. Sie können die generierte PDF-Datei nun in Ihren Projekten oder Anwendungen verwenden.