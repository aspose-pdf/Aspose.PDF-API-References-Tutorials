---
title: Suchen und Text abrufen Alle
linktitle: Suchen und Text abrufen Alle
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen können.
type: docs
weight: 420
url: /de/net/programming-with-text/search-and-get-text-all/
---
## Einführung

Mussten Sie schon einmal bestimmten Text aus einer PDF-Datei extrahieren, fanden es aber schwierig? PDFs können sich manchmal wie verschlossene Container anfühlen, was es schwierig macht, die benötigten Informationen zu erhalten. Aber hier sind die guten Neuigkeiten: Mit Aspose.PDF für .NET können Sie problemlos Text aus jeder PDF-Datei suchen und abrufen. Diese leistungsstarke Bibliothek bietet alles, was Sie zum Arbeiten mit PDFs in Ihren .NET-Anwendungen benötigen, und macht die Textextraktion zum Kinderspiel. In diesem Tutorial führen wir Sie durch den Prozess des Suchens und Extrahierens von Text aus einer PDF-Datei mit Aspose.PDF für .NET. Egal, ob Sie ein Textanalysetool erstellen oder einfach nur die Datenextraktion aus PDF-Berichten automatisieren müssen, hier sind Sie richtig!

## Voraussetzungen

Bevor wir uns in den Code stürzen, stellen wir sicher, dass Sie alles eingerichtet haben:

1. Aspose.PDF für .NET: Sie müssen Aspose.PDF für .NET herunterladen und installieren. Sie können es von der Download-Seite herunterladen.[Hier](https://releases.aspose.com/pdf/net/).
2. .NET-Umgebung: Stellen Sie sicher, dass auf Ihrem Entwicklungscomputer .NET Framework oder .NET Core eingerichtet ist.
3. Grundlegende C##-Kenntnisse: Einige Kenntnisse in C# und der Arbeit mit .NET-Projekten werden empfohlen.
4.  PDF-Dokument: Eine Beispiel-PDF-Datei, aus der wir Text extrahieren. In diesem Beispiel verwenden wir`SearchAndGetTextFromAll.pdf`.

## Pakete importieren

Bevor Sie Code schreiben, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren, um mit Aspose.PDF zu arbeiten.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Diese Namespaces bieten Zugriff auf das Dokumentobjektmodell des PDF und ermöglichen uns, Text innerhalb der Datei zu bearbeiten.

Lassen Sie uns den Vorgang in einfache Schritte aufteilen, damit Sie ihn problemlos nachvollziehen können.

## Schritt 1: Dokumentverzeichnis festlegen

Als Erstes müssen Sie den Pfad zum Verzeichnis angeben, in dem sich Ihre PDF-Datei befindet. Dies hilft der Anwendung, die Datei zu finden, aus der Sie den Text extrahieren.

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  Der`dataDir` Die Variable sollte auf das Verzeichnis zeigen, in dem Ihr`SearchAndGetTextFromAll.pdf` Datei wird gespeichert.
-  Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad auf Ihrem Computer.

## Schritt 2: Öffnen Sie das PDF-Dokument

Als nächstes öffnen wir das PDF-Dokument mit Aspose.PDF's`Document` Objekt.

```csharp
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Wir erstellen eine neue Instanz des`Document` Klasse, indem Sie den vollständigen Dateipfad der PDF-Datei übergeben.
- Dadurch wird die PDF-Datei in den Speicher geladen und für die Verarbeitung vorbereitet.

## Schritt 3: Erstellen Sie einen Textabsorber

 Der`TextFragmentAbsorber` Objekt wird verwendet, um nach bestimmtem Text im PDF zu suchen. In diesem Fall suchen wir nach dem Wort „Text“.

```csharp
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  Der`TextFragmentAbsorber` wird mit der Zeichenfolge initialisiert`"text"`Das heißt, es wird nach allen Vorkommen des Wortes „Text“ im PDF-Dokument gesucht.

## Schritt 4: Absorber für alle Seiten akzeptieren

Nun weisen wir das PDF-Dokument an, den Absorber zu akzeptieren und auf allen Seiten nach dem Text zu suchen.

```csharp
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  Der`Accept` Die Methode wird auf die Seiten des Dokuments angewendet. Dadurch werden alle Seiten nach dem angegebenen Text durchsucht.

## Schritt 5: Textfragmente extrahieren

Sobald der Absorber das Dokument gescannt hat, können wir die extrahierten Textfragmente abrufen.

```csharp
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  Der`TextFragments` Eigentum der`TextFragmentAbsorber` Gibt eine Sammlung aller Textfragmente zurück, die dem Suchbegriff entsprechen.

## Schritt 6: Durchlaufen der Textfragmente

Da wir nun über die Sammlung von Textfragmenten verfügen, werden wir diese durchlaufen und die Details extrahieren.

```csharp
// Durchlaufen der Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  Der`foreach` Schleife durchläuft jede`TextFragment` in der Sammlung.
- Wir drucken verschiedene Eigenschaften jedes Fragments, beispielsweise den eigentlichen Text, seine Position auf der Seite, Schriftdetails und Schriftgröße.
-  Der`XIndent` Und`YIndent` Eigenschaften geben die genauen Koordinaten des Textfragments innerhalb des PDFs an.

## Abschluss

Und da haben Sie es! Mit nur wenigen Codezeilen haben wir mit Aspose.PDF für .NET erfolgreich Text aus einer PDF-Datei gesucht und extrahiert. Die Flexibilität von Aspose.PDF ermöglicht es Ihnen, PDF-Dateien auf zahlreiche Arten zu bearbeiten, was es zu einer hervorragenden Wahl für Entwickler macht, die robuste PDF-Lösungen in .NET-Umgebungen benötigen. Sie können dieses Beispiel problemlos erweitern, um nach anderen Wörtern zu suchen, weitere Details zu extrahieren oder sogar den PDF-Inhalt nach Ihren Anforderungen zu bearbeiten. Hoffentlich hat Ihnen dieser Leitfaden einen klaren und unkomplizierten Ansatz für die Arbeit mit PDF-Dateien vermittelt. Probieren Sie es mit Ihren eigenen PDF-Dateien aus!

## Häufig gestellte Fragen

### Kann ich nach mehreren Wörtern gleichzeitig suchen?  
 Ja, Sie können die`TextFragmentAbsorber` um nach mehreren Phrasen zu suchen, indem Sie die Suchzeichenfolge entsprechend anpassen.

### Was ist, wenn der Text mehrere Zeilen umfasst?  
Aspose.PDF erkennt und extrahiert Text auch dann noch, wenn er sich über mehrere Zeilen erstreckt. Sie können diese Fragmente einzeln behandeln.

### Wie speichere ich den extrahierten Text in einer Datei?  
 Sie können den extrahierten Text mithilfe von Standard-Datei-E/A-Operationen in C# in eine Datei schreiben, wie zum Beispiel:`StreamWriter`.

### Unterstützt Aspose.PDF das Extrahieren von Text aus gescannten PDFs?  
Aspose.PDF unterstützt keine OCR. Für gescannte PDFs benötigen Sie ein OCR-Tool, um den Text zu erkennen.

### Wie gehe ich mit verschlüsselten PDFs um?  
Wenn Ihre PDF-Datei passwortgeschützt ist, können Sie sie mit Aspose.PDF entsperren, indem Sie beim Laden des Dokuments das Passwort eingeben.