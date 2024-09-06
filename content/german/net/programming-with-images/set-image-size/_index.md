---
title: Bildgröße in PDF-Datei festlegen
linktitle: Bildgröße in PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Größe eines Bildes in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 270
url: /de/net/programming-with-images/set-image-size/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Größe eines Bilds in einer PDF-Datei festlegen. Befolgen Sie diese Schritte, um diesen Vorgang problemlos durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können sie von der offiziellen Aspose-Website herunterladen.

## Schritt 1: Erstellen des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument zu erstellen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instanziieren eines Dokumentobjekts
Document doc = new Document();

// Fügen Sie der Seitensammlung der PDF-Datei eine Seite hinzu
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 2: Bild hinzugefügt

Als Nächstes fügen wir der Seite des PDF-Dokuments ein Bild hinzu. Verwenden Sie den folgenden Code:

```csharp
// Erstellen einer Imageinstanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Legen Sie die Breite und Höhe des Bildes in Punkten fest
img. FixWidth = 100;
img. FixHeight = 100;

//Bildtyp auf unbekannt (Unbekannt) setzen
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Pfad zur Bildquelldatei
img.File = dataDir + "aspose-logo.jpg";

// Fügen Sie das Bild zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(img);
```

Achten Sie darauf, den richtigen Pfad zur Bildquelldatei anzugeben.

## Schritt 3: Seiteneigenschaften festlegen

Zum Schluss legen wir die Eigenschaften der Seite fest, einschließlich ihrer Breite und Höhe. Verwenden Sie den folgenden Code:

```csharp
// Festlegen der Seiteneigenschaften
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Beispielquellcode zum Festlegen der Bildgröße mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document-Objekt instanziieren
Document doc = new Document();
// Seite zur Seitensammlung von PDF-Dateien hinzufügen
Aspose.Pdf.Page page = doc.Pages.Add();
// Erstellen einer Imageinstanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Bildbreite und -höhe in Punkten festlegen
img.FixWidth = 100;
img.FixHeight = 100;
// Bildtyp als SVG festlegen
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Pfad zur Quelldatei
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Festlegen der Seiteneigenschaften
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// Speichern Sie die resultierende PDF-Datei
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben die Größe eines Bildes in einem PDF-Dokument mit Aspose.PDF für .NET erfolgreich festgelegt. Sie können diese Methode jetzt auf Ihre eigenen Projekte anwenden, um die Größe von Bildern in PDF-Dateien anzupassen.

### FAQs zum Festlegen der Bildgröße in einer PDF-Datei

#### F: Was ist der Zweck des Festlegens der Größe eines Bildes in einem PDF-Dokument mit Aspose.PDF für .NET?

A: Der Zweck der Größeneinstellung eines Bildes in einem PDF-Dokument besteht darin, die Abmessungen des Bildes zu steuern, wenn es zum PDF hinzugefügt wird. Auf diese Weise können Sie das Erscheinungsbild und Layout von Bildern in Ihren PDF-Dateien anpassen.

#### F: Wie funktioniert die Größeneinstellung eines Bildes in einem PDF-Dokument?

 A: Der Prozess umfasst die Erstellung eines`Aspose.Pdf.Image` Instanz, indem Sie die Breite und Höhe mit den`FixWidth` Und`FixHeight` Eigenschaften und fügen Sie dann das Bild zum PDF-Dokument hinzu. Darüber hinaus können Sie die Abmessungen der Seite selbst so festlegen, dass das Bild hineinpasst.

#### F: Kann ich die Größe eines Bildes auf einen bestimmten Prozentsatz der Seitenabmessungen einstellen?

A: Der bereitgestellte Code legt die absolute Breite und Höhe des Bildes in Punkten fest. Wenn Sie die Größe eines Bildes basierend auf einem Prozentsatz der Seitenabmessungen festlegen möchten, müssen Sie die Abmessungen entsprechend berechnen und den Code entsprechend anpassen.

####  F: Welche Bedeutung hat das`FileType` property when adding an image to the PDF document?

 A: Die`FileType`Eigenschaft gibt den Typ des Bildes an, das dem PDF-Dokument hinzugefügt wird. Im bereitgestellten Code ist der Wert`Unknown` zeigt an, dass der Bildtyp unbekannt ist und Aspose.PDF versucht, den Bildtyp anhand der Dateierweiterung zu bestimmen.

#### F: Kann ich mit dieser Methode mehrere Bilder zu einer einzigen Seite hinzufügen?

 A: Ja, Sie können mehrere Bilder zu einer Seite hinzufügen, indem Sie mehrere`Aspose.Pdf.Image` Instanzen und fügen Sie sie der Absatzsammlung der Seite hinzu. Stellen Sie sicher, dass Sie die Positionierung und das Layout der Bilder nach Bedarf anpassen.

#### F: Wie kann ich die Platzierung und Ausrichtung des hinzugefügten Bildes auf der Seite steuern?

 A: Die Platzierung und Ausrichtung des hinzugefügten Bildes kann durch Anpassen der Koordinaten und des Layouts des Bildes mithilfe von Eigenschaften wie`img.Left`, `img.Top`und Absatzformatierungseigenschaften.

####  F: Was ist der Zweck der Festlegung der Seiteneigenschaften mit`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Durch das Festlegen der Seiteneigenschaften können Sie die Abmessungen der Seite selbst definieren. Dadurch wird sichergestellt, dass die Seitenabmessungen dem hinzugefügten Bild und allen anderen Inhalten, die Sie auf der Seite haben, gerecht werden.

#### F: Kann ich für verschiedene Bilder im selben PDF-Dokument unterschiedliche Größen festlegen?

 A: Ja, Sie können verschiedene Größen für verschiedene Bilder festlegen, indem Sie separate`Aspose.Pdf.Image` Instanzen und Anpassen der`FixWidth`, `FixHeight`und Platzierungseigenschaften für jedes Bild.

#### F: Wie kann ich diese Methode zum Festlegen von Bildgrößen in PDF-Dateien in meine eigenen Projekte integrieren?

A: Um diese Methode in Ihre Projekte zu integrieren, folgen Sie den beschriebenen Schritten und ändern Sie den Code nach Bedarf. Sie können diese Methode verwenden, um Ihren PDF-Dokumenten Bilder bestimmter Größen basierend auf den Anforderungen Ihrer Anwendung hinzuzufügen.