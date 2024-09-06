---
title: Bradley-Algorithmus
linktitle: Bradley-Algorithmus
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie ein PDF-Dokument mit dem Bradley-Algorithmus mit Aspose.PDF für .NET.
type: docs
weight: 30
url: /de/net/programming-with-images/bradley-algorithm/
---
Diese Schritt-für-Schritt-Anleitung erklärt, wie Sie den Bradley-Algorithmus mit Aspose.PDF für .NET verwenden. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Dokumentverzeichnis festlegen

Stellen Sie vor dem Start sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Verwenden Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## Schritt 3: Ausgabedateien definieren

 Definieren Sie die Ausgabedateinamen für das resultierende Bild und das Binärbild. Ersetzen Sie`"resultant_out.tif"` Und`"37116-bin_out.tif"` mit den gewünschten Namen für die Ausgabedateien.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Schritt 4: Erstellen des Resolution-Objekts

 Erstellen Sie ein`Resolution` Objekt, um die Auflösung des TIFF-Bildes festzulegen. In diesem Beispiel verwenden wir eine Auflösung von 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Schritt 5: Erstellen des TiffSettings-Objekts

 Erstellen Sie ein`TiffSettings` Objekt, um Einstellungen für die Ausgabe-TIFF-Datei anzugeben. In diesem Beispiel verwenden wir LZW-Komprimierung und eine Farbtiefe von 1 Bit pro Pixel (1-bpp-Format).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Schritt 6: Erstellen Sie das TIFF-Gerät

 Erstellen Sie ein TIFF-Gerät mit dem`TiffDevice` Objekt und geben Sie die Auflösung und die TIFF-Einstellungen an.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Schritt 7: Konvertieren Sie die jeweilige Seite und speichern Sie das Bild

 Verwenden Sie die`Process` Methode des TIFF-Geräts, um eine bestimmte Seite des PDF-Dokuments zu konvertieren und das Bild in einer TIFF-Datei zu speichern. Geben Sie den Dateiausgabepfad an.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Schritt 8: Binärisieren Sie das Bild mit dem Bradley-Algorithmus

 Verwenden Sie die`BinarizeBradley`Methode des TIFF-Geräts, um das Bild mit dem Bradley-Algorithmus zu binärisieren. Diese Methode verwendet einen Eingabestream des Originalbilds und einen Ausgabestream für das Binärbild. Geben Sie den Binärisierungsschwellenwert an (in diesem Beispiel 0,1).

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### Beispiel-Quellcode für den Bradley-Algorithmus mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Resolution-Objekt erstellen
Resolution resolution = new Resolution(300);
// TiffSettings-Objekt erstellen
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// TIFF-Gerät erstellen
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben die Konvertierung mit dem Bradley-Algorithmus mit Aspose.PDF für .NET erfolgreich abgeschlossen. Sie können die resultierenden Bilder jetzt in Ihren Projekten oder Anwendungen verwenden.

### Häufig gestellte Fragen

#### F: Was ist der Bradley-Algorithmus und in welcher Beziehung steht er zu Aspose.PDF für .NET?

A: Der Bradley-Algorithmus ist eine Bildverarbeitungstechnik zur Verbesserung der Bildqualität und -schärfe. Aspose.PDF für .NET bietet eine praktische Möglichkeit, den Bradley-Algorithmus auf PDF-Dokumente anzuwenden, was zu verbesserten Bildern führt.

#### F: Wie richte ich meine Umgebung für die Verwendung des Bradley-Algorithmus mit Aspose.PDF für .NET ein?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie Aspose.PDF für .NET richtig installiert und Ihre Entwicklungsumgebung konfiguriert haben.

#### F: Welche Bedeutung hat die Definition des Dokumentverzeichnisses im Bradley-Algorithmus-Prozess?

A: Die Angabe des richtigen Dokumentverzeichnisses ist entscheidend, um sicherzustellen, dass das PDF-Dokument für die Verarbeitung im richtigen Pfad liegt.

#### F: Wie öffne ich ein PDF-Dokument mit Aspose.PDF für .NET im Bradley-Algorithmus?

 A: Verwenden Sie die`Document` Klasse zum Öffnen des PDF-Dokuments, das als Eingabe für den Bradley-Algorithmus-Prozess dient.

#### F: Was ist der Zweck der Definition von Ausgabedateinamen für das Bild und das Binärbild im Bradley-Algorithmus-Prozess?

A: Durch das Definieren von Ausgabedateinamen können Sie angeben, wo das resultierende Bild und das Binärbild nach dem Anwenden des Bradley-Algorithmus gespeichert werden.

#### F: Welchen Einfluss hat die Auflösungseinstellung auf die TIFF-Bildqualität im Bradley-Algorithmus-Prozess?

A: Die Auflösungseinstellung bestimmt den Detailgrad und die Klarheit des resultierenden TIFF-Bildes nach Anwendung des Bradley-Algorithmus.

#### F: Welche Einstellungen kann ich für das TIFF-Ausgabebild im Bradley-Algorithmus-Prozess anpassen?
A: Sie können Einstellungen wie Komprimierungstyp und Farbtiefe anpassen, um die gewünschte Ausgabe für das TIFF-Bild zu erzielen.

#### F: Wie trägt das TIFF-Gerät zum Bradley-Algorithmus-Prozess bei?

A: Das TIFF-Gerät fungiert als Werkzeug zur Bildverarbeitung und Anwendung des Bradley-Algorithmus, was zu einer verbesserten Bildqualität führt.

#### F: Wie konvertiere ich im Bradley-Algorithmus-Prozess eine bestimmte Seite eines PDF-Dokuments in ein TIFF-Bild?

 A: Nutzen Sie die`Process` Methode des TIFF-Geräts, um eine bestimmte Seite des PDF-Dokuments in ein TIFF-Bild umzuwandeln, das dann mit dem Bradley-Algorithmus weiterverarbeitet werden kann.