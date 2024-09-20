---
title: Suchen und Abrufen einer Textseite in einer PDF-Datei
linktitle: Suchen und Abrufen einer Textseite in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf einer bestimmten Seite einer PDF-Datei suchen und abrufen können.
type: docs
weight: 430
url: /de/net/programming-with-text/search-and-get-text-page/
---
## Einführung

Mussten Sie schon einmal in einem PDF-Dokument nach einem bestimmten Text suchen und ihn zur weiteren Verwendung extrahieren? Vielleicht erstellen Sie eine App, die Dokumente verarbeitet und eine präzise Datenextraktion erfordert, oder Sie müssen PDFs einfach nur effizient analysieren. Was auch immer Ihr Fall sein mag, Sie sind hier richtig! In diesem Tutorial erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Text auf einer Seite in einer PDF-Datei suchen und ihn abrufen können. Egal, ob Sie Anfänger oder erfahrener Entwickler sind, diese Anleitung führt Sie auf unterhaltsame und ansprechende Weise durch jeden Schritt. Bereit loszulegen? Dann legen wir los!

## Voraussetzungen

Bevor wir mit dem Programmieren beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:

1.  Aspose.PDF für .NET-Bibliothek: Sie können es herunterladen von[Hier](https://releases.aspose.com/pdf/net/) oder holen Sie sich über denselben Link eine kostenlose Testversion. Um eine zu kaufen, gehen Sie zu[Aspose-Shop](https://purchase.aspose.com/buy).
2. .NET Framework: Sie benötigen eine funktionierende .NET-Entwicklungsumgebung wie Visual Studio.
3. Eine PDF-Datei: Sie benötigen eine Beispiel-PDF-Datei, in der wir den Text suchen und extrahieren können. Nehmen wir für dieses Tutorial an, dass die Datei den Namen hat`SearchAndGetTextPage.pdf`.

## Pakete importieren

Als Erstes müssen wir die erforderlichen Namespaces importieren, um mit Aspose.PDF für .NET zu arbeiten. Stellen Sie sicher, dass diese oben in Ihrem Code enthalten sind.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Nachdem wir nun die Voraussetzungen geklärt haben, wollen wir den Code Schritt für Schritt aufschlüsseln. Jeder Schritt ist klar umrissen, damit er leicht nachvollziehbar ist.

## Schritt 1: Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest

Bevor Sie mit Ihrem PDF interagieren, müssen Sie den Pfad angeben, unter dem Ihr PDF-Dokument gespeichert ist. Dadurch wird sichergestellt, dass das Programm auf die Datei zugreifen kann.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Dies ist der Pfad zum Ordner, in dem Ihre PDF-Dateien gespeichert sind. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad, in dem sich das PDF befindet.

## Schritt 2: Laden Sie das PDF-Dokument

Der nächste Schritt besteht darin, das PDF-Dokument in den Speicher zu laden, damit Sie damit arbeiten können. So geht's:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Dokument: Dies ist die Aspose.PDF-Klasse, die die PDF-Datei lädt.
- pdfDocument: Die Variable, in der Ihre PDF-Datei nach dem Laden gespeichert wird.

## Schritt 3: Erstellen Sie ein Text Absorber-Objekt

 Der`TextFragmentAbsorber`Mit dieser Klasse können Sie nach bestimmtem Text in der PDF-Datei suchen. Lassen Sie uns eine Instanz dieser Klasse erstellen, um alle Instanzen einer bestimmten Suchphrase zu finden.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Diese Klasse ist für das Suchen und Extrahieren von Text aus der PDF-Datei verantwortlich.
- „Abbildung“: Ersetzen Sie dies durch einen beliebigen Text, nach dem Sie im PDF suchen möchten.

## Schritt 4: Den Text Absorber auf die gesamte PDF-Datei anwenden

Sobald der Textabsorber eingerichtet ist, müssen Sie dem Programm sagen, dass es alle Seiten der PDF-Datei durchsuchen soll.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Diese Methode wendet den Textabsorber auf das PDF an und durchsucht jede Seite nach dem von Ihnen angegebenen Text.

## Schritt 5: Den extrahierten Text abrufen und durchlaufen

Nachdem wir das PDF gescannt haben, ist es an der Zeit, die Ergebnisse abzurufen und anzuzeigen. Wir durchlaufen die extrahierten Textfragmente in einer Schleife.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Diese Sammlung enthält alle Instanzen der vom Textabsorber gefundenen Textfragmente.

## Schritt 6: Durchlaufen Sie jedes Fragment und extrahieren Sie Daten

Wir durchlaufen nun die`textFragmentCollection` und extrahieren Sie verschiedene Eigenschaften jedes Textsegments, wie etwa seine Position, Schriftdetails und Farbe.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: Jedes Fragment enthält Teile des gefundenen Textes.
- Textsegment: Jedes Fragment kann mehrere Segmente haben, die unterschiedliche Teile des Textes darstellen.
- TextState: Bietet detaillierte Informationen zu Schriftart, Größe und Farbe des Textes.

In dieser Schleife drucken wir Details wie den eigentlichen Text, seine Position (X- und Y-Koordinaten), die Schriftart, ob die Schriftart in das PDF eingebettet ist und die Vordergrundfarbe des Textes aus.

## Abschluss

Und da haben Sie es! Sie haben jetzt erfolgreich mit Aspose.PDF für .NET nach Text in einer PDF-Datei gesucht und diesen extrahiert. Es ist unglaublich, wie viel Flexibilität Sie mit dieser Bibliothek haben. Ob Sie in einem großen Dokument nach bestimmtem Text suchen, ihn extrahieren oder seine Eigenschaften analysieren müssen, Aspose.PDF macht es zu einem Kinderspiel. Und mit dem Code, den wir behandelt haben, sind Sie gut gerüstet, um ihn an Ihre Bedürfnisse anzupassen. 

## Häufig gestellte Fragen

### Kann ich nach mehreren Phrasen gleichzeitig suchen?  
 Ja, Sie können den Code so ändern, dass nach mehreren Phrasen gesucht wird, indem Sie mehrere`TextFragmentAbsorber` Objekte.

### Wie kann ich Text von einer bestimmten Seite extrahieren?  
 Sie können eine bestimmte Seite ansprechen, indem Sie den`TextFragmentAbsorber` auf eine einzelne Seite anstatt auf das gesamte Dokument. Beispiel:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Ist Aspose.PDF für .NET kostenlos?  
 Aspose.PDF ist ein kommerzielles Produkt, aber Sie können es mit einem[Kostenlose Testversion](https://releases.aspose.com/).

### Kann ich mit Aspose.PDF Bilder aus dem PDF extrahieren?  
 Ja, Aspose.PDF ermöglicht es Ihnen, neben Text auch Bilder zu extrahieren. Überprüfen Sie die[Dokumentation](https://reference.aspose.com/pdf/net/) für weitere Details.

### Was ist, wenn ich weitere Hilfe oder Unterstützung benötige?  
 Hilfe erhalten Sie jederzeit vom[Aspose Support Forum](https://forum.aspose.com/c/pdf/10).