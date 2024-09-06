---
title: Bildplatzierungen
linktitle: Bildplatzierungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Bilder in ein PDF-Dokument einfügen.
type: docs
weight: 170
url: /de/net/programming-with-images/image-placements/
---
In diesem Tutorial verwenden wir die Aspose.PDF-Bibliothek für .NET, um mit PDF-Dokumenten zu arbeiten und Operationen an Bildern durchzuführen. Wir laden ein PDF-Dokument, extrahieren die Bildplatzierungsinformationen und rufen die Bilder mit sichtbaren Abmessungen ab.

## Schritt 1: Einrichten der Umgebung
Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung wie folgt eingerichtet haben:
- Aspose.PDF für .NET auf Ihrem Computer installiert.
- AC#-Projekt einsatzbereit.

## Schritt 2: Laden des PDF-Dokuments
Zu Beginn müssen wir das PDF-Dokument laden, das wir verarbeiten möchten. Stellen Sie sicher, dass Sie den richtigen Pfad zum Verzeichnis haben, das das PDF-Dokument enthält.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Laden Sie das PDF-Quelldokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENTS DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis, das die PDF-Datei enthält.

## Schritt 3: Platzierungsinformationen aus Bildern extrahieren
 Nachdem wir nun das PDF-Dokument geladen haben, können wir die Platzierungsinformationen aus den Bildern extrahieren. Wir verwenden`ImagePlacementAbsorber`um Bildstellen von der ersten Seite des Dokuments aufzunehmen.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Den Inhalt der ersten Seite laden
doc.Pages[1].Accept(abs);
```

Wir haben jetzt die Bildplatzierungsinformationen aus der ersten Seite des Dokuments extrahiert.

## Schritt 4: Abrufen von Bildern mit sichtbaren Abmessungen
Nun rufen wir die Bilder mit ihren sichtbaren Abmessungen aus den Platzierungsinformationen ab, die wir zuvor extrahiert haben.

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     // Abrufen von Bildeigenschaften
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

In dieser Schleife rufen wir die Eigenschaften jedes Bildes ab, wie Breite, Höhe, X- und Y-Koordinaten der unteren linken Ecke sowie horizontale und vertikale Auflösung. Anschließend rufen wir jedes Bild mit seinen sichtbaren Abmessungen anhand der Platzierungsinformationen ab.

### Beispiel-Quellcode für Bildplatzierungen mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Laden Sie das PDF-Quelldokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Inhalt der ersten Seite laden
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Abrufen von Bildeigenschaften
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
		// Abrufen eines Bilds aus Ressourcen
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//Bitmap mit tatsächlichen Abmessungen erstellen
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## Abschluss
Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.PDF für .NET Bildplatzierungen in einem PDF-Dokument vornehmen. Wir haben den bereitgestellten C#-Quellcode erläutert, mit dem Sie ein PDF-Dokument laden, die Platzierungsinformationen aus den Bildern extrahieren und die Bilder mit sichtbaren Abmessungen abrufen können. Experimentieren Sie ruhig weiter mit Aspose.PDF, um die vielen anderen Funktionen zu erkunden.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Extrahierens von Bildplatzierungsinformationen aus einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Extrahieren von Bildplatzierungsinformationen können Sie die Positionierung, Abmessungen und Auflösung von Bildern in einem PDF-Dokument abrufen. Diese Informationen sind für eine präzise Bildbearbeitung und -analyse unerlässlich.

#### F: Wie erleichtert Aspose.PDF für .NET die Extraktion von Bildplatzierungsinformationen aus einem PDF-Dokument?

 A: Aspose.PDF für .NET bietet die`ImagePlacementAbsorber`Klasse, die verwendet werden kann, um Bildplatzierungsdetails aus einem PDF-Dokument zu übernehmen. Der bereitgestellte Code zeigt, wie diese Klasse zum Abrufen von Bildplatzierungsinformationen verwendet wird.

#### F: Wofür können Bildplatzierungsinformationen in realen Szenarien verwendet werden?

A: Informationen zur Bildplatzierung sind wertvoll für Aufgaben wie die Gewährleistung einer genauen Bildausrichtung, das Berechnen von Bildabmessungen, das Überprüfen der Bildqualität und das Erstellen von Berichten zur Bildverwendung in einem PDF-Dokument.

#### F: Wie gewährleistet das Codebeispiel eine genaue Extraktion der Bildplatzierungsinformationen?

 A: Das Codebeispiel verwendet die`ImagePlacementAbsorber` Klasse, um den Inhalt einer angegebenen Seite zu durchlaufen, Bildplatzierungen zu identifizieren und ihre Attribute wie Breite, Höhe, Koordinaten und Auflösung abzurufen.

#### F: Kann der Code erweitert werden, um Bilder über mehrere Seiten oder Dokumente hinweg zu verarbeiten?

A: Ja, der Code kann durch Durchlaufen mehrerer Seiten oder Dokumente erweitert werden, um Informationen zur Bildplatzierung zu extrahieren und bildbezogene Aufgaben auszuführen.

#### F: Wie ruft der Code Bilder mit ihren sichtbaren Abmessungen basierend auf den Platzierungsinformationen ab?

A: Das Codebeispiel extrahiert die Bilddaten aus den Ressourcen, erstellt ein Bitmap-Bild mit den tatsächlichen Abmessungen und stellt Eigenschaften wie Breite, Höhe, Koordinaten und Auflösung bereit.

#### F: Ist dieser Ansatz für große PDF-Dokumente mit zahlreichen Bildern effizient?

A: Ja, Aspose.PDF für .NET ist auf Leistung und Ressourcennutzung optimiert. Es extrahiert Bildplatzierungsinformationen effizient sogar aus großen PDF-Dokumenten.

#### F: Welchen Nutzen können Entwickler aus dem Verständnis und der Nutzung von Informationen zur Bildplatzierung ziehen?

A: Entwickler können eine präzise Bildbearbeitung, Ausrichtung und Analyse in PDF-Dokumenten sicherstellen. Mit diesen Informationen können sie Anwendungen für die Bildverarbeitung, Berichterstellung und Qualitätssicherung erstellen.

#### F: Kann der Code angepasst werden, um zusätzliche bildbezogene Attribute oder Metadaten zu extrahieren?

A: Auf jeden Fall. Der Code kann erweitert werden, um zusätzliche Attribute wie Bildtyp, Farbraum, Komprimierung und mehr zu extrahieren, indem entsprechende Klassen und Methoden von Aspose.PDF für .NET verwendet werden.

#### F: Welche Bedeutung hat die Schlussfolgerung dieses Tutorials?

A: Die Schlussfolgerung fasst den Inhalt des Tutorials zusammen und ermutigt zur weiteren Erkundung von Aspose.PDF für .NET, um seine Fähigkeiten über die Bildplatzierung hinaus zu nutzen und Türen für verschiedene PDF-bezogene Aufgaben zu öffnen.