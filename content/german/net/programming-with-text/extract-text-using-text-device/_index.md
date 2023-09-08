---
title: Extrahieren Sie Text mit einem Textgerät
linktitle: Extrahieren Sie Text mit einem Textgerät
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit dem Textgerät in Aspose.PDF für .NET Text aus einem PDF-Dokument extrahieren.
type: docs
weight: 210
url: /de/net/programming-with-text/extract-text-using-text-device/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einem PDF-Dokument mithilfe des Textgeräts in Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie Text extrahieren möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit`Document`Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Schritt 5: Extrahieren Sie Text mit dem Textgerät
 Ein ... kreieren`StringBuilder` Objekt, das den extrahierten Text enthält. Durchlaufen Sie jede Seite des Dokuments und verwenden Sie a`TextDevice` um den Text von jeder Seite zu extrahieren.

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
 Geben Sie den Pfad der Ausgabedatei an und speichern Sie den extrahierten Text mithilfe von in einer Textdatei`File.WriteAllText` Methode.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Beispielquellcode für Extract Text Using Text Device mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Zeichenfolge zum Speichern des extrahierten Texts
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Textgerät erstellen
		TextDevice textDevice = new TextDevice();
		// Textextraktionsoptionen festlegen – Textextraktionsmodus festlegen (Raw oder Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Konvertieren Sie eine bestimmte Seite und speichern Sie Text im Stream
		textDevice.Process(pdfPage, textStream);
		// Konvertieren Sie eine bestimmte Seite und speichern Sie Text im Stream
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Speicherstrom schließen
		textStream.Close();
		// Holen Sie sich Text aus dem Speicherstream
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
Sie haben mit dem Textgerät in Aspose.PDF für .NET erfolgreich Text aus einem PDF-Dokument extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial bietet Anleitungen zum Extrahieren von Text aus einem PDF-Dokument mithilfe der Textgerätefunktion in Aspose.PDF für .NET. Der beigefügte C#-Quellcode demonstriert die notwendigen Schritte, um diese Aufgabe zu erfüllen.

#### F: Welche Namespaces sollte ich importieren?

A: Fügen Sie in der Codedatei, in der Sie Text extrahieren möchten, die folgenden using-Anweisungen am Anfang der Datei ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und stellt den Pfad zur Eingabe-PDF-Datei bereit.

#### F: Wie extrahiere ich Text mit dem Textgerät?

 A: Schritt 5 umfasst die Erstellung eines`StringBuilder` Objekt, das den extrahierten Text enthält. Anschließend durchlaufen Sie jede Seite des Dokuments und verwenden a`TextDevice` zusammen mit`TextExtractionOptions` um Text von jeder Seite zu extrahieren.

#### F: Wie speichere ich den extrahierten Text in einer Datei?

 A: In Schritt 6 geben Sie den Pfad der Ausgabedatei an und verwenden den`File.WriteAllText`Methode zum Speichern des extrahierten Textes in einer Textdatei.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch die Befolgung dieses Tutorials haben Sie gelernt, wie Sie die Textgerätefunktion in Aspose.PDF für .NET nutzen, um Text aus einem PDF-Dokument zu extrahieren. Der extrahierte Text wurde in einer bestimmten Ausgabedatei gespeichert, sodass Sie den extrahierten Inhalt nach Bedarf bearbeiten und nutzen können.