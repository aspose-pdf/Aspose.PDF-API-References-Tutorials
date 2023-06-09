---
title: Konvertieren Sie alle Seiten in PNG
linktitle: Konvertieren Sie alle Seiten in PNG
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach alle Seiten eines PDF-Dokuments in PNG-Dateien.
type: docs
weight: 60
url: /de/net/programming-with-images/convert-all-pages-to-png/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET alle Seiten eines PDF-Dokuments in PNG-Dateien konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## Schritt 3: Konvertieren Sie jede Seite in PNG

 In diesem Schritt gehen wir jede Seite des PDF-Dokuments durch und konvertieren sie in einzelne PNG-Dateien. Wir werden a verwenden`for`Schleife, um alle Seiten zu durchlaufen.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //Erstellen Sie einen Stream, um das PNG-Bild zu speichern
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Erstellen Sie ein PNG-Gerät mit den angegebenen Attributen
         // Breite, Höhe, Auflösung, Qualität
         // Qualität [0-100], 100 ist das Maximum
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Schließen Sie den Stream
         imageStream.Close();
     }
}
```

### Beispielquellcode für „Alle Seiten in PNG konvertieren“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// Erstellen Sie ein PNG-Gerät mit angegebenen Attributen
		// Breite, Höhe, Auflösung, Qualität
		// Qualität [0-100], 100 ist das Maximum
		// Auflösungsobjekt erstellen
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Stream schließen
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben alle Seiten eines PDF-Dokuments mit Aspose.PDF für .NET erfolgreich in PNG-Dateien konvertiert. Einzelne PNG-Dateien werden im angegebenen Verzeichnis gespeichert. Sie können diese PNG-Dateien jetzt in Ihren Projekten oder Anwendungen verwenden.