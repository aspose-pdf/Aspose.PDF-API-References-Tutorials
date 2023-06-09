---
title: Bildplatzierungen
linktitle: Bildplatzierungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Bilder in einem PDF-Dokument platzieren.
type: docs
weight: 170
url: /de/net/programming-with-images/image-placements/
---

In diesem Tutorial verwenden wir die Aspose.PDF-Bibliothek für .NET, um mit PDF-Dokumenten zu arbeiten und Vorgänge an Bildern durchzuführen. Wir laden ein PDF-Dokument, extrahieren die Informationen zur Bildplatzierung und rufen die Bilder mit sichtbaren Abmessungen ab.

## Schritt 1: Einrichten der Umgebung
Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung wie folgt eingerichtet haben:
- Aspose.PDF für .NET ist auf Ihrem Computer installiert.
- AC#-Projekt zur Verwendung bereit.

## Schritt 2: Laden des PDF-Dokuments
Zunächst müssen wir das PDF-Dokument laden, das wir verarbeiten möchten. Stellen Sie sicher, dass Sie den richtigen Pfad zum Verzeichnis haben, das das PDF-Dokument enthält.

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie das Quell-PDF-Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Unbedingt ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis, das die PDF-Datei enthält.

## Schritt 3: Platzierungsinformationen aus Bildern extrahieren
 Nachdem wir nun das PDF-Dokument geladen haben, können wir die Platzierungsinformationen aus den Bildern extrahieren. Wir werden verwenden`ImagePlacementAbsorber`um Bildstellen von der ersten Seite des Dokuments zu übernehmen.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Laden Sie den Inhalt der ersten Seite
doc.Pages[1].Accept(abs);
```

Wir haben jetzt die Bildplatzierungsinformationen von der ersten Seite des Dokuments extrahiert.

## Schritt 4: Bilder mit sichtbaren Abmessungen abrufen
Jetzt rufen wir die Bilder mit ihren sichtbaren Abmessungen aus den zuvor extrahierten Platzierungsinformationen ab.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Bildeigenschaften abrufen
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     // Rufen Sie das Bild mit sichtbaren Abmessungen ab
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         // Holen Sie sich das Bild aus den Ressourcen
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         // Erstellen Sie ein Bild mit tatsächlichen Abmessungen
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

In dieser Schleife rufen wir die Eigenschaften jedes Bildes ab, z. B. Breite, Höhe, X- und Y-Koordinaten der unteren linken Ecke sowie horizontale und vertikale Auflösung. Anschließend rufen wir mithilfe der Platzierungsinformationen jedes Bild mit seinen sichtbaren Abmessungen ab.

### Beispielquellcode für Bildplatzierungen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das Quell-PDF-Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Laden Sie den Inhalt der ersten Seite
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Bildeigenschaften abrufen
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	// Bild mit sichtbaren Abmessungen abrufen
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		// Bild aus Ressourcen abrufen
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Erstellen Sie eine Bitmap mit tatsächlichen Abmessungen
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Abschluss
Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.PDF für .NET Bildplatzierungen in einem PDF-Dokument durchführen. Wir haben den bereitgestellten C#-Quellcode erklärt, der es Ihnen ermöglicht, ein PDF-Dokument zu laden, die Platzierungsinformationen aus den Bildern zu extrahieren und die Bilder mit sichtbaren Abmessungen abzurufen. Experimentieren Sie ruhig weiter mit Aspose.PDF, um die vielen anderen Funktionen zu erkunden.