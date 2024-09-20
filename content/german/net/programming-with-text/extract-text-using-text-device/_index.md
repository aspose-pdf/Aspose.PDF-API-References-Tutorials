---
title: Extrahieren Sie Text mit dem Textgerät
linktitle: Extrahieren Sie Text mit dem Textgerät
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit dem Textgerät in Aspose.PDF für .NET Text aus einem PDF-Dokument extrahieren.
type: docs
weight: 210
url: /de/net/programming-with-text/extract-text-using-text-device/
---
## Einführung

Das Extrahieren von Text aus einer PDF-Datei kann schwierig sein, insbesondere bei Dokumenten mit verschiedenen Formaten, eingebetteten Schriftarten oder komplexen Layouts. Aber mit Aspose.PDF für .NET wird dieser Vorgang zum Kinderspiel! Egal, ob Sie Seiten einer PDF-Datei zur weiteren Analyse in Klartext umwandeln oder einfach nur bestimmte Abschnitte extrahieren möchten, Aspose.PDF bietet Ihnen alles. In diesem Tutorial erklären wir Schritt für Schritt, wie Sie mit der Klasse TextDevice in Aspose.PDF Text aus einer PDF-Datei extrahieren. Wir bieten auch klare Erklärungen, damit Sie dieselben Methoden problemlos auf Ihre eigenen Projekte anwenden können.

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen Sie sicher, dass Sie alles haben, um mitmachen zu können. Folgendes benötigen Sie:

1.  Aspose.PDF für .NET: Laden Sie die neueste Version von der[Aspose.PDF für .NET-Downloadseite](https://releases.aspose.com/pdf/net/).
2. Entwicklungsumgebung: Visual Studio oder eine andere C#-Entwicklungsumgebung.
3. .NET Framework: Stellen Sie sicher, dass Ihr Projekt auf .NET Framework 4.x oder höher abzielt.
4. Eingabe-PDF-Datei: Eine PDF-Datei, die Sie zur Textextraktion verwenden. Legen Sie diese in einem Verzeichnis auf Ihrem Computer ab (wir nennen dies`YOUR DOCUMENT DIRECTORY`).

## Pakete importieren

Oben in Ihrem Code müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.PDF zu arbeiten:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Schritt 1: Laden Sie Ihr PDF-Dokument

 Bevor wir Text extrahieren, müssen wir das PDF-Dokument in den Speicher laden. In diesem Schritt öffnen Sie Ihr PDF mit Aspose.PDFs`Document` Klasse. Dadurch können Sie auf alle Seiten und Inhalte in der Datei zugreifen.

```csharp
// Definieren Sie den Pfad zu Ihrem PDF-Dokument
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laden Sie das PDF-Dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Hier verwenden wir`Document pdfDocument = new Document(dataDir + "input.pdf");` , um das PDF zu laden.`dataDir` enthält den Verzeichnispfad Ihrer PDF-Datei. Dadurch erhalten wir Zugriff auf das gesamte Dokument, können die Seiten durchlaufen und Inhalte extrahieren.

## Schritt 2: Einrichten eines String Builders zur Textspeicherung

 Nachdem das Dokument geladen ist, benötigen wir eine Möglichkeit, den extrahierten Text zu speichern. Dazu verwenden wir ein`StringBuilder` was eine effiziente Zeichenkettenverkettung ermöglicht.

```csharp
// StringBuilder zum Speichern des extrahierten Textes
StringBuilder builder = new StringBuilder();
```

 Wir initialisieren eine`StringBuilder`Instanz, die den von jeder Seite extrahierten Text sammelt. Dies ist eine effizientere Möglichkeit, große Zeichenfolgen zu verarbeiten als die normale Zeichenfolgenverkettung in einer Schleife.

## Schritt 3: Durch PDF-Seiten blättern

 Als nächstes durchlaufen wir jede Seite des PDF-Dokuments, um den Text zu extrahieren. Wir verarbeiten jede Seite einzeln mit dem`TextDevice` Klasse, die für die Konvertierung des PDF-Inhalts in das Textformat verantwortlich ist.

```csharp
// Durchlaufen Sie alle Seiten im PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Verarbeiten Sie jede Seite zur Textextraktion
}
```

Diese Schleife durchläuft jede Seite des PDFs (`pdfDocument.Pages` ). Für jede Seite extrahieren wir den Text und fügen ihn zu unserem`StringBuilder`.

## Schritt 4: Text von jeder Seite extrahieren

 Nun richten wir den Textextraktionsprozess für jede Seite ein. Hier erstellen wir eine`TextDevice` Objekt und verwenden Sie es zur Verarbeitung der PDF-Seiten. Das`TextDevice` extrahiert Rohtext oder formatierten Text basierend auf den von uns festgelegten Extraktionsoptionen.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Erstellen eines Textgeräts zur Textextraktion
    TextDevice textDevice = new TextDevice();
    
    // Textextraktionsoptionen auf „Pure“-Modus setzen
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Extrahieren Sie Text von der aktuellen Seite und speichern Sie ihn im Speicherstream
    textDevice.Process(pdfPage, textStream);

    // Speicherstrom in Text umwandeln
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Den extrahierten Text an den StringBuilder anhängen
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : Der`TextDevice` Klasse wird verwendet, um Text aus der PDF-Datei zu extrahieren.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Diese Option extrahiert den Rohtext, ohne Formatierungen wie Schriftarten oder Positionen beizubehalten. Sie können auch`TextFormattingMode.Raw` wenn Sie mehr Kontrolle über die Formatierung benötigen.
- `textDevice.Process(pdfPage, textStream);` : Dadurch wird jede Seite des PDFs verarbeitet und der extrahierte Text in einem`MemoryStream`.
-  Zum Schluss konvertieren wir den Text aus dem`MemoryStream` in einen String und hängen Sie ihn an den`StringBuilder`.

## Schritt 5: Extrahierten Text in einer Datei speichern

 Nach der Verarbeitung aller Seiten wird der Text im`StringBuilder`Der letzte Schritt besteht darin, den extrahierten Text in einer Datei zu speichern.

```csharp
// Definieren Sie den Ausgabepfad für die Textdatei
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Speichern Sie den extrahierten Text in einer Datei
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Dies schreibt den gesamten Inhalt der`StringBuilder` in eine Textdatei.
- Der Pfad für die Ausgabedatei wird durch Anhängen eines Dateinamens (`"input_Text_Extracted_out.txt"` ) zur`dataDir` Weg.

## Abschluss

Das Extrahieren von Text aus einer PDF-Datei mit Aspose.PDF für .NET ist ein einfacher und effizienter Vorgang. Indem Sie die in diesem Handbuch beschriebenen Schritte befolgen, können Sie problemlos PDF-Dokumente öffnen, Seiten durchlaufen und Text in eine Textdatei extrahieren. Dies ist besonders nützlich für die Verarbeitung großer Mengen von PDF-Daten, die Durchführung von Textanalysen oder die Konvertierung von Dokumenten zur weiteren Bearbeitung.

Mit Aspose.PDF sind Sie nicht auf die Textextraktion beschränkt – Sie können Anmerkungen verarbeiten, Bilder bearbeiten oder sogar PDFs in andere Formate wie HTML oder Word konvertieren. Die Flexibilität und Leistungsfähigkeit dieser Bibliothek machen sie zu einem unschätzbaren Werkzeug für die PDF-Verwaltung in .NET-Anwendungen.

## Häufig gestellte Fragen

### Kann Aspose.PDF Text aus bildbasierten PDFs extrahieren?
Nein, Aspose.PDF ist dafür gedacht, Text aus inhaltsbasierten PDFs zu extrahieren. Für bildbasierte PDFs wird OCR-Technologie benötigt.

### Behält Aspose.PDF die Formatierung beim Extrahieren von Text bei?
Standardmäßig wird der Text ohne Formatierung extrahiert, Sie können die Extraktionsoptionen jedoch anpassen, wenn Sie einen Teil der Formatierung beibehalten möchten.

### Kann ich Text aus einem bestimmten Seitenbereich extrahieren?
Ja, Sie können den Code so ändern, dass er eine Schleife über einen bestimmten Seitenbereich statt über alle Seiten durchführt.

### Was sind die Textextraktionsmodi in Aspose.PDF?
Aspose.PDF bietet zwei Modi: Raw und Pure. Der Raw-Modus versucht, das ursprüngliche Layout beizubehalten, während der Pure-Modus nur den Text ohne Formatierung extrahiert.

### Ist Aspose.PDF für .NET mit .NET Core kompatibel?
Ja, Aspose.PDF für .NET ist vollständig kompatibel mit .NET Core und .NET Framework.