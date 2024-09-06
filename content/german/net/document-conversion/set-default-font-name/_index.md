---
title: Standard-Schriftartnamen festlegen
linktitle: Standard-Schriftartnamen festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Rendern von PDFs in Bilder mit Aspose.PDF für .NET einen Standardschriftnamen festlegen. Dieses Handbuch enthält Voraussetzungen, schrittweise Anleitungen und häufig gestellte Fragen.
type: docs
weight: 270
url: /de/net/document-conversion/set-default-font-name/
---
## Einführung

Haben Sie schon einmal versucht, ein PDF-Dokument in ein Bild umzuwandeln, aber festgestellt, dass die Schriftarten einfach nicht richtig aussehen? Vielleicht erscheint der Text verzerrt oder die Originalschriftart wird nicht unterstützt. Hier kann das Festlegen einer Standardschriftart die Lösung sein! Mit Aspose.PDF für .NET können Sie ganz einfach eine Standardschriftart für Ihr PDF-Rendering festlegen und so sicherstellen, dass Ihr Dokument klar und professionell aussieht. In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie den Standardschriftnamen festlegen, wenn Sie ein PDF in ein Bild umwandeln. Am Ende dieses Handbuchs verfügen Sie über die Fähigkeiten, alle Herausforderungen beim PDF-Rendering zu meistern, die auf Sie zukommen. Bereit? Dann legen wir los!

## Voraussetzungen

Bevor wir uns in den Code stürzen, müssen Sie ein paar Dinge vorbereitet haben:

- Aspose.PDF für .NET: Diese leistungsstarke Bibliothek verwenden wir zur Bearbeitung unseres PDF-Dokuments. Sie können sie von der[Aspose-Website](https://releases.aspose.com/pdf/net/).
- Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Dies wird unsere Entwicklungsumgebung sein.
- .NET Framework: Stellen Sie sicher, dass Sie das .NET Framework installiert haben. Aspose.PDF für .NET unterstützt verschiedene Versionen. Überprüfen Sie daher die Dokumentation, um sie Ihren Anforderungen anzupassen.
- Ein PDF-Dokument: Sie benötigen ein Beispiel-PDF-Dokument zum Arbeiten. Wenn Sie keins haben, erstellen Sie ein einfaches PDF oder laden Sie ein Beispiel online herunter.

Sobald Sie alles eingerichtet haben, können wir mit der Codierung beginnen!

## Pakete importieren

Bevor wir uns in den Code vertiefen, müssen unbedingt die erforderlichen Pakete importiert werden. Dadurch wird sichergestellt, dass wir Zugriff auf alle Klassen und Methoden haben, die wir für unser Projekt benötigen.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Diese Importe sind von entscheidender Bedeutung, da sie die erforderlichen Namespaces für die Handhabung der PDF-Bearbeitung, Bildwiedergabe und Dateistream-Operationen bereitstellen.

## Schritt 1: Richten Sie Ihr Projekt und Ihren Dokumentpfad ein

Als Erstes richten wir den Verzeichnispfad ein, in dem sich Ihr PDF-Dokument befindet. Dies ist Ihr Ausgangspunkt für die Bearbeitung der PDF-Datei.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Hier,`dataDir` ist das Verzeichnis, in dem sich Ihr PDF-Dokument befindet. Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokument. Dies ist wichtig, da der Code wissen muss, woher die PDF-Datei abgerufen werden soll.

## Schritt 2: Laden Sie das PDF-Dokument

Nachdem wir nun den Dokumentpfad haben, besteht der nächste Schritt darin, das PDF-Dokument in den Speicher zu laden, damit wir mit der Arbeit daran beginnen können.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Wir verwenden die`Document` Klasse aus der Aspose.PDF-Bibliothek, um unsere PDF-Datei zu laden. Diese Klasse bietet verschiedene Methoden und Eigenschaften zum Arbeiten mit dem PDF-Dokument. Die`"input.pdf"` sollte durch den tatsächlichen Dateinamen Ihrer PDF-Datei ersetzt werden. Diese Datei wird als Eingabe für das Rendering verwendet.

## Schritt 3: Erstellen Sie einen Bildstream für die Ausgabe

Sobald das Dokument geladen ist, müssen wir einen Stream einrichten, um das gerenderte Bild zu speichern. Hier wird das Ausgabebild gespeichert.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 Der`FileStream`Klasse wird verwendet, um eine neue Datei zu erstellen, in der das gerenderte Bild gespeichert wird. In diesem Beispiel speichern wir das Bild als`"SetDefaultFontName.png"` . Der`FileMode.Create` sorgt dafür, dass eine neue Datei erstellt oder eine bestehende Datei überschrieben wird.

## Schritt 4: Stellen Sie die Auflösung für das Bild ein

Bevor Sie das PDF in ein Bild umwandeln, müssen Sie unbedingt die Auflösung festlegen. Diese bestimmt die Qualität und Klarheit des Ausgabebilds.

```csharp
Resolution resolution = new Resolution(300);
```
 Der`Resolution` Die Klasse legt die Auflösung des Ausgabebildes fest. Hier haben wir eine Auflösung von 300 DPI (dots per inch) gewählt, was der Standard für qualitativ hochwertige Bilder ist. Dadurch wird sichergestellt, dass Text und Grafiken in Ihrer PDF-Datei klar und ohne Detailverlust wiedergegeben werden.

## Schritt 5: Konfigurieren Sie das PNG-Gerät

Als Nächstes müssen wir das Gerät konfigurieren, das die Konvertierung des PDF in ein PNG-Bild übernimmt.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 Der`PngDevice` Klasse ist für die Darstellung des PDF-Dokuments in ein PNG-Bild verantwortlich. Durch Übergabe der`resolution` Wenn Sie dem nicht zustimmen, stellen wir sicher, dass das Bild mit der angegebenen DPI erstellt wird.

## Schritt 6: Legen Sie den Standardschriftnamen fest

Hier kommt der kritische Teil – das Festlegen des Standardschriftnamens. Dies ist die Ersatzschriftart, falls die Originalschriftart im PDF nicht verfügbar ist.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Wir erstellen eine Instanz von`RenderingOptions` und setzen Sie seine`DefaultFontName` Eigentum an`"Arial"`. Das bedeutet, dass Arial verwendet wird, wenn die Originalschriftart im PDF nicht gefunden werden kann. Dieser Schritt ist entscheidend, um die Lesbarkeit und das Erscheinungsbild des Textes im gerenderten Bild beizubehalten.

## Schritt 7: Rendern Sie die PDF-Seite in ein Bild

Nachdem alles eingerichtet ist, können wir nun die erste Seite des PDF-Dokuments in ein Bild umwandeln und es mit dem zuvor erstellten Dateistream speichern.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 Der`Process` Methode der`PngDevice` Die Klasse wird verwendet, um die angegebene PDF-Seite (in diesem Fall die erste Seite) in ein Bild umzuwandeln. Die Ausgabe wird dann im`imageStream`Dieser Schritt konvertiert die PDF-Seite in ein PNG-Bild mit der angegebenen Auflösung und Standardschriftart.

## Schritt 8: Schließen Sie den Dateistream und das PDF-Dokument

Nach dem Rendern des Bildes müssen der Dateistream und das PDF-Dokument unbedingt geschlossen werden, um Ressourcen freizugeben.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Schließen der`imageStream` stellt sicher, dass die Datei ordnungsgemäß gespeichert wird und keine Daten verloren gehen.`pdfDocument` gibt Speicher und Ressourcen frei und verhindert so mögliche Speicherlecks.

## Abschluss

Und da haben Sie es! Mit nur wenigen Codezeilen haben Sie gelernt, wie Sie beim Rendern einer PDF-Datei in ein Bild mit Aspose.PDF für .NET einen Standardschriftnamen festlegen. Diese Fähigkeit ist unglaublich praktisch, insbesondere beim Umgang mit PDF-Dateien, die möglicherweise nicht unterstützte Schriftarten enthalten. Indem Sie eine Standardschriftart festlegen, stellen Sie sicher, dass Ihre gerenderten Bilder ihre Lesbarkeit und ihr professionelles Erscheinungsbild behalten.

## Häufig gestellte Fragen

### Was passiert, wenn die angegebene Standardschriftart nicht auf dem System installiert ist?
 Wenn die Standardschriftart in der`RenderingOptions` nicht auf dem System installiert ist, verwendet Aspose.PDF eine systemdefinierte Ersatzschriftart.

### Kann ich andere Schriftarten als Arial als Standardschriftart verwenden?
Auf jeden Fall! Sie können jede auf Ihrem System installierte Schriftart als Standardschriftart festlegen.

### Ist es möglich, mehrere Seiten einer PDF-Datei in einem Durchgang in Bilder umzuwandeln?
Ja, Sie können die Seiten Ihrer PDF-Datei durchlaufen und jede Seite mit demselben Vorgang einzeln rendern.

### Beeinträchtigt das Einstellen einer hohen Auflösung die Leistung der PDF-Wiedergabe?
Ja, höhere Auflösungen führen zu größeren Bilddateien und können die Renderzeit verlängern, erzeugen aber auch klarere Bilder.

### Kann ich das PDF in andere Bildformate als PNG rendern?
Ja, Aspose.PDF unterstützt das Rendern in verschiedene Bildformate wie JPEG, BMP und TIFF.