---
title: Bild im Header
linktitle: Bild im Header
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild in den Kopfbereich eines PDF-Dokuments einfügen.
type: docs
weight: 140
url: /de/net/programming-with-stamps-and-watermarks/image-in-header/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild in den Kopfbereich eines PDF-Dokuments einfügen. Wir verwenden den bereitgestellten C#-Quellcode, um ein vorhandenes PDF-Dokument zu öffnen, einen Bildpuffer zu erstellen, seine Eigenschaften festzulegen und ihn allen Seiten des PDF-Dokuments hinzuzufügen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Eine installierte .NET-Entwicklungsumgebung.
- Die Aspose.PDF-Bibliothek für .NET wurde heruntergeladen und in Ihrem Projekt referenziert.

## Schritt 2: Laden des vorhandenen PDF-Dokuments

Der erste Schritt besteht darin, das vorhandene PDF-Dokument in Ihr Projekt zu laden. Hier ist wie:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öffnen Sie das vorhandene PDF-Dokument
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen und Hinzufügen des Bildes im Kopfbereich

Nachdem das PDF-Dokument nun geladen ist, können wir einen Bildpuffer erstellen und ihn allen Seiten des Dokuments als Kopfzeilenabschnitt hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie den Frame-Puffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Legen Sie die Eigenschaften des Bildpuffers fest
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

//Bildpuffer zu allen Seiten hinzufügen
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Der obige Code erstellt einen Bildpuffer aus der Datei „aspose-logo.jpg“ und legt dessen Eigenschaften wie den oberen Rand sowie die horizontale und vertikale Ausrichtung fest. Anschließend wird der Bildstempel als Kopfbereich auf allen Seiten des PDF-Dokuments eingefügt.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Sobald das Bild im Kopfbereich hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Imagein Header mit Aspose.PDF für .NET 

```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Kopfzeile erstellen
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Legen Sie die Eigenschaften des Stempels fest
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Kopfzeile auf allen Seiten hinzufügen
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Aktualisiertes Dokument speichern
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET ein Bild in den Kopfbereich eines PDF-Dokuments einfügen. Sie können jetzt die Kopfzeilen Ihrer PDF-Dokumente anpassen, indem Sie Bilder hinzufügen.
