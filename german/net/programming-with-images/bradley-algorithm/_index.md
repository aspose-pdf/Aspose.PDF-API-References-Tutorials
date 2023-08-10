---
title: Bradley-Algorithmus
linktitle: Bradley-Algorithmus
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie ein PDF-Dokument mithilfe des Bradley-Algorithmus mit Aspose.PDF für .NET.
type: docs
weight: 30
url: /de/net/programming-with-images/bradley-algorithm/
---
In dieser Schritt-für-Schritt-Anleitung wird erläutert, wie Sie den Bradley-Algorithmus mit Aspose.PDF für .NET verwenden. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

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

## Schritt 3: Ausgabedateien definieren

 Definieren Sie die Ausgabedateinamen für das resultierende Bild und das Binärbild. Ersetzen`"resultant_out.tif"` Und`"37116-bin_out.tif"` mit den gewünschten Namen für die Ausgabedateien.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## Schritt 4: Erstellen Sie das Resolution-Objekt

 Ein ... kreieren`Resolution`Objekt, um die Auflösung des TIFF-Bildes festzulegen. In diesem Beispiel verwenden wir eine Auflösung von 300 dpi.

```csharp
Resolution resolution = new Resolution(300);
```

## Schritt 5: Erstellen Sie das TiffSettings-Objekt

 Ein ... kreieren`TiffSettings`-Objekt, um Einstellungen für die Ausgabe-TIFF-Datei anzugeben. In diesem Beispiel verwenden wir die LZW-Komprimierung und eine Farbtiefe von 1 Bit pro Pixel (1-bpp-Format).

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## Schritt 6: Erstellen Sie das TIFF-Gerät

 Erstellen Sie ein TIFF-Gerät mit`TiffDevice` Objekt, unter Angabe der Auflösung und TIFF-Einstellungen.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## Schritt 7: Konvertieren Sie die spezifische Seite und speichern Sie das Bild

 Benutzen Sie die`Process` Methode des TIFF-Geräts, um eine bestimmte Seite des PDF-Dokuments zu konvertieren und das Bild in einer TIFF-Datei zu speichern. Geben Sie den Dateiausgabepfad an.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## Schritt 8: Binarisieren Sie das Bild mit dem Bradley-Algorithmus

 Benutzen Sie die`BinarizeBradley` Methode des TIFF-Geräts, um das Bild mithilfe des Bradley-Algorithmus zu binarisieren. Diese Methode verwendet einen Eingabestream des Originalbilds und einen Ausgabestream für das Binärbild. Geben Sie den Binärisierungsschwellenwert an (in diesem Beispiel 0,1).

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

### Beispielquellcode für den Bradley-Algorithmus mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
// Auflösungsobjekt erstellen
Resolution resolution = new Resolution(300);
// Erstellen Sie ein TiffSettings-Objekt
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
// Erstellen Sie ein TIFF-Gerät
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
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

Herzlichen Glückwunsch! Sie haben die Konvertierung mithilfe des Bradley-Algorithmus mit Aspose.PDF für .NET erfolgreich abgeschlossen. Die resultierenden Bilder können Sie nun in Ihren Projekten oder Anwendungen verwenden.

### FAQs

#### F: Was ist der Bradley-Algorithmus und in welcher Beziehung steht er zu Aspose.PDF für .NET?

A: Der Bradley-Algorithmus ist eine Bildverarbeitungstechnik zur Verbesserung der Bildqualität und -schärfe. Aspose.PDF für .NET bietet eine praktische Möglichkeit, den Bradley-Algorithmus auf PDF-Dokumente anzuwenden, was zu verbesserten Bildern führt.

#### F: Wie richte ich meine Umgebung für die Verwendung des Bradley-Algorithmus mit Aspose.PDF für .NET ein?

A: Bevor Sie beginnen, stellen Sie sicher, dass Aspose.PDF für .NET ordnungsgemäß installiert und Ihre Entwicklungsumgebung konfiguriert ist.

#### F: Welche Bedeutung hat die Definition des Dokumentverzeichnisses im Bradley-Algorithmus-Prozess?

A: Die Angabe des richtigen Dokumentverzeichnisses ist entscheidend, um sicherzustellen, dass sich das PDF-Dokument im richtigen Pfad für die Verarbeitung befindet.

#### F: Wie öffne ich ein PDF-Dokument mit Aspose.PDF für .NET im Bradley-Algorithmus?

 A: Benutzen Sie die`Document` Klasse zum Öffnen des PDF-Dokuments, das als Eingabe für den Bradley-Algorithmus-Prozess dient.

#### F: Was ist der Zweck der Definition von Ausgabedateinamen für das Bild und das Binärbild im Bradley-Algorithmus-Prozess?

A: Durch das Definieren von Ausgabedateinamen können Sie angeben, wo das resultierende Bild und das Binärbild nach Anwendung des Bradley-Algorithmus gespeichert werden.

#### F: Wie wirkt sich die Auflösungseinstellung auf die TIFF-Bildqualität im Bradley-Algorithmus-Prozess aus?

A: Die Auflösungseinstellung bestimmt den Detaillierungsgrad und die Klarheit des resultierenden TIFF-Bildes nach Anwendung des Bradley-Algorithmus.

#### F: Welche Einstellungen kann ich für das ausgegebene TIFF-Bild im Bradley-Algorithmus-Prozess anpassen?
A: Sie können Einstellungen wie Komprimierungstyp und Farbtiefe anpassen, um die gewünschte Ausgabe für das TIFF-Bild zu erzielen.

#### F: Welchen Beitrag leistet das TIFF-Gerät zum Bradley-Algorithmus-Prozess?

A: Das TIFF-Gerät fungiert als Werkzeug zur Bildverarbeitung und Anwendung des Bradley-Algorithmus, was zu einer verbesserten Bildqualität führt.

#### F: Wie konvertiere ich eine bestimmte Seite eines PDF-Dokuments im Bradley-Algorithmus-Prozess in ein TIFF-Bild?

 A: Nutzen Sie die`Process` Methode des TIFF-Geräts, um eine bestimmte Seite des PDF-Dokuments in ein TIFF-Bild umzuwandeln, das dann mit dem Bradley-Algorithmus weiterverarbeitet werden kann.