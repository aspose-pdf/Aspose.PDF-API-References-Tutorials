---
title: Text suchen und Rechteck zeichnen
linktitle: Text suchen und Rechteck zeichnen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Text in einer PDF-Datei suchen, Rechtecke um den gefundenen Text zeichnen und das geänderte Dokument speichern.
type: docs
weight: 460
url: /de/net/programming-with-text/search-text-and-draw-rectangle/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET nach bestimmtem Text in einem PDF-Dokument suchen, ein Rechteck um den gefundenen Text zeichnen und das geänderte Dokument speichern. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

## Voraussetzungen

Bevor Sie mit dem Lernprogramm fortfahren, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#.
- Aspose.PDF für .NET-Bibliothek installiert. Sie können es von der Aspose-Website beziehen oder NuGet verwenden, um es in Ihrem Projekt zu installieren.

## Schritt 1: Einrichten des Projekts

Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu.

## Schritt 2: Erforderliche Namespaces importieren

Fügen Sie am Anfang Ihrer C#-Datei die folgenden Using-Direktiven hinzu, um die erforderlichen Namespaces zu importieren:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Schritt 3: Pfad zum Dokumentverzeichnis festlegen

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest mit dem`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit dem`Document` Klasse:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Ersetzen`"SearchAndGetTextFromAll.pdf"` durch den tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 5: Erstellen Sie einen TextFragmentAbsorber

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Ersetzen`@"[\S]+"` mit Ihrem gewünschten regulären Ausdrucksmuster.

## Schritt 6: Suche mit regulären Ausdrücken aktivieren

 Aktivieren Sie die Suche mit regulären Ausdrücken, indem Sie`TextSearchOptions` Eigenschaft des Absorbers:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Schritt 7: Auf allen Seiten suchen

Akzeptieren Sie den Absorber für alle Seiten des Dokuments:

```csharp
document.Pages.Accept(textAbsorber);
```

## Schritt 8: Zeichnen Sie ein Rechteck um den gefundenen Text

 Erstellen Sie ein`PdfContentEditor` Objekt und durchläuft die abgerufenen Textfragmente, wobei um jedes Textsegment ein Rechteck gezeichnet wird:

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

 Ersetzen Sie unbedingt`"SearchTextAndDrawRectangle_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text suchen und Rechteck zeichnen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
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

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie in einem PDF-Dokument nach bestimmtem Text suchen, ein Rechteck um den gefundenen Text zeichnen und das geänderte Dokument mit Aspose.PDF für .NET speichern. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung, vom Einrichten des Projekts bis zum Ausführen der erforderlichen Aktionen. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um Text zu bearbeiten und Rechtecke in PDF-Dateien zu zeichnen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text suchen und Rechteck zeichnen“?

A: Das Tutorial „Text suchen und Rechteck zeichnen“ führt Benutzer durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um in einem PDF-Dokument nach bestimmtem Text zu suchen, Rechtecke um die gefundenen Textsegmente zu zeichnen und das geänderte Dokument zu speichern. Das Tutorial enthält detaillierte Anweisungen und C#-Codebeispiele, um jeden Schritt des Prozesses zu veranschaulichen.

#### F: Wie hilft dieses Tutorial beim Zeichnen von Rechtecken um bestimmten Text in einem PDF-Dokument?

A: Dieses Tutorial bietet eine umfassende Anleitung zum Suchen und Zeichnen von Rechtecken um bestimmte Textsegmente in einem PDF-Dokument. Es zeigt den Vorgang des Einrichtens eines Projekts, des Ladens eines PDF-Dokuments, des Aktivierens der Suche mit regulären Ausdrücken, des Zeichnens von Rechtecken um gefundene Textsegmente und des Speicherns des geänderten PDF.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Fügen Sie dann Ihrem Projekt einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Bearbeiten von PDF-Dokumenten nutzen.

#### F: Kann ich mit diesem Tutorial Rechtecke um bestimmten Text zeichnen?

A: Ja, das Tutorial konzentriert sich auf das Zeichnen von Rechtecken um bestimmte Textsegmente in einem PDF-Dokument. Es zeigt, wie Sie den gewünschten Text mithilfe regulärer Ausdrücke finden, Rechtecke um die identifizierten Textsegmente erstellen und das geänderte PDF speichern.

#### F: Wie kann ich den Text angeben, nach dem ich suchen möchte, und Rechtecke darum zeichnen?

 A: Um den zu suchenden Text anzugeben und Rechtecke darum zu zeichnen, erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie sein Muster mit dem`Text` Parameter. Ersetzen Sie das Standardmuster`@"[\S]+"` im Code des Tutorials mit Ihrem gewünschten regulären Ausdrucksmuster.

#### F: Wie aktiviere ich die Suche nach Text mit regulären Ausdrücken?

 A: Die Suche mit regulären Ausdrücken wird aktiviert durch die Erstellung eines`TextSearchOptions` Objekt und setzt seinen Wert auf`true` Ordnen Sie dieses Objekt dem`TextSearchOptions` Eigentum der`TextFragmentAbsorber` Instanz. Dadurch wird sichergestellt, dass bei der Textsuche das reguläre Ausdrucksmuster verwendet wird.

#### F: Wie zeichne ich Rechtecke um den gefundenen Text?

 A: Nach der Identifizierung der Textsegmente mit Hilfe der`TextFragmentAbsorber` bietet das Tutorial eine Schleife, um diese Segmente zu durchlaufen. Für jedes Textsegment zeigt das Tutorial, wie Sie mithilfe der`DrawBox` Methode und geben Sie das Aussehen des Rechtecks an.

#### F: Welche Schritte sind zum Speichern der geänderten PDF-Datei mit gezeichneten Rechtecken erforderlich?

A: Zeichnen Sie Rechtecke um die gewünschten Textsegmente und verwenden Sie die`Document` Klasse`Save` Methode zum Speichern des geänderten Dokuments. Der Beispielcode des Tutorials zeigt, wie das bearbeitete PDF gespeichert und eine Erfolgsmeldung angezeigt wird.

#### F: Kann ich das Aussehen der gezeichneten Rechtecke anpassen?

 A: Ja, Sie können das Aussehen der gezeichneten Rechtecke anpassen. Im Beispielcode des Tutorials wird das`DrawBox` Die Methode wird zum Erstellen von Rechtecken verwendet. Sie können Eigenschaften wie Farbe, Stil und Dicke ändern, um das Erscheinungsbild der gezeichneten Rechtecke anzupassen.