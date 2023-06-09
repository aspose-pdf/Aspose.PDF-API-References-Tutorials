---
title: Bildgröße festlegen
linktitle: Bildgröße festlegen
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Größe eines Bildes in einem PDF-Dokument mit Aspose.PDF für .NET.
type: docs
weight: 270
url: /de/net/programming-with-images/set-image-size/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.PDF für .NET die Größe eines Bildes in einem PDF-Dokument festlegen. Befolgen Sie diese Schritte, um diesen Vorgang einfach durchzuführen.

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

// Pfad zur Bildquelldatei
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
//Seite zur Seitensammlung der PDF-Datei hinzufügen
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