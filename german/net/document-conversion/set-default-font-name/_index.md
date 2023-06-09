---
title: Legen Sie den Standardschriftnamen fest
linktitle: Legen Sie den Standardschriftnamen fest
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen des Standardschriftnamens in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 270
url: /de/net/document-conversion/set-default-font-name/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET den Standardschriftnamen in einer PDF-Datei festlegen. Manchmal kann es beim Extrahieren von Bildern aus einer PDF-Datei zu Problemen mit fehlenden Schriftarten kommen. Durch die Angabe eines Standardschriftnamens können Sie sicherstellen, dass extrahierter Text korrekt angezeigt wird. Führen Sie die folgenden Schritte aus, um den Standardschriftnamen in einer PDF-Datei festzulegen.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Laden des PDF-Dokuments
 Der erste Schritt besteht darin, das PDF-Dokument in ein zu laden`Document` Objekt. Verwenden Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Code zum Hinzufügen
}
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Legen Sie den Standardschriftnamen fest
 Als Nächstes legen wir den Standardschriftnamen mithilfe von fest`DefaultFontName` Option der`RenderingOptions` Objekt. Verwenden Sie den folgenden Code:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Code zum Hinzufügen
     }
}
```

 Unbedingt ersetzen`"Arial"` mit dem gewünschten Schriftartnamen.

## Schritt 3: Bildextraktion
Als nächstes extrahieren wir das Bild von der angegebenen Seite des PDF-Dokuments. Verwenden Sie den folgenden Code:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Stellen Sie sicher, dass Sie die richtige Seitenzahl angeben`pdfDocument.Pages[1]`.

### Beispielquellcode für „Standardschriftnamen festlegen“ mit Aspose.PDF für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.PDF für .NET den Standardschriftnamen in einer PDF-Datei festlegt. Durch die Angabe eines Standardschriftnamens können Sie sicherstellen, dass extrahierter Text korrekt angezeigt wird. Verwenden Sie diese Methode, um Probleme mit fehlenden Schriftarten beim Extrahieren von Bildern aus PDF-Dateien zu beheben.