---
title: Bradley-Algorithmus
linktitle: Bradley-Algorithmus
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit dem Bradley-Algorithmus in Aspose.PDF für .NET ein PDF in TIFF konvertieren. Schritt-für-Schritt-Anleitung, Voraussetzungen und FAQs für eine nahtlose Konvertierung.
type: docs
weight: 30
url: /de/net/programming-with-images/bradley-algorithm/
---
## Einführung

Die Arbeit mit PDF-Dateien kann manchmal mehr erfordern als nur das Lesen oder Bearbeiten – Sie müssen sie möglicherweise in Bilder konvertieren. Eine leistungsstarke Möglichkeit, PDFs in TIFF-Bilder umzuwandeln, ist die Verwendung des Bradley-Algorithmus über die Aspose.PDF für .NET-Bibliothek. Diese Methode gewährleistet qualitativ hochwertige Binärbilder, die sich perfekt für die Dokumentenarchivierung und andere spezielle Anwendungsfälle eignen.

Dieses Tutorial führt Sie durch einen detaillierten, leicht verständlichen Prozess zum Konvertieren einer PDF-Seite in ein TIFF-Bild mit dem Bradley-Binarisierungsalgorithmus. Aspose.PDF für .NET vereinfacht diese Aufgabe und bietet Ihnen die Möglichkeit, Ihre Dokument-Workflows zu automatisieren und zu optimieren.

## Voraussetzungen

Bevor wir uns in den Code vertiefen, stellen wir sicher, dass Sie alles haben, was Sie brauchen, um den Anweisungen zu folgen:

-  Aspose.PDF für .NET: Sie benötigen die Bibliothek. Laden Sie sie herunter von[Hier](https://releases.aspose.com/pdf/net/).
- Visual Studio (oder eine beliebige C#-IDE).
- Grundkenntnisse in C#.
-  Eine gültige Lizenz oder ein[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) von Aspose.

## Pakete importieren

Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces in Ihr Projekt importieren. Diese Bibliotheken bieten Ihnen die Tools zum Bearbeiten von PDF-Dokumenten, zum Konvertieren in das TIFF-Format und zum Anwenden des Bradley-Binarisierungsalgorithmus.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Lassen Sie uns den Vorgang in einfache Schritte unterteilen, damit Sie ihn problemlos nachvollziehen können. Am Ende dieser Anleitung haben Sie mithilfe des Bradley-Algorithmus erfolgreich eine PDF-Seite in ein binäres TIFF-Bild konvertiert.

## Schritt 1: Dokumentverzeichnis festlegen

Im ersten Schritt geben Sie den Pfad zum Verzeichnis an, in dem sich Ihr PDF-Dokument befindet. Außerdem definieren Sie die Ausgabepfade für die zu generierenden TIFF-Bilder.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Pfad zu Ihrer PDF-Datei
```

Hier speichern Sie sowohl die Quell-PDF- als auch die konvertierten TIFF-Dateien. Stellen Sie sicher, dass das Verzeichnis richtig eingestellt ist, damit der Code Dateien fehlerfrei lesen und schreiben kann.

## Schritt 2: Öffnen Sie das PDF-Dokument

Nachdem der Pfad festgelegt ist, können Sie nun das zu konvertierende PDF-Dokument öffnen. Aspose.PDF für .NET erleichtert das Laden eines Dokuments zur weiteren Verarbeitung.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Hier,`PageToTIFF.pdf` ist die Beispieldatei. Sie können sie durch eine beliebige PDF-Datei Ihrer Wahl ersetzen. Das Dokumentobjekt enthält jetzt das PDF zur weiteren Bearbeitung.

## Schritt 3: Ausgabepfade für Bilder definieren

Als Nächstes geben Sie die Ausgabepfade für die generierten TIFF-Dateien an, einschließlich des Standard-TIFF und der binären Version.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Durch die Trennung dieser Pfade erhalten Sie eine Datei für die Standard-TIFF-Konvertierung und eine andere für das binäre Bild nach Anwendung des Bradley-Algorithmus.

## Schritt 4: Erstellen eines Auflösungsobjekts

Bei der Konvertierung von PDFs in TIFF spielt die Auflösung eine wichtige Rolle bei der Bestimmung der Bildqualität. Für unsere Zwecke stellen wir sie auf 300 DPI ein, um eine hochwertige Ausgabe zu gewährleisten.

```csharp
Resolution resolution = new Resolution(300);
```

Höhere DPI bedeuten eine bessere Bildschärfe, insbesondere bei Dokumenten, die gedruckt oder archiviert werden.

## Schritt 5: TIFF-Einstellungen konfigurieren

Als Nächstes müssen Sie die Einstellungen für das TIFF-Bild konfigurieren. Hier verwenden wir LZW-Komprimierung und stellen die Farbtiefe auf 1bpp (1 Bit pro Pixel) ein, um ein Binärbild zu erhalten.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Indem wir die Tiefe auf 1 bpp einstellen, bereiten wir das Bild für die binäre Ausgabe vor. Die LZW-Komprimierung wurde gewählt, weil sie die Dateigröße effizient reduziert, ohne an Qualität zu verlieren.

## Schritt 6: Erstellen Sie das TIFF-Gerät

Jetzt müssen Sie ein TIFF-Gerät erstellen, das die Konvertierung durchführt. Dieses Gerät verwendet die zuvor definierte Auflösung und TIFF-Einstellungen.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Das TIFF-Gerät ist das Herzstück dieses Vorgangs. Es nimmt das PDF-Dokument und konvertiert jede Seite basierend auf Ihren vordefinierten Einstellungen in ein TIFF-Bild.

## Schritt 7: Konvertieren Sie die PDF-Seite in TIFF

 Es ist Zeit, das PDF zu verarbeiten und die erste Seite in ein TIFF-Bild umzuwandeln.`Process` Mit dieser Methode können Sie bestimmte Seiten oder das gesamte Dokument konvertieren. In diesem Beispiel konvertieren wir die erste Seite.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Sobald die Methode abgeschlossen ist, wird ein TIFF-Bild am zuvor definierten Speicherort gespeichert.

## Schritt 8: Den Bradley-Binarisierungsalgorithmus anwenden

Jetzt kommt die Magie – der Bradley-Algorithmus! Dieser Algorithmus konvertiert das Graustufen-TIFF-Bild in ein Binärbild und optimiert es für Dokumentenerkennungssysteme.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 Die Methode BinarizeBradley verwendet zwei Dateiströme (Eingabe und Ausgabe) sowie einen Schwellenwert (hier`0.1`), das den Binärisierungsgrad bestimmt. Nach der Ausführung haben Sie ein perfekt binärisiertes Bild, das zur Verwendung bereit ist.

## Schritt 9: Erfolgreiche Konvertierung bestätigen

Abschließend empfiehlt es sich, den Benutzer darüber zu informieren, dass der Vorgang erfolgreich war. Dies können Sie mit einer einfachen Konsolenausgabe tun.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Sobald dies gedruckt ist, wissen Sie, dass Ihre PDF-Seite erfolgreich in ein binäres TIFF-Bild konvertiert wurde!

## Abschluss

Da haben Sie es! Sie haben gerade gelernt, wie Sie eine PDF-Seite in ein TIFF-Bild konvertieren und den Bradley-Binarisierungsalgorithmus mit Aspose.PDF für .NET anwenden. Dieser Prozess ist für die Dokumentenarchivierung, die optische Zeichenerkennung (OCR) und andere professionelle Anwendungen unerlässlich. Mit hochwertiger Auflösung und effizienter Komprimierung können Sie sicherstellen, dass Ihre Dokumentbilder sowohl klar als auch handlich groß sind.

## Häufig gestellte Fragen

### Was ist der Bradley-Algorithmus?
Der Bradley-Algorithmus ist eine Binärisierungstechnik, die Graustufenbilder in Binärbilder (Schwarzweiß) umwandelt, indem für jedes Pixel auf Grundlage seiner Umgebung ein adaptiver Schwellenwert bestimmt wird.

### Kann ich mit dieser Methode mehrere PDF-Seiten in TIFF konvertieren?
 Ja, Sie können die`Process` Methode zum Konvertieren aller Seiten durch Durchlaufen der Seiten im Dokument.

### Was ist die optimale Auflösung für die Konvertierung von PDFs in TIFF?
Für qualitativ hochwertige Bilder werden im Allgemeinen 300 DPI empfohlen. Sie können diesen Wert jedoch Ihren Anforderungen entsprechend anpassen.

### Was bedeutet 1bpp in der Farbtiefe?
1bpp (1 Bit pro Pixel) bedeutet, dass das Bild schwarzweiß ist und jedes Pixel entweder vollständig schwarz oder vollständig weiß ist.

### Ist der Bradley-Algorithmus für OCR geeignet?
Ja, der Bradley-Algorithmus wird häufig in der OCR-Vorverarbeitung verwendet, da er den Textkontrast in gescannten Dokumenten verbessert.