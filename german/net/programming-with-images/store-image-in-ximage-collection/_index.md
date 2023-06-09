---
title: Bild in der XImage-Sammlung speichern
linktitle: Bild in der XImage-Sammlung speichern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Speichern eines Bildes in der XImage-Sammlung mit Aspose.PDF für .NET.
type: docs
weight: 290
url: /de/net/programming-with-images/store-image-in-ximage-collection/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Bild in der XImage-Sammlung speichern. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Initialisierung des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument zu initialisieren:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Initialisieren Sie das Dokument
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Schritt 2: Hinzufügen des Bildes zur XImage-Sammlung

Als Nächstes fügen wir das Bild zur XImage-Sammlung des PDF-Dokuments hinzu. Verwenden Sie den folgenden Code:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Stellen Sie sicher, dass Sie den korrekten Pfad zur Bildquelldatei angeben.

## Schritt 3: Platzierung des Bildes auf der Seite

Platzieren wir nun das Bild auf der Seite des PDF-Dokuments. Verwenden Sie den folgenden Code:

```csharp
page. Contents. Add(new GSave());

// Koordinaten festlegen
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Mit dem ConcatenateMatrix-Operator: Definieren Sie, wie das Bild platziert werden soll
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Dadurch wird das Bild an den angegebenen Koordinaten auf der Seite platziert.

## Schritt 4: Speichern des PDF-Dokuments

Abschließend speichern wir das aktualisierte PDF-Dokument. Verwenden Sie den folgenden Code:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das endgültige PDF-Dokument an.

### Beispielquellcode für Store Image In XImage Collection mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument initialisieren
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Koordinaten festlegen
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Mit dem ConcatenateMatrix-Operator (Verkettungsmatrix): Definiert, wie das Bild platziert werden muss
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein Bild in der XImage-Sammlung gespeichert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um Bilder in PDF-Dateien zu bearbeiten und zu personalisieren.