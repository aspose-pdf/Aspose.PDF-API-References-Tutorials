---
title: Alle Seiten in TIFF
linktitle: Alle Seiten in TIFF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie alle Seiten eines PDF-Dokuments in eine TIFF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 20
url: /de/net/programming-with-images/all-pages-to-tiff/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET alle Seiten eines PDF-Dokuments in eine TIFF-Datei konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Schritt 3: Erstellen Sie das Resolution-Objekt

 Ein ... kreieren`Resolution` Objekt, um die Auflösung des TIFF-Bildes festzulegen. In diesem Beispiel verwenden wir eine Auflösung von 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Schritt 4: Erstellen Sie das TiffSettings-Objekt

 Ein ... kreieren`TiffSettings` -Objekt, um Einstellungen für die Ausgabe-TIFF-Datei anzugeben. In diesem Beispiel deaktivieren wir die Komprimierung, verwenden eine Standardfarbtiefe und stellen die Form auf Querformat ein.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
```

## Schritt 5: Erstellen Sie das TIFF-Gerät

 Erstellen Sie ein TIFF-Gerät mit`TiffDevice` Objekt, unter Angabe der Auflösung und TIFF-Einstellungen.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Schritt 6: Alle Seiten konvertieren und Bild speichern

 Benutzen Sie die`Process` Methode des TIFF-Geräts, um alle Seiten des PDF-Dokuments zu konvertieren und das Bild in einer TIFF-Datei zu speichern. Geben Sie den Dateiausgabepfad an.

```csharp
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

### Beispielquellcode für „Alle Seiten in TIFF“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
// Auflösungsobjekt erstellen
Resolution resolution = new Resolution(300);
// Erstellen Sie ein TiffSettings-Objekt
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.None;
tiffSettings.Depth = ColorDepth.Default;
tiffSettings.Shape = ShapeType.Landscape;
tiffSettings.SkipBlankPages = false;
// Erstellen Sie ein TIFF-Gerät
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
tiffDevice.Process(pdfDocument, dataDir + "AllPagesToTIFF_out.tif");
System.Console.WriteLine("PDF all pages converted to one tiff file successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben alle Seiten eines PDF-Dokuments mit Aspose.PDF für .NET erfolgreich in eine TIFF-Datei konvertiert. Sie können die generierte TIFF-Datei nun in Ihren Projekten oder Anwendungen verwenden.