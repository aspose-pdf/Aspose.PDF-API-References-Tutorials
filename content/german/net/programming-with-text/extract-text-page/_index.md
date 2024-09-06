---
title: Textseite in PDF-Datei extrahieren
linktitle: Textseite in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text aus einer bestimmten Seite einer PDF-Datei extrahieren.
type: docs
weight: 200
url: /de/net/programming-with-text/extract-text-page/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einer bestimmten Seite in einer PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

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
using System.IO;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Schritt 5: Text von einer bestimmten Seite extrahieren
 Erstellen Sie ein`TextAbsorber` Objekt, um Text aus dem Dokument zu extrahieren. Akzeptieren Sie den Absorber für die gewünschte Seite, indem Sie ihn über das`Pages` Sammlung der`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Schritt 6: Den extrahierten Text abrufen
 Zugriff auf den extrahierten Text aus dem`TextAbsorber` Objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Schritt 7: Speichern Sie den extrahierten Text
 Erstellen Sie ein`TextWriter` und öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten. Schreiben Sie den extrahierten Text in die Datei und schließen Sie den Stream.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Beispielquellcode zum Extrahieren von Textseiten mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
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

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einer bestimmten Seite in einer PDF-Datei mit Aspose.PDF für .NET. Der begleitende C#-Quellcode demonstriert die erforderlichen Schritte zum Erfüllen dieser Aufgabe.

#### F: Welche Namespaces soll ich importieren?

A: Fügen Sie in der Codedatei, aus der Sie Text extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven ein:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Bereitstellung des Pfads zur Eingabe-PDF-Datei.

#### F: Wie extrahiere ich Text von einer bestimmten Seite?

 A: Schritt 5 umfasst die Erstellung eines`TextAbsorber` Objekt, um Text aus dem PDF-Dokument zu extrahieren. Anschließend akzeptieren Sie den Absorber für die gewünschte Seite, indem Sie über das`Pages` Sammlung der`pdfDocument`.

#### F: Wie greife ich auf den extrahierten Text zu?

 A: Schritt 6 führt Sie durch den Zugriff auf den extrahierten Text aus dem`TextAbsorber` Objekt.

#### F: Wie speichere ich den extrahierten Text in einer Datei?

 A: In Schritt 7 erstellen Sie eine`TextWriter`, öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten, schreiben Sie den extrahierten Text in die Datei und schließen Sie dann den Stream.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.PDF für .NET Text aus einer bestimmten Seite eines PDF-Dokuments extrahieren. Der extrahierte Text wurde in einer angegebenen Ausgabedatei gespeichert, sodass Sie Textinhalte von bestimmten Seiten gezielt ansprechen und analysieren können.