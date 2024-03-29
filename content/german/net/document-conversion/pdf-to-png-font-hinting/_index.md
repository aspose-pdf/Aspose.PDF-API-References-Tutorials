---
title: Hinweise zu PDF-zu-PNG-Schriftarten
linktitle: Hinweise zu PDF-zu-PNG-Schriftarten
second_title: Aspose.PDF für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Konvertieren von PDF in PNG mit Schriftarthinweisen mithilfe von Aspose.PDF für .NET.
type: docs
weight: 160
url: /de/net/document-conversion/pdf-to-png-font-hinting/
---
In diesem Tutorial führen wir Sie durch den Prozess der Konvertierung einer PDF-Datei in PNG-Bilder mit Aspose.PDF für .NET und aktivieren dabei Schriftartenhinweise. Font Hinting ist eine Technik, die die Lesbarkeit kleiner Schriftarten verbessert. Wenn Sie die folgenden Schritte ausführen, können Sie jede Seite der PDF-Datei in ein PNG-Bild mit Schriftartenhinweisen konvertieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF-Bibliothek für .NET auf Ihrem System installiert.
- Eine Entwicklungsumgebung wie Visual Studio.

## Schritt 1: Öffnen des Quell-PDF-Dokuments
In diesem Schritt öffnen wir die Quell-PDF-Datei mit Aspose.PDF für .NET. Befolgen Sie den folgenden Code:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Öffnen Sie das Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Unbedingt austauschen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Verzeichnis, in dem sich Ihre PDF-Datei befindet.

## Schritt 2: Aktivieren Sie die Schriftartenhinweise
Nach dem Öffnen der PDF-Datei aktivieren wir mithilfe der Rendering-Optionen Schriftarthinweise. Verwenden Sie den folgenden Code:

```csharp
// Erstellen Sie Rendering-Optionen, um Schriftartenhinweise zu aktivieren
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Schritt 3: In PNG-Bilder konvertieren
Jetzt konvertieren wir jede Seite der PDF-Datei in ein PNG-Bild mit Schriftartenhinweisen. Verwenden Sie den folgenden Code:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Erstellen Sie ein PNGDevice-Objekt mit den angegebenen Attributen
         // Breite, Höhe, Auflösung, Qualität
         // Qualität [0-100], 100 ist das Maximum
         // Erstellen Sie ein Resolution-Objekt
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Legen Sie vordefinierte Rendering-Optionen fest
         pngDevice.RenderingOptions = opts;

         // Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Schließen Sie den Stream
         imageStream.Close();
     }
}
```

Der obige Code konvertiert jede Seite der PDF-Datei in ein PNG-Bild mit Schriftartenhinweisen und speichert jedes Bild als separate PNG-Datei.

### Beispielquellcode für PDF-zu-PNGFont-Hinweise mit Aspose.PDF für .NET

```csharp
try
{
	
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokument öffnen
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Erstellen Sie Aspose.Pdf.RenderingOptions, um Schriftartenhinweise zu aktivieren
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Erstellen Sie ein PNG-Gerät mit angegebenen Attributen
			// Breite, Höhe, Auflösung, Qualität
			// Qualität [0-100], 100 ist das Maximum
			// Auflösungsobjekt erstellen
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Legen Sie vordefinierte Rendering-Optionen fest
			pngDevice.RenderingOptions = opts;

			//Konvertieren Sie eine bestimmte Seite und speichern Sie das Bild im Stream
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Stream schließen
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Abschluss
In diesem Tutorial haben wir den Schritt-für-Schritt-Prozess der Konvertierung von PDF-Dateien in PNG-Bilder mit Schriftarthinweisen mithilfe von Aspose.PDF für .NET behandelt. Wenn Sie die oben beschriebenen Anweisungen befolgen, sollten Sie nun in der Lage sein, jede Seite der PDF-Datei in ein PNG-Bild mit Schriftartenhinweisen zu konvertieren. Diese Funktion ist nützlich, wenn Sie beim Konvertieren in PNG-Bilder die Lesbarkeit kleiner Schriftarten beibehalten möchten.

### FAQs

#### F: Was ist Schrifthinweis und warum ist er beim Konvertieren von PDF in PNG wichtig?

A: Font Hinting ist eine Technik, mit der die Lesbarkeit kleiner Schriftarten durch Anpassen ihrer Form und Positionierung verbessert wird. Beim Konvertieren von PDF- in PNG-Bilder stellt die Aktivierung von Schrifthinweisen sicher, dass der Text in den resultierenden PNG-Bildern lesbar und klar bleibt, insbesondere bei kleinen Schriftgrößen. Dies ist wichtig, um die Qualität und Lesbarkeit von Texten bei der Konvertierung von PDF-Dokumenten in Bilder aufrechtzuerhalten.

#### F: Wie wirkt sich die Schriftartangabe auf den PNG-Konvertierungsprozess aus?

A: Schriftarthinweise beeinflussen die Art und Weise, wie der Text in den resultierenden PNG-Bildern während des PDF-zu-PNG-Konvertierungsprozesses gerendert wird. Durch die Aktivierung von Schrifthinweisen passt die Aspose.PDF-Bibliothek die Schriftwiedergabe an, um sicherzustellen, dass kleine Schriftarten ihre Klarheit und Lesbarkeit behalten und die PNG-Bilder optisch ansprechender und lesbarer werden.

#### F: Kann ich die Einstellungen für Schriftarthinweise anpassen, um die PNG-Konvertierung anzupassen?

 A: Ja, die Aspose.PDF für .NET-Bibliothek bietet Optionen zum Anpassen des PNG-Konvertierungsprozesses, einschließlich Einstellungen für Schriftarthinweise. Im bereitgestellten Codebeispiel ist die`UseFontHinting` Eigentum der`RenderingOptions` Objekt ist eingestellt auf`true` um Schriftartenhinweise zu aktivieren. Sie können den Konvertierungsprozess weiter verfeinern, indem Sie andere Eigenschaften im anpassen`RenderingOptions` Unterricht nach Ihren Wünschen.

#### F: Wie werden die PNG-Bilder beim PNG-Konvertierungsprozess gespeichert?

A: Im bereitgestellten Codebeispiel wird jede Seite des PDF-Dokuments in ein separates PNG-Bild konvertiert. Die PNG-Bilder werden als einzelne Dateien mit Dateinamen gespeichert, die dem Muster „Bild“ folgen{pageCount}_ out.png", wo`{pageCount}` ist die Nummer der Seite, die konvertiert wird. Jedes PNG-Bild stellt eine Seite des ursprünglichen PDF-Dokuments dar.