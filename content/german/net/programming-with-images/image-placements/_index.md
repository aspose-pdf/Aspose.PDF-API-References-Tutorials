---
title: Bildplatzierungen
linktitle: Bildplatzierungen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Bildplatzierungen in PDF-Dokumenten extrahieren und bearbeiten. Schritt-für-Schritt-Anleitung mit Beispielen und Codeausschnitten.
type: docs
weight: 170
url: /de/net/programming-with-images/image-placements/
---
## Einführung

Das Arbeiten mit Bildern in PDF-Dateien kann schwierig sein, aber mit Aspose.PDF für .NET können Sie Bildeigenschaften ganz einfach bearbeiten und extrahieren. Egal, ob Sie Bildabmessungen ermitteln, diese extrahieren oder andere Eigenschaften wie die Auflösung abrufen möchten, Aspose.PDF bietet die Tools, die Sie benötigen. Dieses Tutorial führt Sie Schritt für Schritt durch das Extrahieren von Bildplatzierungen in einem PDF-Dokument mit Aspose.PDF für .NET. Wir behandeln alles vom Importieren von Paketen bis zum Abrufen von Bildeigenschaften wie Breite, Höhe und Auflösung.

## Voraussetzungen

Bevor wir mit dem Tutorial beginnen, müssen Sie einige Dinge vorbereitet haben. Hier ist eine kurze Checkliste:

1.  Aspose.PDF für .NET: Stellen Sie sicher, dass Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie herunterladen[Hier](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Sie müssen Visual Studio oder eine andere .NET-unterstützte IDE auf Ihrem Computer installiert haben.
3. Ein PDF-Dokument: Halten Sie ein Beispiel-PDF-Dokument bereit, das Bilder enthält. Für dieses Beispiel verwenden wir eine Datei namens`ImagePlacement.pdf`.
4. Grundlegende C#-Kenntnisse: Dieses Handbuch ist zwar anfängerfreundlich, grundlegende C#-Kenntnisse helfen Ihnen jedoch dabei, die Codeausschnitte besser zu verstehen.

## Pakete importieren

Bevor wir uns mit den Einzelheiten des Codes befassen, müssen Sie zunächst die erforderlichen Namespaces importieren. Diese Pakete sind für die Arbeit mit PDF-Dokumenten und die Bildbearbeitung in Aspose.PDF für .NET von entscheidender Bedeutung.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Mit diesen Paketen können Sie mit PDFs arbeiten (`Aspose.Pdf`), Bildplatzierungen manipulieren (`Aspose.Pdf.ImagePlacement`) und zur Verarbeitung von Bild-Streams und Grafiken (`System.Drawing` Und`System.IO`).

Nachdem wir nun die Voraussetzungen und Pakete bereitgestellt haben, wollen wir jeden Teil des Tutorials in einer einfachen, leicht verständlichen Anleitung aufschlüsseln.

## Schritt 1: Laden Sie das PDF-Dokument

Der erste Schritt besteht darin, das PDF-Dokument in Ihr Projekt zu laden. Dies bildet die Grundlage für die Arbeit mit Bildern in der PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 In diesem Schritt definieren wir den Dateipfad des PDF-Dokuments mit`dataDir`und anschließendes Erstellen einer neuen Instanz des`Aspose.Pdf.Document` Klasse. Dadurch können wir die PDF-Datei in unser Programm laden. Einfach, oder? Genau wie beim Öffnen eines Buches zum Lesen sind wir nun bereit, den Inhalt zu erkunden.

## Schritt 2: Initialisieren Sie den Image Placement Absorber

Zum Extrahieren der Bilder benötigen wir einen sogenannten „Image Placement Absorber“. Stellen Sie sich das wie ein Tool vor, das alle Bildinformationen auf einer bestimmten Seite aufnimmt.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Hier erstellen wir eine Instanz von`ImagePlacementAbsorber`. Dieses Objekt sammelt und speichert Informationen über alle Bildplatzierungen auf einer bestimmten PDF-Seite. Stellen Sie es sich so vor, als würden Sie eine Seite mit einer Lupe scannen und alle Bilder darauf identifizieren!

## Schritt 3: Akzeptieren Sie den Absorber auf der ersten Seite

Als nächstes müssen wir dem Absorber mitteilen, welche Seite der PDF-Datei gescannt werden soll. In diesem Beispiel konzentrieren wir uns auf die erste Seite.

```csharp
doc.Pages[1].Accept(abs);
```

 Der`Accept` Methode durchsucht die erste Seite des PDF-Dokuments nach Bildern und speichert die Ergebnisse im`ImagePlacementAbsorber`Es ist, als würde man der Lupe sagen, wo sie nach Bildern suchen soll.

## Schritt 4: Durchlaufen Sie jede Bildplatzierung

Nachdem wir die Seite gescannt haben, müssen wir jedes auf der Seite gefundene Bild durchlaufen und seine Eigenschaften abrufen.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Diese Schleife durchläuft jedes Bild auf der Seite. Wir drucken die Breite, Höhe, das untere linke x (LLX), das untere linke y (LLY) und die Auflösung des Bildes (sowohl horizontal als auch vertikal) aus. Diese Details helfen Ihnen, die Größe und Positionierung jedes Bildes im PDF zu verstehen.

## Schritt 5: Extrahieren Sie das Bild mit sichtbaren Abmessungen

Nachdem Sie Informationen zu den Bildern gesammelt haben, möchten Sie möglicherweise das eigentliche Bild mit seinen Abmessungen extrahieren. So können Sie das tun.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Dieser Codeausschnitt ruft das Bild aus dem PDF ab und skaliert es auf seine tatsächlichen Abmessungen, wie in der`ImagePlacement` Objekt. Indem Sie das Bild in einem Speicherstream speichern und skalieren, stellen Sie sicher, dass das extrahierte Bild genau die Größe beibehält, in der es in der PDF-Datei angezeigt wurde.

## Abschluss

Das Extrahieren von Bildplatzierungen aus einem PDF-Dokument mit Aspose.PDF für .NET ist ziemlich unkompliziert, wenn man es Schritt für Schritt aufschlüsselt. Wir haben alles abgedeckt, vom Laden einer PDF-Datei über das Abrufen von Bildeigenschaften bis hin zum Extrahieren von Bildern mit ihren tatsächlichen Abmessungen. Aspose.PDF macht das Arbeiten mit PDFs und das Bearbeiten von Inhalten unglaublich einfach und ermöglicht Ihnen, effizient mit Bildern, Text und vielem mehr zu arbeiten.

## Häufig gestellte Fragen

### Kann ich Bilder aus einer bestimmten Seite des PDF extrahieren?  
 Ja, durch Angabe der Seitenzahl bei Verwendung des`Accept` Methode können Sie sich auf eine bestimmte Seite konzentrieren.

### Welche Bildformate werden für die Extraktion unterstützt?  
Aspose.PDF unterstützt verschiedene Formate, darunter PNG, JPEG, BMP und mehr.

### Ist es möglich, das extrahierte Bild zu manipulieren?  
 Absolut! Nach dem Extrahieren können Sie die`System.Drawing` Namespace zum Bearbeiten des Bildes.

### Kann ich Bilder aus passwortgeschützten PDFs extrahieren?  
Ja, das können Sie, aber Sie müssen die PDF-Datei mit den entsprechenden Anmeldeinformationen entsperren, bevor Sie die Bilder extrahieren.

### Funktioniert Aspose.PDF für .NET auf allen .NET-Frameworks?  
Ja, es unterstützt .NET Framework, .NET Core und .NET 5 und höher.