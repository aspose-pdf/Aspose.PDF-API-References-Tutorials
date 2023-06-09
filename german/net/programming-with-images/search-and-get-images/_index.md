---
title: Bilder suchen und abrufen
linktitle: Bilder suchen und abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Suchen und Abrufen von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 260
url: /de/net/programming-with-images/search-and-get-images/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Bilder in einem PDF-Dokument suchen und abrufen. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Bildspeicherorte suchen

Um die Speicherorte von Bildern im PDF-Dokument zu durchsuchen, verwenden Sie den folgenden Code:

```csharp
// Erstellen Sie ein ImagePlacementAbsorber-Objekt, um nach Bildpositionen zu suchen
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

// Akzeptieren Sie den Absorber für alle Seiten des Dokuments
doc.Pages.Accept(abs);
```

Dadurch werden die Positionen der Bilder im Absorber erfasst.

## Schritt 3: Durchsuchen Sie Bildspeicherorte und rufen Sie Bilder und ihre Eigenschaften ab

Als Nächstes durchsuchen wir die gesammelten Bildspeicherorte und rufen die Bilder und ihre Eigenschaften ab. Verwenden Sie den folgenden Code:

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //Rufen Sie das Bild mit dem ImagePlacement-Objekt ab
     XImage image = imagePlacement.Image;

     // Zeigen Sie die Eigenschaften des Bildstandorts an
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Dadurch werden alle Bildspeicherorte durchsucht, passende Bilder gefunden und deren Eigenschaften angezeigt.

### Beispielquellcode für „Bilder suchen und abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Erstellen Sie ein ImagePlacementAbsorber-Objekt, um eine Bildplatzierungssuche durchzuführen
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Akzeptieren Sie den Absorber für alle Seiten
doc.Pages.Accept(abs);
// Durchlaufen Sie alle ImagePlacements und rufen Sie Bild- und ImagePlacement-Eigenschaften ab
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Rufen Sie das Bild mit dem ImagePlacement-Objekt ab
	XImage image = imagePlacement.Image;
	// Bildplatzierungseigenschaften für alle Platzierungen anzeigen
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder in einem PDF-Dokument gesucht und abgerufen. Jetzt können Sie diese Methode auf Ihre eigenen Projekte anwenden, um Bilder zu extrahieren und deren Eigenschaften aus PDF-Dateien abzurufen.