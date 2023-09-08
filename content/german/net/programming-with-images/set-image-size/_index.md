---
title: Bildgröße in der PDF-Datei festlegen
linktitle: Bildgröße in der PDF-Datei festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Größe eines Bildes in einer PDF-Datei mit Aspose.PDF für .NET.
type: docs
weight: 270
url: /de/net/programming-with-images/set-image-size/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Größe eines Bildes in einer PDF-Datei festlegen. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder eine andere Entwicklungsumgebung installiert und konfiguriert.
- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET installiert. Sie können es von der offiziellen Website von Aspose herunterladen.

## Schritt 1: Erstellung des PDF-Dokuments

Verwenden Sie zunächst den folgenden Code, um ein neues PDF-Dokument zu erstellen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instanziieren Sie ein Document-Objekt
Document doc = new Document();

// Fügen Sie eine Seite zur Seitensammlung der PDF-Datei hinzu
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Schritt 2: Bild hinzugefügt

Als Nächstes fügen wir der Seite des PDF-Dokuments ein Bild hinzu. Verwenden Sie den folgenden Code:

```csharp
// Erstellen Sie eine Image-Instanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Legen Sie die Breite und Höhe des Bildes in Punkten fest
img. FixWidth = 100;
img. FixHeight = 100;

// Bildtyp auf unbekannt (Unbekannt) setzen
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//Pfad zur Bildquelldatei
img.File = dataDir + "aspose-logo.jpg";

// Fügen Sie das Bild zur Absatzsammlung der Seite hinzu
page.Paragraphs.Add(img);
```

Stellen Sie sicher, dass Sie den korrekten Pfad zur Bildquelldatei angeben.

## Schritt 3: Seiteneigenschaften festlegen

Schließlich legen wir die Eigenschaften der Seite fest, einschließlich ihrer Breite und Höhe. Verwenden Sie den folgenden Code:

```csharp
// Seiteneigenschaften festlegen
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Beispielquellcode zum Festlegen der Bildgröße mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentobjekt instanziieren
Document doc = new Document();
// Seite zur Seitensammlung der PDF-Datei hinzufügen
Aspose.Pdf.Page page = doc.Pages.Add();
// Erstellen Sie eine Image-Instanz
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Legen Sie die Bildbreite und -höhe in Punkten fest
img.FixWidth = 100;
img.FixHeight = 100;
// Stellen Sie den Bildtyp auf SVG ein
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Pfad für die Quelldatei
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Seiteneigenschaften festlegen
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

#### F: Was ist der Zweck, die Größe eines Bildes in einem PDF-Dokument mit Aspose.PDF für .NET festzulegen?

A: Der Zweck des Festlegens der Größe eines Bildes in einem PDF-Dokument besteht darin, die Abmessungen des Bildes zu steuern, wenn es dem PDF hinzugefügt wird. Dadurch können Sie das Erscheinungsbild und Layout von Bildern in Ihren PDF-Dateien anpassen.

#### F: Wie funktioniert das Festlegen der Bildgröße in einem PDF-Dokument?

 A: Der Prozess umfasst die Erstellung eines`Aspose.Pdf.Image` Geben Sie beispielsweise seine Breite und Höhe mithilfe von an`FixWidth` Und`FixHeight` Eigenschaften und fügen Sie dann das Bild dem PDF-Dokument hinzu. Darüber hinaus können Sie die Abmessungen der Seite selbst anpassen, um sie an das Bild anzupassen.

#### F: Kann ich die Größe eines Bildes auf einen bestimmten Prozentsatz der Seitenabmessungen einstellen?

A: Der bereitgestellte Code legt die absolute Breite und Höhe des Bildes in Punkten fest. Wenn Sie die Größe eines Bildes anhand eines Prozentsatzes der Seitenabmessungen festlegen möchten, müssen Sie die Abmessungen entsprechend berechnen und den Code entsprechend anpassen.

####  F: Welche Bedeutung hat das?`FileType` property when adding an image to the PDF document?

 A: Die`FileType`Die Eigenschaft gibt den Typ des Bildes an, das dem PDF-Dokument hinzugefügt wird. Im bereitgestellten Code der Wert`Unknown` zeigt an, dass der Bildtyp unbekannt ist und Aspose.PDF versucht, den Bildtyp anhand der Dateierweiterung zu ermitteln.

#### F: Kann ich mit dieser Methode mehrere Bilder zu einer einzelnen Seite hinzufügen?

 A: Ja, Sie können mehrere Bilder zu einer einzelnen Seite hinzufügen, indem Sie mehrere erstellen`Aspose.Pdf.Image` Instanzen und fügen Sie sie der Absatzsammlung der Seite hinzu. Stellen Sie sicher, dass Sie die Positionierung und das Layout der Bilder nach Bedarf anpassen.

#### F: Wie kann ich die Platzierung und Ausrichtung des hinzugefügten Bildes auf der Seite steuern?

 A: Die Platzierung und Ausrichtung des hinzugefügten Bildes kann durch Anpassen der Koordinaten und des Layouts des Bildes mithilfe von Eigenschaften wie gesteuert werden`img.Left`, `img.Top`und Absatzformatierungseigenschaften.

####  F: Zu welchem Zweck werden die Seiteneigenschaften festgelegt?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: Durch Festlegen der Seiteneigenschaften können Sie die Abmessungen der Seite selbst definieren. Dadurch wird sichergestellt, dass die Seitenabmessungen dem hinzugefügten Bild und allen anderen Inhalten, die Sie möglicherweise auf der Seite haben, gerecht werden.

#### F: Kann ich für verschiedene Bilder innerhalb desselben PDF-Dokuments unterschiedliche Größen festlegen?

 A: Ja, Sie können unterschiedliche Größen für verschiedene Bilder festlegen, indem Sie separate Bilder erstellen`Aspose.Pdf.Image` Instanzen und Anpassen der`FixWidth`, `FixHeight`und Platzierungseigenschaften für jedes Bild.

#### F: Wie kann ich diese Methode in meine eigenen Projekte integrieren, um Bildgrößen in PDF-Dateien festzulegen?

A: Um diese Methode in Ihre Projekte zu integrieren, befolgen Sie die beschriebenen Schritte und ändern Sie den Code nach Bedarf. Mit dieser Methode können Sie je nach den Anforderungen Ihrer Anwendung Bilder in bestimmten Größen zu Ihren PDF-Dokumenten hinzufügen.