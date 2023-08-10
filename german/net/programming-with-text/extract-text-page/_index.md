---
title: Textseite extrahieren
linktitle: Textseite extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text aus einer bestimmten Seite eines PDF-Dokuments extrahieren.
type: docs
weight: 200
url: /de/net/programming-with-text/extract-text-page/
---

Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einer bestimmten Seite eines PDF-Dokuments mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

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
using System.IO;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Schritt 5: Extrahieren Sie Text von einer bestimmten Seite
 Ein ... kreieren`TextAbsorber` Objekt zum Extrahieren von Text aus dem Dokument. Akzeptieren Sie den Absorber für die gewünschte Seite, indem Sie über darauf zugreifen`Pages` Sammlung der`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Schritt 6: Holen Sie sich den extrahierten Text
 Greifen Sie auf den extrahierten Text zu`TextAbsorber` Objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Schritt 7: Speichern Sie den extrahierten Text
 Ein ... kreieren`TextWriter` und öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten. Schreiben Sie den extrahierten Text in die Datei und schließen Sie den Stream.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Beispielquellcode für „Textseite extrahieren“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um Text zu extrahieren
TextAbsorber textAbsorber = new TextAbsorber();
//Akzeptieren Sie den Absorber für eine bestimmte Seite
pdfDocument.Pages[1].Accept(textAbsorber);
// Holen Sie sich den extrahierten Text
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Erstellen Sie einen Writer und öffnen Sie die Datei
TextWriter tw = new StreamWriter(dataDir);
// Schreiben Sie eine Textzeile in die Datei
tw.WriteLine(extractedText);
// Schließen Sie den Stream
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Text aus einer bestimmten Seite eines PDF-Dokuments extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.