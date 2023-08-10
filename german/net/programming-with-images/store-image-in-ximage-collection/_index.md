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
//Initialisieren Sie das Dokument
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

// Mit dem ConcatenateMatrix-Operator: Definieren Sie, wie das Bild platziert werden soll
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
// Mit dem ConcatenateMatrix-Operator (Verkettungsmatrix): Definiert, wie das Bild platziert werden muss
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich ein Bild in der XImage-Sammlung gespeichert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um Bilder in PDF-Dateien zu bearbeiten und zu personalisieren.

### FAQs

#### F: Was ist der Zweck der Speicherung eines Bildes in der XImage-Sammlung mit Aspose.PDF für .NET?

A: Durch das Speichern eines Bildes in der XImage-Sammlung können Sie Bilder in einem PDF-Dokument effizient verwalten und verwenden. Mit diesem Ansatz können Sie Bilder bearbeiten, anpassen und personalisieren, bevor Sie sie auf bestimmten Seiten platzieren.

#### F: Wie unterscheidet sich das Speichern eines Bildes in der XImage-Sammlung vom direkten Platzieren eines Bildes auf einer PDF-Seite?

A: Das Speichern eines Bildes in der XImage-Sammlung bietet eine besser organisierte und wiederverwendbare Möglichkeit, Bilder zu verwalten. Anstatt ein Bild direkt auf einer Seite zu platzieren, speichern Sie es in der Sammlung und können dann bei Bedarf namentlich darauf verweisen, was eine einfachere Verwaltung und Änderung ermöglicht.

#### F: Kann ich innerhalb eines einzigen PDF-Dokuments mehrere Bilder zur XImage-Sammlung hinzufügen?

A: Ja, Sie können innerhalb desselben PDF-Dokuments mehrere Bilder zur XImage-Sammlung hinzufügen. Jedem Bild wird in der Sammlung ein eindeutiger Name zugewiesen, der zur Referenzierung und Platzierung der Bilder auf verschiedenen Seiten verwendet werden kann.

#### F: Wie lege ich die Position und Größe des Bildes fest, wenn ich es auf einer PDF-Seite aus der XImage-Sammlung platziere?

A: Um die Position und Größe des Bildes festzulegen, müssen Sie ein Rechteck und eine Matrixtransformation definieren. Das Rechteck definiert die Grenzen des Bildes und die Matrixtransformation gibt an, wie das Bild innerhalb dieses Rechtecks platziert werden soll.

####  F: Was ist der Zweck des`GSave()` and `GRestore()` operators in the code for placing the image?

 A: Die`GSave()` Und`GRestore()` Operatoren werden verwendet, um den Grafikstatus der PDF-Seite zu speichern und wiederherzustellen. Dadurch wird sichergestellt, dass die auf der Seite ausgeführten Vorgänge, z. B. das Platzieren des Bildes, keinen Einfluss auf den Status der Seite nach dem Platzieren des Bildes haben.

#### F: Kann ich zusätzliche Änderungen oder Transformationen auf die in der XImage-Sammlung gespeicherten Bilder anwenden?

A: Ja, Sie können verschiedene Änderungen und Transformationen auf die in der XImage-Sammlung gespeicherten Bilder anwenden. Mit den entsprechenden Operationen und Techniken von Aspose.PDF für .NET können Sie drehen, skalieren, zuschneiden und andere Transformationen durchführen.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren, um Bilder in der XImage-Sammlung eines PDF-Dokuments zu speichern und zu platzieren?

A: Um diese Methode zu integrieren, befolgen Sie die beschriebenen Schritte und ändern Sie den Code, um ihn an die Anforderungen Ihres Projekts anzupassen. Mit der XImage-Sammlung können Sie Bilder speichern und verwalten und sie dann mithilfe der angegebenen Koordinaten und Transformationen auf bestimmten Seiten platzieren.

#### F: Gibt es irgendwelche Überlegungen oder Einschränkungen bei der Arbeit mit der XImage-Sammlung in Aspose.PDF für .NET?

A: Während die XImage-Sammlung eine leistungsstarke Möglichkeit zum Verwalten und Bearbeiten von Bildern bietet, ist es wichtig, Faktoren wie die Speichernutzung und die Komplexität der an den Bildern durchgeführten Vorgänge zu berücksichtigen. Eine sorgfältige Verwaltung der Sammlung und eine effiziente Nutzung der Ressourcen werden empfohlen.

#### F: Kann ich in der XImage-Sammlung gespeicherte Bilder in mehreren PDF-Dokumenten wiederverwenden?

A: Die XImage-Sammlung ist für jedes PDF-Dokument spezifisch und nicht für die dokumentübergreifende Wiederverwendung konzipiert. Wenn Sie Bilder in mehreren Dokumenten wiederverwenden müssen, müssen Sie sie für jedes Dokument separat speichern und verwalten.