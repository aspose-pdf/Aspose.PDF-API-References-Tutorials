---
title: Seite zu PNG
linktitle: Seite zu PNG
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren einer Seite in das PNG-Format mit Aspose.PDF für .NET.
type: docs
weight: 220
url: /de/net/programming-with-images/page-to-png/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET eine Seite in das PNG-Format konvertieren. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Seite in PNG konvertieren

Als nächstes konvertieren wir eine bestimmte Seite des PDF-Dokuments in das PNG-Format. Verwenden Sie den folgenden Code:

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
// Erstellen Sie ein Resolution-Objekt
Resolution resolution = new Resolution(300);
// Erstellen Sie ein PNG-Gerät mit den angegebenen Attributen (Breite, Höhe, Auflösung).
PngDevice pngDevice = new PngDevice(resolution);
// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
pngDevice.Process(pdfDocument.Pages[1], imageStream);
// Schließen Sie den Stream
imageStream.Close();
}
```

Stellen Sie sicher, dass Sie den gewünschten Pfad und Dateinamen für das ausgegebene PNG-Bild angeben.

### Beispielquellcode für Page To PNG mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "PageToPNG.pdf");
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.png", FileMode.Create))
{
	// Auflösungsobjekt erstellen
	Resolution resolution = new Resolution(300);
	// Erstellen Sie ein PNG-Gerät mit angegebenen Attributen (Breite, Höhe, Auflösung).
	PngDevice pngDevice = new PngDevice(resolution);
	// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
	pngDevice.Process(pdfDocument.Pages[1], imageStream);
	// Stream schließen
	imageStream.Close();
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben eine Seite mit Aspose.PDF für .NET erfolgreich in das PNG-Format konvertiert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um bestimmte Seiten aus PDF-Dateien zu extrahieren und sie als PNG-Bilder zu speichern.