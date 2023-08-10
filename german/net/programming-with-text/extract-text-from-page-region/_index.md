---
title: Extrahieren Sie Text aus dem Seitenbereich
linktitle: Extrahieren Sie Text aus dem Seitenbereich
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text aus einem bestimmten Bereich auf einer Seite eines PDF-Dokuments extrahieren.
type: docs
weight: 190
url: /de/net/programming-with-text/extract-text-from-page-region/
---

Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einem bestimmten Bereich auf einer Seite eines PDF-Dokuments mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

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
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Schritt 5: Extrahieren Sie Text aus einem Seitenbereich
 Ein ... kreieren`TextAbsorber`Objekt zum Extrahieren von Text aus dem Dokument. Konfigurieren Sie die`TextSearchOptions` um die Suche auf einen bestimmten Seitenbereich zu beschränken, der durch ein Rechteck definiert ist.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Schritt 6: Holen Sie sich den extrahierten Text
 Greifen Sie auf den extrahierten Text zu`TextAbsorber` Objekt.

```csharp
string extractedText = absorb.Text;
```

## Schritt 7: Speichern Sie den extrahierten Text
 Ein ... kreieren`TextWriter` und öffnen Sie die Datei, in der Sie den extrahierten Text speichern möchten. Schreiben Sie den extrahierten Text in die Datei und schließen Sie den Stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Beispielquellcode zum Extrahieren von Text aus dem Seitenbereich mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um Text zu extrahieren
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Akzeptieren Sie den Absorber für die erste Seite
pdfDocument.Pages[1].Accept(absorber);
// Holen Sie sich den extrahierten Text
string extractedText = absorber.Text;
// Erstellen Sie einen Writer und öffnen Sie die Datei
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Schreiben Sie eine Textzeile in die Datei
tw.WriteLine(extractedText);
// Schließen Sie den Stream
tw.Close();
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Text aus einem bestimmten Bereich auf einer Seite eines PDF-Dokuments extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.