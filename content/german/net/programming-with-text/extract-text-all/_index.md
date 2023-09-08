---
title: Extrahieren Sie den gesamten Text in einer PDF-Datei
linktitle: Extrahieren Sie Text in eine PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text in einer PDF-Datei extrahieren.
type: docs
weight: 180
url: /de/net/programming-with-text/extract-text-all/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens des gesamten Textes in einer PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

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
 Öffnen Sie ein vorhandenes PDF-Dokument mit`Document`Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Schritt 5: Extrahieren Sie den gesamten Text
 Ein ... kreieren`TextAbsorber`Objekt zum Extrahieren von Text aus dem Dokument. Akzeptieren Sie dann die Seite für alle Seiten.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Schritt 6: Holen Sie sich den extrahierten Text
 Greifen Sie auf den extrahierten Text zu`TextAbsorber` Objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Schritt 7: Speichern Sie den extrahierten Text
 Ein ... kreieren`TextWriter` und öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten. Schreiben Sie den extrahierten Text in die Datei und schließen Sie den Stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Beispielquellcode für Extract Text All mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um Text zu extrahieren
TextAbsorber textAbsorber = new TextAbsorber();
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textAbsorber);
// Holen Sie sich den extrahierten Text
string extractedText = textAbsorber.Text;
// Erstellen Sie einen Writer und öffnen Sie die Datei
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Schreiben Sie eine Textzeile in die Datei
tw.WriteLine(extractedText);
// Schließen Sie den Stream
tw.Close();
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich den gesamten Text aus einem PDF-Dokument extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial dient als Anleitung zum Extrahieren des gesamten Textes aus einer PDF-Datei mit Aspose.PDF für .NET. Der beigefügte C#-Quellcode bietet Schritt-für-Schritt-Anleitungen zur Lösung dieser Aufgabe.

#### F: Welche Namespaces sollte ich importieren?

A: Fügen Sie in der Codedatei, in der Sie Text extrahieren möchten, die folgenden using-Anweisungen am Anfang der Datei ein:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` im Code einfügen und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und stellt den Pfad zur Eingabe-PDF-Datei bereit.

#### F: Wie extrahiere ich den gesamten Text aus dem Dokument?

 A: Schritt 5 umfasst die Erstellung eines`TextAbsorber` Objekt zum Extrahieren von Text aus dem PDF-Dokument. Dann erhalten Sie die Seite für alle Seiten.

#### F: Wie greife ich auf den extrahierten Text zu?

 A: Schritt 6 führt Sie durch den Zugriff auf den extrahierten Text aus`TextAbsorber` Objekt.

#### F: Wie speichere ich den extrahierten Text in einer Datei?

 A: In Schritt 7 erstellen Sie eine`TextWriter`, öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten, schreiben Sie den extrahierten Text in die Datei und schließen Sie dann den Stream.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch Befolgen dieses Tutorials haben Sie gelernt, wie Sie mit Aspose.PDF für .NET den gesamten Text aus einem PDF-Dokument extrahieren. Der extrahierte Text wurde in einer angegebenen Ausgabedatei gespeichert, sodass Sie den Textinhalt des Dokuments analysieren und bearbeiten können.