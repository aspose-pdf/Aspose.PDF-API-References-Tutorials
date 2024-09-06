---
title: Extrahieren Sie Text mit dem Textgerät
linktitle: Extrahieren Sie Text mit dem Textgerät
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit dem Textgerät in Aspose.PDF für .NET Text aus einem PDF-Dokument extrahieren.
type: docs
weight: 210
url: /de/net/programming-with-text/extract-text-using-text-device/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einem PDF-Dokument mithilfe des Textgeräts in Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, aus der Sie Text extrahieren möchten, oben in der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Schritt 5: Text mit Text Device extrahieren
 Erstellen Sie ein`StringBuilder` Objekt, das den extrahierten Text enthält. Durchlaufen Sie jede Seite des Dokuments und verwenden Sie ein`TextDevice` um den Text von jeder Seite zu extrahieren.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Schritt 6: Speichern Sie den extrahierten Text
 Geben Sie den Ausgabedateipfad an und speichern Sie den extrahierten Text in einer Textdatei mit dem`File.WriteAllText` Verfahren.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Beispielquellcode zum Extrahieren von Text mit Text Device unter Verwendung von Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Zeichenfolge zur Aufnahme des extrahierten Textes
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Textgerät erstellen
		TextDevice textDevice = new TextDevice();
		// Textextraktionsoptionen festlegen - Textextraktionsmodus festlegen (Raw oder Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konvertieren Sie eine bestimmte Seite und speichern Sie Text im Stream
		textDevice.Process(pdfPage, textStream);
		// Konvertieren Sie eine bestimmte Seite und speichern Sie Text im Stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Memory Stream schließen
		textStream.Close();
		// Text aus dem Speicherstrom abrufen
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Speichern Sie den extrahierten Text in einer Textdatei
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben erfolgreich Text aus einem PDF-Dokument mithilfe des Textgeräts in Aspose.PDF für .NET extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial bietet Anleitungen zum Extrahieren von Text aus einem PDF-Dokument mithilfe der Text Device-Funktion in Aspose.PDF für .NET. Der zugehörige C#-Quellcode zeigt die notwendigen Schritte zum Erfüllen dieser Aufgabe.

#### F: Welche Namespaces soll ich importieren?

A: Fügen Sie in der Codedatei, aus der Sie Text extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Bereitstellung des Pfads zur Eingabe-PDF-Datei.

#### F: Wie extrahiere ich Text mit dem Textgerät?

 A: Schritt 5 umfasst die Erstellung eines`StringBuilder` Objekt, das den extrahierten Text enthält. Anschließend durchlaufen Sie jede Seite des Dokuments und verwenden ein`TextDevice` zusammen mit`TextExtractionOptions` um Text von jeder Seite zu extrahieren.

#### F: Wie speichere ich den extrahierten Text in einer Datei?

 A: In Schritt 6 geben Sie den Ausgabedateipfad an und verwenden die`File.WriteAllText`Methode, um den extrahierten Text in einer Textdatei zu speichern.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie gelernt, wie Sie die Text Device-Funktion in Aspose.PDF für .NET nutzen können, um Text aus einem PDF-Dokument zu extrahieren. Der extrahierte Text wurde in einer angegebenen Ausgabedatei gespeichert, sodass Sie den extrahierten Inhalt nach Bedarf bearbeiten und verwenden können.