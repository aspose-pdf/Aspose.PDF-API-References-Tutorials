---
title: Bild in XImage-Sammlung speichern
linktitle: Bild in XImage-Sammlung speichern
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Speichern eines Bildes in einer XImage-Sammlung mit Aspose.PDF für .NET.
type: docs
weight: 290
url: /de/net/programming-with-images/store-image-in-ximage-collection/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET ein Bild in der XImage-Sammlung speichern. Befolgen Sie diese Schritte, um diesen Vorgang problemlos durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können sie von der offiziellen Aspose-Website herunterladen.

## Schritt 1: Initialisierung des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument zu initialisieren:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//Initialisieren des Dokuments
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Schritt 2: Hinzufügen des Bildes zur XImage-Sammlung

Als nächstes fügen wir das Bild zur XImage-Sammlung des PDF-Dokuments hinzu. Verwenden Sie den folgenden Code:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Achten Sie darauf, den richtigen Pfad zur Bildquelldatei anzugeben.

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

// Verwenden des ConcatenateMatrix-Operators: Definieren Sie, wie das Bild platziert werden soll
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Dadurch wird das Bild an den angegebenen Koordinaten auf der Seite platziert.

## Schritt 4: Speichern des PDF-Dokuments

Zum Schluss speichern wir das aktualisierte PDF-Dokument. Verwenden Sie den folgenden Code:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Geben Sie unbedingt den gewünschten Pfad und Dateinamen für das endgültige PDF-Dokument an.

### Beispielquellcode zum Speichern von Bildern in einer XImage-Sammlung mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
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
// Verwenden des Operators ConcatenateMatrix (Matrix verketten): Definiert, wie das Bild platziert werden muss
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich ein Bild in der XImage-Sammlung mit Aspose.PDF für .NET gespeichert. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um Bilder in PDF-Dateien zu bearbeiten und zu personalisieren.

### Häufig gestellte Fragen

#### F: Was ist der Zweck der Speicherung eines Bildes in der XImage-Sammlung mit Aspose.PDF für .NET?

A: Durch das Speichern eines Bilds in der XImage-Sammlung können Sie Bilder in einem PDF-Dokument effizient verwalten und verwenden. Mit diesem Ansatz können Sie Bilder bearbeiten, anpassen und personalisieren, bevor Sie sie auf bestimmten Seiten platzieren.

#### F: Worin besteht der Unterschied zwischen dem Speichern eines Bildes in der XImage-Sammlung und dem direkten Platzieren eines Bildes auf einer PDF-Seite?

A: Das Speichern eines Bilds in der XImage-Sammlung bietet eine besser organisierte und wiederverwendbare Möglichkeit, Bilder zu verwalten. Anstatt ein Bild direkt auf einer Seite zu platzieren, speichern Sie es in der Sammlung und können dann bei Bedarf namentlich darauf verweisen, was die Verwaltung und Änderung erleichtert.

#### F: Kann ich der XImage-Sammlung in einem einzigen PDF-Dokument mehrere Bilder hinzufügen?

A: Ja, Sie können der XImage-Sammlung innerhalb desselben PDF-Dokuments mehrere Bilder hinzufügen. Jedem Bild wird in der Sammlung ein eindeutiger Name zugewiesen, der zum Verweisen und Platzieren der Bilder auf verschiedenen Seiten verwendet werden kann.

#### F: Wie gebe ich die Position und Größe des Bildes an, wenn ich es auf einer PDF-Seite aus der XImage-Sammlung platziere?

A: Um die Position und Größe des Bildes festzulegen, müssen Sie ein Rechteck und eine Matrixtransformation definieren. Das Rechteck definiert die Grenzen des Bildes und die Matrixtransformation gibt an, wie das Bild innerhalb dieses Rechtecks platziert werden soll.

####  F: Was ist der Zweck der`GSave()` and `GRestore()` operators in the code for placing the image?

 A: Die`GSave()` Und`GRestore()` Operatoren werden verwendet, um den Grafikstatus der PDF-Seite zu speichern und wiederherzustellen. Dadurch wird sichergestellt, dass die auf der Seite ausgeführten Vorgänge, z. B. das Platzieren des Bildes, den Status der Seite nach dem Platzieren des Bildes nicht beeinflussen.

#### F: Kann ich zusätzliche Änderungen oder Transformationen auf die in der XImage-Sammlung gespeicherten Bilder anwenden?

A: Ja, Sie können verschiedene Änderungen und Transformationen auf die in der XImage-Sammlung gespeicherten Bilder anwenden. Sie können sie drehen, skalieren, zuschneiden und andere Transformationen mit den entsprechenden Operationen und Techniken durchführen, die von Aspose.PDF für .NET bereitgestellt werden.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren, um Bilder in der XImage-Sammlung eines PDF-Dokuments zu speichern und zu platzieren?

A: Um diese Methode zu integrieren, folgen Sie den beschriebenen Schritten und ändern Sie den Code, um ihn den Anforderungen Ihres Projekts anzupassen. Sie können die XImage-Sammlung verwenden, um Bilder zu speichern und zu verwalten und sie dann mit den angegebenen Koordinaten und Transformationen auf bestimmten Seiten zu platzieren.

#### F: Gibt es irgendwelche Überlegungen oder Einschränkungen bei der Arbeit mit der XImage-Sammlung in Aspose.PDF für .NET?

A: Die XImage-Sammlung bietet zwar eine leistungsstarke Möglichkeit zum Verwalten und Bearbeiten von Bildern, es ist jedoch wichtig, Faktoren wie Speichernutzung und Komplexität der an den Bildern durchgeführten Vorgänge zu berücksichtigen. Eine sorgfältige Verwaltung der Sammlung und eine effiziente Nutzung der Ressourcen wird empfohlen.

#### F: Kann ich in der XImage-Sammlung gespeicherte Bilder in mehreren PDF-Dokumenten wiederverwenden?

A: Die XImage-Sammlung ist spezifisch für jedes PDF-Dokument und nicht für die dokumentübergreifende Wiederverwendung konzipiert. Wenn Sie Bilder in mehreren Dokumenten wiederverwenden müssen, müssen Sie sie für jedes Dokument separat speichern und verwalten.