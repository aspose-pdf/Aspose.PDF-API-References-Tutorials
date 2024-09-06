---
title: Suchen und Abrufen von Bildern in einer PDF-Datei
linktitle: Suchen und Abrufen von Bildern in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Suchen und Abrufen von Bildern in PDF-Dateien mit Aspose.PDF für .NET.
type: docs
weight: 260
url: /de/net/programming-with-images/search-and-get-images/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET Bilder in PDF-Dateien suchen und abrufen. Befolgen Sie diese Schritte, um diesen Vorgang problemlos durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können sie von der offiziellen Aspose-Website herunterladen.

## Schritt 1: Laden des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um das PDF-Dokument zu laden:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

Stellen Sie sicher, dass Sie den richtigen Pfad zu Ihrem PDF-Dokument angeben.

## Schritt 2: Bildspeicherorte suchen

Um nach den Speicherorten von Bildern im PDF-Dokument zu suchen, verwenden Sie den folgenden Code:

```csharp
// Erstellen Sie ein ImagePlacementAbsorber-Objekt zum Suchen nach Bildspeicherorten
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
     // Holen Sie sich das Bild mithilfe des ImagePlacement-Objekts
     XImage image = imagePlacement.Image;

     // Anzeigen der Bildspeicherorteigenschaften
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

Dadurch werden alle Bildspeicherorte durchsucht, passende Bilder abgerufen und deren Eigenschaften angezeigt.

### Beispielquellcode für „Suchen und Abrufen von Bildern“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
// Erstellen Sie ein ImagePlacementAbsorber-Objekt, um eine Bildplatzierungssuche durchzuführen
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
// Akzeptieren Sie den Absorber für alle Seiten
doc.Pages.Accept(abs);
// Durchlaufen Sie alle Bildplatzierungen, holen Sie sich Bild- und Bildplatzierungseigenschaften
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	// Holen Sie sich das Bild mit dem ImagePlacement-Objekt
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

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Bilder in einem PDF-Dokument gesucht und abgerufen. Jetzt können Sie diese Methode auf Ihre eigenen Projekte anwenden, um Bilder zu extrahieren und ihre Eigenschaften aus PDF-Dateien abzurufen.

### FAQs zum Suchen und Abrufen von Bildern in PDF-Dateien

#### F: Was ist der Zweck der Suche und des Abrufens von Bildern in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Durch das Suchen und Abrufen von Bildern in einem PDF-Dokument können Sie Bilder innerhalb der PDF-Datei lokalisieren und extrahieren. Dies kann für verschiedene Zwecke nützlich sein, beispielsweise zum Analysieren des Inhalts, Überprüfen der Bildeigenschaften oder zur Weiterverarbeitung der Bilder.

#### F: Wie funktioniert die Suche nach Bildern in einem PDF-Dokument?

 A: Der Prozess beinhaltet die Verwendung von`ImagePlacementAbsorber` Objekt, um eine Suche nach Bildplatzierungen auf allen Seiten des PDF-Dokuments durchzuführen. Der Absorber sammelt Informationen über die Position, Größe und Auflösung jedes Bilds im Dokument.

####  F: Was ist der Zweck der`ImagePlacement` object in the code?

 A: Die`ImagePlacement`Objekt stellt die Platzierung eines Bildes im PDF-Dokument dar. Es bietet Eigenschaften, mit denen Sie auf Details wie Abmessungen, Koordinaten und Auflösung des Bildes zugreifen können.

#### F: Kann ich die gesuchten und abgerufenen Bilder nach bestimmten Kriterien filtern?

A: Der bereitgestellte Code sammelt Informationen zu allen Bildern im PDF-Dokument. Wenn Sie Bilder nach bestimmten Kriterien filtern möchten (z. B. Bildtyp, Abmessungen, Auflösung), müssen Sie den Code möglicherweise ändern, um entsprechende Filterbedingungen einzuschließen.

#### F: Wie kann ich auf den eigentlichen Bildinhalt zugreifen, nachdem ich die Platzierungsinformationen erhalten habe?

 A: Die`XImage` Objekt erhalten aus dem`ImagePlacement` Objekt stellt den eigentlichen Bildinhalt dar. Sie können dieses Objekt`XImage` Objekt, beispielsweise durch Speichern in einer Datei oder Anzeigen in Ihrer Anwendung.

#### F: Was kann ich mit den erhaltenen Bildeigenschaften tun?

A: Die ermittelten Bildeigenschaften wie Breite, Höhe, Koordinaten und Auflösung können für verschiedene Zwecke genutzt werden. Sie können die Eigenschaften analysieren, dem Benutzer anzeigen oder als Eingabe für die weitere Verarbeitung verwenden.

#### F: Kann ich mit dieser Methode die Bilder im PDF-Dokument ändern oder bearbeiten?

A: Der bereitgestellte Code konzentriert sich auf die Suche und den Abruf von Informationen zur Bildplatzierung. Um Bilder zu ändern oder zu bearbeiten, müssen Sie möglicherweise zusätzliche Funktionen wie Bildbearbeitung mithilfe der Aspose.PDF-Bibliothek integrieren.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren?

A: Um diese Methode in Ihre Projekte zu integrieren, folgen Sie den beschriebenen Schritten und ändern Sie den Code nach Bedarf. Sie können die erhaltenen Bildplatzierungsinformationen und -eigenschaften entsprechend den Anforderungen Ihrer Anwendung verwenden.

#### F: Bietet Aspose.PDF für .NET andere Funktionen zur Bildbearbeitung in PDF-Dokumenten?

A: Ja, Aspose.PDF für .NET bietet eine Reihe von Funktionen für die Arbeit mit Bildern in PDF-Dokumenten, darunter Bildeinfügung, Größenänderung, Drehung, Extraktion und mehr. Sie können die Dokumentation und Beispiele der Bibliothek erkunden, um alle Funktionen kennenzulernen.