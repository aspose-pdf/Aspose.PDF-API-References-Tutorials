---
title: Konvertieren Sie alle Seiten in EMF
linktitle: Konvertieren Sie alle Seiten in EMF
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach alle Seiten eines PDF-Dokuments in EMF-Dateien.
type: docs
weight: 50
url: /de/net/programming-with-images/convert-all-pages-to-emf/
---

In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET alle Seiten eines PDF-Dokuments in EMF-Dateien (Enhanced Metafile) konvertieren. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit`Document` Klasse von Aspose.PDF. Benutzen Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToEMF.pdf");
```

## Schritt 3: Konvertieren Sie jede Seite in EMF

 In diesem Schritt gehen wir jede Seite des PDF-Dokuments durch und konvertieren sie in einzelne EMF-Dateien. Wir werden a verwenden`for`Schleife, um alle Seiten zu durchlaufen.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Erstellen Sie einen Stream, um das EMF-Bild zu speichern
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
     {
         // Erstellen Sie ein Resolution-Objekt
         Resolution resolution = new Resolution(300);
        
         // Erstellen Sie ein EMF-Gerät mit den angegebenen Attributen
         // Breite, Höhe, Auflösung
         EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
        
         // Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
         emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Schließen Sie den Stream
         imageStream.Close();
     }
}
```

### Beispielquellcode für „Alle Seiten in EMF konvertieren“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ConvertAllPagesToEMF.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".emf", FileMode.Create))
	{
		// Auflösungsobjekt erstellen
		Resolution resolution = new Resolution(300);
		// Erstellen Sie ein PNG-Gerät mit angegebenen Attributen
		// Breite, Höhe, Auflösung
		EmfDevice emfDevice = new EmfDevice(500, 700, resolution);
		// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
		emfDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Stream schließen
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to EMF successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben alle Seiten eines PDF-Dokuments mit Aspose.PDF für .NET erfolgreich in EMF-Dateien konvertiert. Einzelne EMF-Dateien werden im angegebenen Verzeichnis gespeichert. Sie können diese EMF-Dateien jetzt in Ihren Projekten oder Anwendungen verwenden.