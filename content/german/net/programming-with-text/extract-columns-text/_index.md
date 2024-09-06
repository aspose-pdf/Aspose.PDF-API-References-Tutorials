---
title: Spaltentext in PDF-Datei extrahieren
linktitle: Spaltentext in PDF-Datei extrahieren
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Spaltentext aus einer PDF-Datei extrahieren.
type: docs
weight: 150
url: /de/net/programming-with-text/extract-columns-text/
---
Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Spaltentext in PDF-Dateien mit Aspose.PDF für .NET. Der bereitgestellte C#-Quellcode demonstriert die erforderlichen Schritte.

## Anforderungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Visual Studio oder ein anderer C#-Compiler muss auf Ihrem Computer installiert sein.
- Aspose.PDF für .NET-Bibliothek. Sie können es von der offiziellen Aspose-Website herunterladen oder einen Paketmanager wie NuGet verwenden, um es zu installieren.

## Schritt 1: Einrichten des Projekts
1. Erstellen Sie ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung.
2. Fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren
Fügen Sie in der Codedatei, aus der Sie Spaltentext extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven hinzu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Schritt 3: Dokumentverzeichnis festlegen
 Suchen Sie im Code nach der Zeile, die besagt:`string dataDir = "YOUR DOCUMENT DIRECTORY";` und ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den Pfad zum Verzeichnis, in dem Ihre Dokumente gespeichert sind.

## Schritt 4: Öffnen Sie das PDF-Dokument
 Öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Übergabe des Pfads zur Eingabe-PDF-Datei.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Schritt 5: Passen Sie die Schriftgröße an
Reduzieren Sie die Schriftgröße der Textfragmente um den Faktor 0,7, um die Lesbarkeit zu verbessern und spaltenförmigen Text besser darzustellen.

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
 Speichern Sie das geänderte PDF-Dokument in einem Speicherstream und laden Sie es als neues Dokument erneut. Verwenden Sie dann die`TextAbsorber` Klasse zum Extrahieren von Text aus den Spalten.

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
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Die Schriftgröße muss um mindestens 70 % reduziert werden
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
Sie haben erfolgreich Spaltentext aus einem PDF-Dokument mit Aspose.PDF für .NET extrahiert. Der extrahierte Text wurde in der angegebenen Ausgabedatei gespeichert.

### Häufig gestellte Fragen

#### F: Was ist der Zweck dieses Tutorials?

A: Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung zum Extrahieren von Textspalten aus einer PDF-Datei mit Aspose.PDF für .NET. Der zugehörige C#-Quellcode bietet eine praktische Demonstration der erforderlichen Verfahren.

#### F: Welche Namespaces soll ich importieren?

A: Fügen Sie in der Codedatei, aus der Sie Textspalten extrahieren möchten, am Anfang der Datei die folgenden Using-Direktiven ein:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### F: Wie gebe ich das Dokumentverzeichnis an?

 A: Suchen Sie die Linie`string dataDir = "YOUR DOCUMENT DIRECTORY";` im Code und ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

#### F: Wie öffne ich ein vorhandenes PDF-Dokument?

 A: In Schritt 4 öffnen Sie ein vorhandenes PDF-Dokument mit dem`Document` Konstruktor und Bereitstellung des Pfads zur Eingabe-PDF-Datei.

#### F: Warum wird die Schriftgröße angepasst?

A: In Schritt 5 wird die Schriftgröße von Textfragmenten um den Faktor 0,7 reduziert. Diese Anpassung verbessert die Lesbarkeit und stellt spaltenförmigen Text genauer dar.

#### F: Wie extrahiere ich Text aus Spalten?

 A: Schritt 6 besteht darin, das geänderte PDF-Dokument in einem Speicherstrom zu speichern, es als neues Dokument neu zu laden und dann mit dem`TextAbsorber` Klasse zum Extrahieren von Text aus den Spalten.

#### F: Zu welchem Zweck wird der extrahierte Text gespeichert?

A: In Schritt 7 speichern Sie den extrahierten Text in einer Textdatei im angegebenen Ausgabedateipfad.

#### F: Warum die Schriftgröße vor dem Extrahieren reduzieren?

A: Durch die Reduzierung der Schriftgröße wird sichergestellt, dass der extrahierte Text richtig in den Spalten ausgerichtet wird, wodurch eine genauere Darstellung des ursprünglichen Layouts ermöglicht wird.

#### F: Was ist die wichtigste Erkenntnis aus diesem Tutorial?

A: Durch das Durcharbeiten dieses Tutorials haben Sie sich das nötige Wissen und die Fähigkeiten angeeignet, um mit Aspose.PDF für .NET Textspalten aus einem PDF-Dokument zu extrahieren. Der resultierende Text wurde in der angegebenen Ausgabedatei gespeichert.