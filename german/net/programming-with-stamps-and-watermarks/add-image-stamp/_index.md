---
title: Bildstempel hinzufügen
linktitle: Bildstempel hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ganz einfach einen Bildstempel zu Ihren PDF-Dokumenten hinzufügen.
type: docs
weight: 20
url: /de/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET einen Bildpuffer zu einem PDF-Dokument hinzufügen. Wir zeigen Ihnen, wie Sie mit dem bereitgestellten C#-Quellcode einen benutzerdefinierten Bildpuffer zu einer bestimmten Seite im PDF-Dokument hinzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen des Framebuffers

Nachdem Sie das PDF-Dokument hochgeladen haben, können Sie den hinzuzufügenden Bildstempel erstellen. So geht's:

```csharp
// Erstellen Sie den Frame-Puffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

Der obige Code erstellt einen neuen Bildpuffer mithilfe der Datei „aspose-logo.jpg“. Stellen Sie sicher, dass der Pfad der Bilddatei korrekt ist.

## Schritt 4: Konfigurieren der Bildpuffereigenschaften

Bevor Sie den Bildstempel zum PDF-Dokument hinzufügen, können Sie verschiedene Eigenschaften des Stempels konfigurieren, wie z. B. Deckkraft, Größe, Position usw. So geht's:

```csharp
// Konfigurieren Sie die Eigenschaften des Bildpuffers
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

Sie können diese Eigenschaften entsprechend Ihren Bedürfnissen anpassen.

## Schritt 5: Bildstempel zum PDF hinzufügen

Da der Bildstempel nun fertig ist, können Sie ihn einer bestimmten Seite des PDF-Dokuments hinzufügen. Hier ist wie:

```csharp
// Fügen Sie den Frame-Puffer zur spezifischen Seite hinzu
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Der obige Code fügt den Bildpuffer zur ersten Seite des PDF-Dokuments hinzu. Bei Bedarf können Sie eine andere Seite angeben.

## Schritt 6: Speichern Sie das Ausgabedokument

Nachdem Sie den Bildpuffer hinzugefügt haben, können Sie das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das Ausgabedokument
pdfDocument.Save(dataDir);
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für „Bildstempel hinzufügen“ mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Bildstempel erstellen
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Stempel zu einer bestimmten Seite hinzufügen
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Ausgabedokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET einen Bildpuffer hinzufügen. Jetzt können Sie dieses Wissen auf Ihre eigenen Projekte anwenden, um benutzerdefinierte Bildstempel zu PDF-Dokumenten hinzuzufügen.
