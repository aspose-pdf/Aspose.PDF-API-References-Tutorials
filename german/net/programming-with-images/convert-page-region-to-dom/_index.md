---
title: Konvertieren Sie den Seitenbereich in DOM
linktitle: Konvertieren Sie den Seitenbereich in DOM
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach einen bestimmten Bereich einer PDF-Seite in ein Document Object Model (DOM).
type: docs
weight: 80
url: /de/net/programming-with-images/convert-page-region-to-dom/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen bestimmten Bereich einer Seite in ein Document Object Model (DOM) konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Schritt 3: Holen Sie sich das Seitenbereichsrechteck

 In diesem Schritt definieren wir ein Rechteck, das den spezifischen Bereich der Seite darstellt, den wir in DOM konvertieren möchten. Benutzen Sie die`Aspose.Pdf.Rectangle` Klasse zum Definieren der Koordinaten des Rechtecks.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Schritt 4: Definieren Sie den Zuschneidebereich der Seite

 Benutzen Sie die`CropBox` Eigentum der`Page` -Objekt, um das Zuschneidefeld der Seite auf das gewünschte Bereichsrechteck festzulegen.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Schritt 5: Speichern Sie das zugeschnittene PDF-Dokument in einem Stream

 In diesem Schritt speichern wir das zugeschnittene PDF-Dokument mithilfe von in einem Stream`MemoryStream` Klasse.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Schritt 6: Öffnen Sie das zugeschnittene PDF-Dokument und konvertieren Sie es in ein Bild

 Öffnen Sie das zugeschnittene PDF-Dokument mit`Document` Klasse und konvertieren Sie es in ein Bild. Wir verwenden eine Auflösung von 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Schritt 7: Konvertieren Sie die spezifische Seite in ein Bild

 Konvertieren Sie die bestimmte Seite mithilfe von in ein Bild`Process` Methode der`pngDevice` Objekt. Geben Sie den Bildausgabepfad an.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Beispielquellcode für „Seitenbereich in DOM konvertieren“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document( dataDir + "AddImage.pdf");
// Erhalten Sie ein Rechteck eines bestimmten Seitenbereichs
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
//Legen Sie den CropBox-Wert entsprechend dem Rechteck des gewünschten Seitenbereichs fest
document.Pages[1].CropBox = pageRect;
// Zugeschnittenes Dokument im Stream speichern
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Öffnen Sie ein zugeschnittenes PDF-Dokument und konvertieren Sie es in ein Bild
document = new Document(ms);
// Auflösungsobjekt erstellen
Resolution resolution = new Resolution(300);
// Erstellen Sie ein PNG-Gerät mit angegebenen Attributen
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich einen bestimmten Bereich einer Seite in ein Document Object Model (DOM) konvertiert. Das resultierende Bild wird im angegebenen Verzeichnis gespeichert. Sie können dieses Bild nun in Ihren Projekten oder Anwendungen verwenden.