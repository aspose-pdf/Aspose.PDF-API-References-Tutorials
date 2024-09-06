---
title: Seitenbereich in DOM konvertieren
linktitle: Seitenbereich in DOM konvertieren
second_title: Aspose.PDF für .NET API-Referenz
description: Konvertieren Sie mit Aspose.PDF für .NET ganz einfach einen bestimmten Bereich einer PDF-Seite in ein Document Object Model (DOM).
type: docs
weight: 80
url: /de/net/programming-with-images/convert-page-region-to-dom/
---
Diese Anleitung führt Sie Schritt für Schritt durch die Konvertierung eines bestimmten Bereichs einer Seite in ein Document Object Model (DOM) mit Aspose.PDF für .NET. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Dokumentverzeichnis festlegen

Stellen Sie vor dem Start sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das Dokument

 In diesem Schritt öffnen wir das PDF-Dokument mit dem`Document` Klasse von Aspose.PDF. Verwenden Sie die`Document` Konstruktor und übergeben Sie den Pfad zum PDF-Dokument.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Schritt 3: Rechteck für Seitenbereich abrufen

 In diesem Schritt definieren wir ein Rechteck, das den spezifischen Bereich der Seite darstellt, den wir in DOM konvertieren möchten. Verwenden Sie die`Aspose.Pdf.Rectangle` Klasse, um die Koordinaten des Rechtecks zu definieren.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Schritt 4: Definieren Sie den Zuschneidebereich der Seite

 Verwenden Sie die`CropBox` Eigentum der`Page` Objekt, um den Zuschneiderahmen der Seite auf das gewünschte Rechteck einzustellen.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Schritt 5: Speichern Sie das zugeschnittene PDF-Dokument in einem Stream

 In diesem Schritt speichern wir das zugeschnittene PDF-Dokument in einem Stream mit dem`MemoryStream` Klasse.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Schritt 6: Öffnen Sie das zugeschnittene PDF-Dokument und konvertieren Sie es in ein Bild

 Öffnen Sie das zugeschnittene PDF-Dokument mit dem`Document`Klasse und konvertieren Sie sie in ein Bild. Wir verwenden eine Auflösung von 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Schritt 7: Konvertieren Sie die jeweilige Seite in ein Bild

 Konvertieren Sie die jeweilige Seite in ein Bild mit dem`Process` Methode der`pngDevice` Objekt. Geben Sie den Bildausgabepfad an.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Beispielquellcode zum Konvertieren von Seitenbereichen in DOM mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document( dataDir + "AddImage.pdf");
// Rechteck eines bestimmten Seitenbereichs abrufen
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Stellen Sie den CropBox-Wert entsprechend dem Rechteck des gewünschten Seitenbereichs ein
document.Pages[1].CropBox = pageRect;
// Beschnittenes Dokument im Stream speichern
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Zugeschnittenes PDF-Dokument öffnen und in ein Bild umwandeln
document = new Document(ms);
// Resolution-Objekt erstellen
Resolution resolution = new Resolution(300);
// PNG-Gerät mit angegebenen Attributen erstellen
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
// Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Abschluss

Herzlichen Glückwunsch! Sie haben einen bestimmten Bereich einer Seite erfolgreich mit Aspose.PDF für .NET in ein Document Object Model (DOM) konvertiert. Das resultierende Bild wird im angegebenen Verzeichnis gespeichert. Sie können dieses Bild jetzt in Ihren Projekten oder Anwendungen verwenden.

## Häufig gestellte Fragen

#### F: Was ist der Zweck der Konvertierung eines bestimmten Bereichs einer Seite in ein Document Object Model (DOM) mit Aspose.PDF für .NET?

A: Das Konvertieren eines bestimmten Bereichs einer PDF-Seite in ein Document Object Model (DOM) kann hilfreich sein, um einen bestimmten Inhaltsabschnitt innerhalb eines PDF-Dokuments zu extrahieren und zu bearbeiten.

#### F: Wie erleichtert Aspose.PDF für .NET die Konvertierung eines bestimmten Seitenbereichs in ein DOM?

A: Aspose.PDF für .NET bietet einen schrittweisen Prozess zum Definieren des gewünschten Seitenbereichs, Festlegen des Zuschneidebereichs, Speichern des zugeschnittenen PDF-Dokuments in einem Stream und Konvertieren des angegebenen Seitenbereichs in ein Bild.

#### F: Warum ist es wichtig, das Dokumentverzeichnis vor dem Start des Konvertierungsprozesses zu definieren?

A: Durch die Angabe des Dokumentverzeichnisses wird sichergestellt, dass das PDF-Dokument und das resultierende Bild korrekt im gewünschten Ausgabepfad liegen.

####  F: Wie funktioniert das`Document` class in Aspose.PDF for .NET help in the conversion process?

 A: Die`Document` Mit der Klasse können Sie PDF-Dokumente öffnen, bearbeiten und speichern. In diesem Fall wird sie verwendet, um das PDF-Dokument zu laden und eine zugeschnittene Version davon zu erstellen.

####  F: Was ist der Zweck der`Rectangle` class in the page region conversion process?

 A: Die`Rectangle`Die Klasse definiert die Koordinaten des bestimmten Bereichs auf der PDF-Seite, den Sie in ein DOM konvertieren möchten. Sie hilft dabei, den Zuschneidebereich genau anzugeben.

#### F: Wie wird der Zuschneidebereich der Seite im Konvertierungsprozess auf die gewünschte Region eingestellt?

 A: Die`CropBox` Eigentum der`Page` -Objekt wird verwendet, um den Zuschneidebereich der Seite auf das definierte Rechteck festzulegen, das die bestimmte Region darstellt.

#### F: Wie wird das zugeschnittene PDF-Dokument während des Konvertierungsvorgangs in einem Stream gespeichert?

 A: Das zugeschnittene PDF-Dokument wird in einem`MemoryStream` Objekt, das eine effiziente Bearbeitung des PDF-Inhalts ermöglicht.

####  F: Welche Rolle spielt der`PngDevice` class play in the page region to DOM conversion process?

 A: Die`PngDevice` Die Klasse unterstützt Sie bei der Konvertierung des zugeschnittenen PDF-Dokuments in ein Bildformat wie PNG, sodass Sie den spezifischen Seitenbereich visualisieren können.

#### F: Kann ich während des Konvertierungsvorgangs die Auflösung oder andere Attribute des resultierenden Bildes anpassen?

 A: Ja, Sie können die Auflösung und andere Attribute des resultierenden Bildes ändern, indem Sie die`PngDevice` Objekt vor der Konvertierung der Seite.