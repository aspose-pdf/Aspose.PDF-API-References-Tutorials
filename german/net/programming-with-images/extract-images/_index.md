---
title: Bilder extrahieren
linktitle: Bilder extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie Bilder ganz einfach aus einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 120
url: /de/net/programming-with-images/extract-images/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Bilder aus einer PDF-Datei extrahieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Schritt 3: Extrahieren Sie ein bestimmtes Bild

 In diesem Schritt extrahieren wir ein bestimmtes Bild von einer bestimmten Seite. Benutzen Sie die`Images` Sammlung der Seite`s `Ressourcenobjekt, um auf das gewünschte Bild zuzugreifen. Im folgenden Beispiel extrahieren wir das Bild mit Index 1 von der ersten Seite.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Schritt 4: Speichern Sie das extrahierte Bild

 Speichern Sie das extrahierte Bild mit in einer Datei`Save` Methode der`xImage`Objekt. Geben Sie den Ausgabepfad und das Bildformat an (in diesem Beispiel verwenden wir das JPEG-Format).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Schritt 5: Speichern Sie die aktualisierte PDF-Datei

 Speichern Sie die aktualisierte PDF-Datei mit`Save` Methode der`pdfDocument` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispielquellcode zum Extrahieren von Bildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extrahieren Sie ein bestimmtes Bild
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Ausgabebild speichern
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder aus einer PDF-Datei extrahiert. Das extrahierte Bild wird im angegebenen Verzeichnis gespeichert und die aktualisierte PDF-Datei wird ebenfalls gespeichert. Sie können diese Dateien nun für Ihre spezifischen Anforderungen verwenden.