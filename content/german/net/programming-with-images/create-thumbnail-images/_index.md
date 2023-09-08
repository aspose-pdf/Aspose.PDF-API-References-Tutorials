---
title: Erstellen Sie Miniaturbilder in einer PDF-Datei
linktitle: Erstellen Sie Miniaturbilder in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erstellen Sie mit Aspose.PDF für .NET ganz einfach Miniaturbilder in einer PDF-Datei.
type: docs
weight: 100
url: /de/net/programming-with-images/create-thumbnail-images/
---
In dieser Anleitung erfahren Sie Schritt für Schritt, wie Sie mit Aspose.PDF für .NET ein Miniaturbild in einer PDF-Datei erstellen. Stellen Sie sicher, dass Sie Ihre Umgebung bereits eingerichtet haben, und führen Sie die folgenden Schritte aus:

## Schritt 1: Definieren Sie das Dokumentenverzeichnis

 Bevor Sie beginnen, stellen Sie sicher, dass Sie das richtige Verzeichnis für die Dokumente festgelegt haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` Geben Sie im Code den Pfad zu dem Verzeichnis ein, das Ihre PDF-Dateien enthält.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Rufen Sie die Namen aller PDF-Dateien in einem Verzeichnis ab

 In diesem Schritt rufen wir mithilfe von C# die Namen aller im angegebenen Verzeichnis vorhandenen PDF-Dateien ab`Directory` Klasse. Dateien werden in einem Array von Zeichenfolgen gespeichert.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Schritt 3: Durchsuchen Sie alle PDF-Dateien und ihre Seiten

 In diesem Schritt gehen wir alle PDF-Dateien und ihre Seiten durch, um Miniaturansichten der Bilder zu erstellen. Wir werden a verwenden`for` Schleife, um alle Dateien zu durchlaufen.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //Öffnen Sie das PDF-Dokument
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Gehen Sie alle Seiten des Dokuments durch
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Erstellen Sie einen Stream, um das Miniaturbild zu speichern
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Erstellen Sie ein Resolution-Objekt
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

### Beispielquellcode zum Erstellen von Miniaturbildern mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Rufen Sie die Namen aller PDF-Dateien in einem bestimmten Verzeichnis ab
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Durchlaufen Sie alle Dateieinträge im Array
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Dokument öffnen
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Auflösungsobjekt erstellen
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, Auflösung, 100);
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

Herzlichen Glückwunsch! Sie haben mit Aspose.PDF für .NET erfolgreich Miniaturansichten von Bildern aus PDF-Dateien erstellt. Miniaturansichten der Bilder werden im angegebenen Verzeichnis gespeichert. Sie können diese Miniaturansichten nun verwenden, um eine visuelle Vorschau Ihrer PDF-Dateien anzuzeigen.

### FAQs zum Erstellen von Miniaturbildern in einer PDF-Datei

#### F: Was ist der Zweck der Erstellung von Miniaturbildern aus PDF-Dateien mit Aspose.PDF für .NET?

A: Durch das Erstellen von Miniaturbildern aus PDF-Dateien können Sie kleine visuelle Vorschauen jeder Seite im PDF erstellen, was für eine schnelle Vorschau und Navigation durch den Inhalt nützlich sein kann.

#### F: Wie erleichtert Aspose.PDF für .NET die Erstellung von Miniaturbildern aus PDF-Dateien?

A: Aspose.PDF für .NET bietet einen schrittweisen Prozess zum Öffnen von PDF-Dokumenten, zum Durchlaufen ihrer Seiten, zum Erstellen von Miniaturbildern und zum Speichern dieser in einem angegebenen Verzeichnis mithilfe von`JpegDevice` Klasse.

#### F: Warum ist es wichtig, das Dokumentverzeichnis zu definieren, bevor mit der Erstellung von Miniaturbildern begonnen wird?

A: Durch die Angabe des Dokumentverzeichnisses wird sichergestellt, dass die PDF-Dateien korrekt lokalisiert werden und die resultierenden Miniaturbilder im gewünschten Ausgabepfad gespeichert werden.

####  F: Wie funktioniert das?`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: Die`Document` Mit der Klasse können Sie PDF-Dokumente öffnen und bearbeiten. In diesem Fall werden damit die PDF-Dateien geladen, aus denen Miniaturbilder erstellt werden.

####  F: Welche Rolle spielt das`JpegDevice` class play in the creation of thumbnail images?

 A: Die`JpegDevice` Die Klasse ist für die Konvertierung von PDF-Seiten in JPEG-Bilder verantwortlich, die als Miniaturbilder verwendet werden. Sie können Attribute wie Breite, Höhe, Auflösung und Qualität angeben.

#### F: Wie wird jede Seite des PDF-Dokuments in ein einzelnes Miniaturbild konvertiert?

 A: Eine verschachtelte`for`Die Schleife wird verwendet, um jede PDF-Datei und ihre Seiten zu durchlaufen. Für jede Seite wird ein JPEG-Gerät mit angegebenen Attributen erstellt und das`Process` Die Methode wird verwendet, um die Seite in ein Miniaturbild umzuwandeln und es im Stream zu speichern.

#### F: Kann ich die Auflösung oder Qualität der resultierenden Miniaturbilder während des Erstellungsprozesses anpassen?

 A: Ja, Sie können Attribute wie Auflösung, Breite, Höhe und Qualität ändern, indem Sie das konfigurieren`JpegDevice` Objekt vor dem Konvertieren jeder Seite.

#### F: Wie kann ich die generierten Miniaturbilder nach dem Erstellungsprozess in meinen Projekten oder Anwendungen verwenden?

A: Die resultierenden Miniaturbilder können verwendet werden, um eine visuelle Vorschau von PDF-Dateien bereitzustellen und Benutzern dabei zu helfen, den Inhalt schnell zu identifizieren und darin zu navigieren.

#### : Gibt es eine Begrenzung für die Anzahl der Miniaturbilder, die mit diesem Erstellungsprozess aus PDF-Dateien generiert werden können?

A: Die Anzahl der generierten Miniaturbilder hängt von der Anzahl der Seiten in jedem PDF-Dokument ab. Jede Seite wird in ein separates Miniaturbild umgewandelt.