---
title: Text durchsuchen und Rechteck zeichnen
linktitle: Text durchsuchen und Rechteck zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie in einer PDF-Datei nach Text suchen, Rechtecke um den gefundenen Text zeichnen und das geänderte Dokument mit Aspose.PDF für .NET speichern.
type: docs
weight: 460
url: /de/net/programming-with-text/search-text-and-draw-rectangle/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET nach einem bestimmten Text in einem PDF-Dokument suchen, ein Rechteck um den gefundenen Text zeichnen und das geänderte Dokument speichern. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website herunterladen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Richten Sie das Projekt ein

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu.

## Schritt 2: Importieren Sie die erforderlichen Namespaces

Fügen Sie am Anfang Ihrer C#-Datei die folgenden using-Anweisungen hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit`Document` Klasse:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Ersetzen`"SearchAndGetTextFromAll.pdf"` mit dem tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 5: Erstellen Sie einen TextFragmentAbsorber

 Ein ... kreieren`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen Suchbegriffs zu finden:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Ersetzen`@"[\S]+"` mit Ihrem gewünschten Muster für reguläre Ausdrücke.

## Schritt 6: Aktivieren Sie die Suche nach regulären Ausdrücken

Aktivieren Sie die Suche nach regulären Ausdrücken, indem Sie Folgendes festlegen`TextSearchOptions` Eigenschaft des Absorbers:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Schritt 7: Suchen Sie auf allen Seiten

Akzeptieren Sie den Absorber für alle Seiten des Dokuments:

```csharp
document.Pages.Accept(textAbsorber);
```

## Schritt 8: Zeichnen Sie ein Rechteck um den gefundenen Text

 Ein ... kreieren`PdfContentEditor` Objekt und durchlaufen Sie die abgerufenen Textfragmente, wobei Sie ein Rechteck um jedes Textsegment zeichnen:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Schritt 9: Speichern Sie das geänderte Dokument

Speichern Sie das geänderte Dokument:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Unbedingt austauschen`"SearchTextAndDrawRectangle_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text suchen und Rechteck zeichnen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach einem bestimmten Text in einem PDF-Dokument suchen, ein Rechteck um den gefundenen Text zeichnen und das geänderte Dokument speichern. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zur Durchführung der erforderlichen Aktionen. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um Text zu bearbeiten und Rechtecke in PDF-Dateien zu zeichnen.