---
title: Erstellen Sie Miniaturbilder
linktitle: Erstellen Sie Miniaturbilder
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Miniaturansichten von Bildern aus PDF-Dateien.
type: docs
weight: 100
url: /de/net/programming-with-images/create-thumbnail-images/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET Bildminiaturansichten aus PDF-Dateien erstellen. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, das Ihre PDF-Dateien enthält.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Rufen Sie die Namen aller PDF-Dateien in einem Verzeichnis ab

 In diesem Schritt rufen wir mithilfe von C# die Namen aller im angegebenen Verzeichnis vorhandenen PDF-Dateien ab`Directory`Klasse. Dateien werden in einem Array von Zeichenfolgen gespeichert.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Schritt 3: Durchsuchen Sie alle PDF-Dateien und ihre Seiten

 In diesem Schritt gehen wir alle PDF-Dateien und ihre Seiten durch, um Miniaturansichten der Bilder zu erstellen. Wir werden a verwenden`for` Schleife, um alle Dateien zu durchlaufen.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Öffnen Sie das PDF-Dokument
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Gehen Sie alle Seiten des Dokuments durch
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Erstellen Sie einen Stream, um das Miniaturbild zu speichern
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Erstellen Sie ein Resolution-Objekt
             Resolution resolution = new Resolution(300);
            
             // Erstellen Sie ein JPEG-Gerät mit den angegebenen Attributen
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Schließen Sie den Stream
             imageStream.Close();
         }
     }
}
```

### Beispielquellcode zum Erstellen von Miniaturbildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Rufen Sie die Namen aller PDF-Dateien in einem bestimmten Verzeichnis ab
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Durchlaufen Sie alle Dateieinträge im Array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Dokument öffnen
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Auflösungsobjekt erstellen
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, Auflösung, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Stream schließen
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Miniaturansichten von Bildern aus PDF-Dateien erstellt. Miniaturansichten der Bilder werden im angegebenen Verzeichnis gespeichert. Sie können diese Miniaturansichten nun verwenden, um eine visuelle Vorschau Ihrer PDF-Dateien anzuzeigen.