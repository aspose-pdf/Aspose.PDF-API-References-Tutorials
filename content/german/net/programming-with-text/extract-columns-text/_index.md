---
title: Extrahieren Sie Spaltentext in einer PDF-Datei
linktitle: Extrahieren Sie Spaltentext in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Spaltentext in einer PDF-Datei extrahieren.
type: docs
weight: 150
url: /de/net/programming-with-text/extract-columns-text/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Spaltentext in einer PDF-Datei mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die notwendigen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer auf Ihrem Computer installierter C#-Compiler.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Richten Sie das Projekt ein
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, in die Sie den Spaltentext extrahieren möchten, am Anfang der Datei die folgenden using-Anweisungen hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Schritt 3: Legen Sie das Dokumentverzeichnis fest
 Suchen Sie im Code die Zeile mit der Aufschrift`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem Pfad zu dem Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit`Document`Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Schritt 5: Passen Sie die Schriftgröße an
Reduzieren Sie die Schriftgröße der Textfragmente um den Faktor 0,7, um die Lesbarkeit zu verbessern und Spaltentext besser darzustellen.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Schritt 6: Text aus Spalten extrahieren
 Speichern Sie das geänderte PDF-Dokument in einem Speicherstream und laden Sie es als neues Dokument erneut. Dann verwenden Sie die`TextAbsorber` Klasse zum Extrahieren von Text aus den Spalten.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Schritt 7: Speichern Sie den extrahierten Text
Speichern Sie den extrahierten Text in einer Textdatei im angegebenen Ausgabedateipfad.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Beispielquellcode zum Extrahieren von Spaltentext mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Die Schriftgröße muss um mindestens 70 % reduziert werden.
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Abschluss
Sie haben mit Aspose.PDF für .NET erfolgreich Spaltentext aus einem PDF-Dokument extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.

### FAQs

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung zum Extrahieren von Textspalten aus einer PDF-Datei mit Aspose.PDF für .NET. Der beigefügte C#-Quellcode bietet eine praktische Demonstration der erforderlichen Vorgehensweisen.

#### F: Welche Namespaces sollte ich importieren?

A: Fügen Sie in der Codedatei, in der Sie Textspalten extrahieren möchten, die folgenden using-Anweisungen am Anfang der Datei ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### F: Wie lege ich das Dokumentenverzeichnis fest?

 A: Suchen Sie die Zeile`string dataDir = "YOUR DOCUMENT DIRECTORY";` im Code einfügen und ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit`Document` Konstruktor und stellt den Pfad zur Eingabe-PDF-Datei bereit.

#### F: Warum wird die Schriftgröße angepasst?

A: Schritt 5 besteht darin, die Schriftgröße von Textfragmenten um den Faktor 0,7 zu reduzieren. Diese Anpassung verbessert die Lesbarkeit und stellt Spaltentext genauer dar.

#### F: Wie extrahiere ich Text aus Spalten?

 A: Schritt 6 besteht darin, das geänderte PDF-Dokument in einem Speicherstream zu speichern, es als neues Dokument erneut zu laden und dann das zu verwenden`TextAbsorber` Klasse zum Extrahieren von Text aus den Spalten.

#### F: Zu welchem Zweck wird der extrahierte Text gespeichert?

A: In Schritt 7 speichern Sie den extrahierten Text in einer Textdatei im angegebenen Ausgabedateipfad.

#### F: Warum die Schriftgröße vor der Extraktion reduzieren?

A: Durch die Reduzierung der Schriftgröße wird sichergestellt, dass der extrahierte Text ordnungsgemäß in den Spalten ausgerichtet wird, wodurch eine genauere Darstellung des ursprünglichen Layouts gewährleistet wird.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch das Befolgen dieses Tutorials haben Sie sich die Kenntnisse und Fähigkeiten angeeignet, die zum Extrahieren von Textspalten aus einem PDF-Dokument mit Aspose.PDF für .NET erforderlich sind. Der resultierende Text wurde in der angegebenen Ausgabedatei gespeichert.