---
title: Miniaturbilder in PDF-Datei erstellen
linktitle: Miniaturbilder in PDF-Datei erstellen
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Miniaturbilder in einer PDF-Datei.
type: docs
weight: 100
url: /de/net/programming-with-images/create-thumbnail-images/
---
Diese Anleitung führt Sie Schritt für Schritt durch die Erstellung von Miniaturbildern in PDF-Dateien mit Aspose.PDF für .NET. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und befolgen Sie die folgenden Schritte:

## Schritt 1: Dokumentverzeichnis festlegen

Stellen Sie vor dem Start sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code durch den Pfad zum Verzeichnis, das Ihre PDF-Dateien enthält.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Holen Sie sich die Namen aller PDF-Dateien in einem Verzeichnis

 In diesem Schritt werden wir die Namen aller PDF-Dateien im angegebenen Verzeichnis mit C# abrufen.`Directory`Klasse. Dateien werden in einem Array von Zeichenfolgen gespeichert.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Schritt 3: Durchsuchen Sie alle PDF-Dateien und ihre Seiten

 In diesem Schritt werden wir alle PDF-Dateien und ihre Seiten durchgehen, um Bildvorschaubilder zu erstellen. Wir verwenden ein`for` Schleife, um alle Dateien zu durchlaufen.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Öffnen Sie das PDF-Dokument
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Gehen Sie alle Seiten des Dokuments durch
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Erstellen Sie einen Stream zum Speichern des Miniaturbilds
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Erstellen eines Resolution-Objekts
             Resolution resolution = new Resolution(300);
            
             // Erstellen Sie ein JPEG-Gerät mit den angegebenen Attributen
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Schließen Sie den Stream
             imageStream.Close();
         }
     }
}
```

### Beispiel-Quellcode zum Erstellen von Miniaturbildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Rufen Sie die Namen aller PDF-Dateien in einem bestimmten Verzeichnis ab
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Durchlaufen Sie alle Dateieinträge im Array.
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Dokument öffnen
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Resolution-Objekt erstellen
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = neues JpegDevice(500, 700, Auflösung, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Stream schließen
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Miniaturbilder aus PDF-Dateien erstellt. Miniaturbilder werden im angegebenen Verzeichnis gespeichert. Sie können diese Miniaturbilder jetzt verwenden, um eine visuelle Vorschau Ihrer PDF-Dateien anzuzeigen.

### FAQs zum Erstellen von Miniaturbildern in PDF-Dateien

#### F: Was ist der Zweck der Erstellung von Miniaturbildern aus PDF-Dateien mit Aspose.PDF für .NET?

A: Durch das Erstellen von Miniaturbildern aus PDF-Dateien können Sie kleine visuelle Vorschauen jeder Seite im PDF generieren, was für eine schnelle Vorschau und Navigation durch den Inhalt nützlich sein kann.

#### F: Wie erleichtert Aspose.PDF für .NET die Erstellung von Miniaturbildern aus PDF-Dateien?

 A: Aspose.PDF für .NET bietet einen schrittweisen Prozess zum Öffnen von PDF-Dokumenten, zum Durchlaufen ihrer Seiten, zum Erstellen von Miniaturbildern und zum Speichern in einem angegebenen Verzeichnis mithilfe des`JpegDevice` Klasse.

#### F: Warum ist es wichtig, das Dokumentverzeichnis zu definieren, bevor mit der Erstellung der Miniaturbilder begonnen wird?

A: Durch die Angabe des Dokumentverzeichnisses wird sichergestellt, dass die PDF-Dateien richtig lokalisiert werden und die resultierenden Miniaturbilder im gewünschten Ausgabepfad gespeichert werden.

####  F: Wie funktioniert das`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: Die`Document` Mit dieser Klasse können Sie PDF-Dokumente öffnen und bearbeiten. In diesem Fall wird sie zum Laden der PDF-Dateien verwendet, aus denen Miniaturbilder erstellt werden.

####  F: Welche Rolle spielt der`JpegDevice` class play in the creation of thumbnail images?

 A: Die`JpegDevice` Die Klasse ist für die Konvertierung von PDF-Seiten in JPEG-Bilder verantwortlich, die als Miniaturbilder verwendet werden. Sie können Attribute wie Breite, Höhe, Auflösung und Qualität angeben.

#### F: Wie wird jede Seite des PDF-Dokuments in ein einzelnes Miniaturbild umgewandelt?

 A: Eine verschachtelte`for` loop wird verwendet, um jede PDF-Datei und ihre Seiten zu durchlaufen. Für jede Seite wird ein JPEG-Gerät mit angegebenen Attributen erstellt, und die`Process` Die Methode wird verwendet, um die Seite in ein Miniaturbild umzuwandeln und es im Stream zu speichern.

#### F: Kann ich die Auflösung oder Qualität der resultierenden Miniaturbilder während des Erstellungsprozesses anpassen?

A: Ja, Sie können Attribute wie Auflösung, Breite, Höhe und Qualität ändern, indem Sie die`JpegDevice` Objekt vor der Konvertierung jeder Seite.

#### F: Wie kann ich die generierten Miniaturbilder nach dem Erstellungsprozess in meinen Projekten oder Anwendungen nutzen?

A: Die resultierenden Miniaturbilder können verwendet werden, um eine visuelle Vorschau von PDF-Dateien bereitzustellen und Benutzern zu helfen, den Inhalt schnell zu identifizieren und darin zu navigieren.

#### : Gibt es eine Begrenzung für die Anzahl der Miniaturbilder, die mit diesem Erstellungsverfahren aus PDF-Dateien generiert werden können?

A: Die Anzahl der generierten Miniaturbilder hängt von der Anzahl der Seiten in jedem PDF-Dokument ab. Jede Seite wird in ein separates Miniaturbild umgewandelt.