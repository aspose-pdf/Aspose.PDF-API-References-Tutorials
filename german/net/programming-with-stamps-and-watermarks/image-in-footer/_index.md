---
title: Bild in der Fußzeile
linktitle: Bild in der Fußzeile
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen.
type: docs
weight: 130
url: /de/net/programming-with-stamps-and-watermarks/image-in-footer/
---
In diesem Tutorial zeigen wir Ihnen Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen. Wir verwenden den bereitgestellten C#-Quellcode, um ein vorhandenes PDF-Dokument zu öffnen, einen Bildpuffer zu erstellen, seine Eigenschaften festzulegen und ihn allen Seiten des PDF-Dokuments hinzuzufügen.

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
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr PDF-Dokument befindet.

## Schritt 3: Erstellen und Hinzufügen des Bildes im Fußzeilenbereich

Nachdem das PDF-Dokument nun geladen ist, können wir einen Bildstempel erstellen und ihn auf allen Seiten des Dokuments hinzufügen. Hier ist wie:

```csharp
// Erstellen Sie den Frame-Puffer
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Legen Sie die Eigenschaften des Bildpuffers fest
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//Bildpuffer zu allen Seiten hinzufügen
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Der obige Code erstellt einen Bildpuffer aus der Datei „aspose-logo.jpg“ und legt dessen Eigenschaften wie den unteren Rand sowie die horizontale und vertikale Ausrichtung fest. Anschließend wird der Bildpuffer allen Seiten des PDF-Dokuments hinzugefügt.

## Schritt 4: Speichern des geänderten PDF-Dokuments

Sobald das Bild zum Fußzeilenbereich hinzugefügt wurde, können wir das geänderte PDF-Dokument speichern. Hier ist wie:

```csharp
// Speichern Sie das geänderte PDF-Dokument
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

Der obige Code speichert das bearbeitete PDF-Dokument im angegebenen Verzeichnis.

### Beispielquellcode für Image In Footer mit Aspose.PDF für .NET 
```csharp

// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokument öffnen
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

// Fußzeile erstellen
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Legen Sie die Eigenschaften des Stempels fest
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Fußzeile auf allen Seiten hinzufügen
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

// Speichern Sie die aktualisierte PDF-Datei
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben gelernt, wie Sie mit Aspose.PDF für .NET ein Bild in den Fußzeilenbereich eines PDF-Dokuments einfügen. Sie können jetzt die Fußzeilen Ihrer PDF-Dokumente anpassen, indem Sie Bilder hinzufügen.
