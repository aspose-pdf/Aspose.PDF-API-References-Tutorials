---
title: Bilder aus PDF-Datei extrahieren
linktitle: Bilder aus PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Extrahieren Sie mit Aspose.PDF für .NET ganz einfach Bilder aus PDF-Dateien.
type: docs
weight: 120
url: /de/net/programming-with-images/extract-images/
---
Diese Anleitung führt Sie Schritt für Schritt durch das Extrahieren von Bildern aus PDF-Dateien mit Aspose.PDF für .NET. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Dokumentverzeichnis festlegen

Stellen Sie vor dem Start sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Verwenden Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Schritt 3: Ein bestimmtes Bild extrahieren

In diesem Schritt extrahieren wir ein bestimmtes Bild von einer bestimmten Seite. Verwenden Sie die`Images` Sammlung der Seite`s `Resources‘-Objekt, um auf das gewünschte Bild zuzugreifen. Im folgenden Beispiel extrahieren wir das Bild mit dem Index 1 von der ersten Seite.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Schritt 4: Speichern Sie das extrahierte Bild

 Speichern Sie das extrahierte Bild in einer Datei mit dem`Save` Methode der`xImage` Objekt. Geben Sie den Ausgabepfad und das Bildformat an (in diesem Beispiel verwenden wir das JPEG-Format).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Schritt 5: Speichern Sie die aktualisierte PDF-Datei

 Speichern Sie die aktualisierte PDF-Datei mit dem`Save` Methode der`pdfDocument` Objekt. Geben Sie den Ausgabepfad für die PDF-Datei an.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Beispiel-Quellcode zum Extrahieren von Bildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extrahieren eines bestimmten Bildes
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Ausgabebild speichern
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Aktualisierte PDF-Datei speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder aus einer PDF-Datei extrahiert. Das extrahierte Bild wird im angegebenen Verzeichnis gespeichert und die aktualisierte PDF-Datei wird ebenfalls gespeichert. Sie können diese Dateien jetzt für Ihre spezifischen Anforderungen verwenden.

### FAQs zum Extrahieren von Bildern aus PDF-Dateien

#### F: Warum sollte ich mit Aspose.PDF für .NET Bilder aus einer PDF-Datei extrahieren wollen?

A: Das Extrahieren von Bildern aus einer PDF-Datei kann für verschiedene Zwecke nützlich sein, beispielsweise zum Archivieren, zur Wiederverwendung von Bildern in anderen Dokumenten, zum Analysieren von Inhalten oder zum Durchführen von Bildverarbeitungsaufgaben.

#### F: Wie erleichtert Aspose.PDF für .NET das Extrahieren von Bildern aus einem PDF-Dokument?

A: Aspose.PDF für .NET bietet einen schrittweisen Prozess zum Öffnen eines PDF-Dokuments, zum Zugriff auf bestimmte Bilder und zum Speichern dieser in Bilddateien in verschiedenen Formaten.

####  F: Welche Rolle spielt der`Document` class in Aspose.PDF for .NET play in image extraction?

 A: Die`Document` Die Klasse wird zum Laden und Bearbeiten von PDF-Dokumenten verwendet. In diesem Zusammenhang hilft sie beim Öffnen des PDF-Dokuments, aus dem Bilder extrahiert werden.

#### F: Wie gebe ich das bestimmte Bild an, das ich aus einer PDF-Seite extrahieren möchte?

 A: Sie können die`Images` Sammlung der Seite`Resources` Objekt, um über den Index auf das gewünschte Bild zuzugreifen. Beispiel:`pdfDocument.Pages[1].Resources.Images[1]` greift auf das erste Bild auf der ersten Seite zu.

#### F: Kann ich Bilder von jeder Seite im PDF-Dokument extrahieren?

A: Ja, Sie können Bilder von jeder Seite im PDF-Dokument extrahieren, indem Sie den gewünschten Seitenindex und den Index des zu extrahierenden Bildes angeben.

#### F: In welchen Bildformaten kann ich die extrahierten Bilder speichern?

 A: Sie können die extrahierten Bilder in verschiedenen Formaten speichern, die vom`ImageFormat` Aufzählung, wie JPEG, PNG, BMP und mehr.

#### F: Wie kann ich die extrahierten Bilder verwenden, nachdem ich sie als Dateien gespeichert habe?

A: Die extrahierten Bilder können wie alle anderen Bilddateien verwendet werden. Sie können sie anzeigen, bearbeiten, freigeben oder in andere Dokumente oder Projekte integrieren.

#### F: Hat das Extrahieren von Bildern aus einer PDF-Datei Auswirkungen auf das Layout oder den Inhalt des ursprünglichen PDF-Dokuments?

A: Nein, das Extrahieren von Bildern aus einer PDF-Datei hat keine Auswirkungen auf das Layout oder den Inhalt des ursprünglichen PDF-Dokuments. Nur die extrahierten Bilder sind betroffen.

#### F: Kann ich in einem einzigen Vorgang mehrere Bilder von verschiedenen Seiten extrahieren?

A: Ja, Sie können denselben Vorgang verwenden, um Bilder aus mehreren Seiten zu extrahieren, indem Sie verschiedene Seitenindizes durchlaufen.