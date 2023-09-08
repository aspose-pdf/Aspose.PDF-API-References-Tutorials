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

### FAQs

#### F: Was ist der Zweck des Tutorials „Text suchen und Rechteck zeichnen“?

A: Das Tutorial „Text suchen und Rechteck zeichnen“ zielt darauf ab, Benutzer durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET zu führen, um in einem PDF-Dokument nach bestimmtem Text zu suchen, Rechtecke um die gefundenen Textsegmente zu zeichnen und die geänderten Texte zu speichern dokumentieren. Das Tutorial enthält detaillierte Anweisungen und C#-Codebeispiele, um jeden Schritt des Prozesses zu veranschaulichen.

#### F: Wie hilft dieses Tutorial beim Zeichnen von Rechtecken um bestimmten Text in einem PDF-Dokument?

A: Dieses Tutorial bietet eine umfassende Anleitung zum Suchen und Zeichnen von Rechtecken um bestimmte Textsegmente in einem PDF-Dokument. Es zeigt den Prozess des Einrichtens eines Projekts, des Ladens eines PDF-Dokuments, der Aktivierung der Suche nach regulären Ausdrücken, des Zeichnens von Rechtecken um gefundene Textsegmente und des Speicherns der geänderten PDF-Datei.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus muss die Bibliothek Aspose.PDF für .NET installiert sein. Sie können es von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Fügen Sie dann Ihrem Projekt einen Verweis auf die Aspose.PDF für .NET-Bibliothek hinzu. Dadurch können Sie die Funktionalität der Bibliothek zum Bearbeiten von PDF-Dokumenten nutzen.

#### F: Kann ich mit diesem Tutorial Rechtecke um einen bestimmten Text zeichnen?

A: Ja, das Tutorial konzentriert sich auf das Zeichnen von Rechtecken um bestimmte Textsegmente in einem PDF-Dokument. Es zeigt, wie Sie den gewünschten Text mithilfe regulärer Ausdrücke finden, Rechtecke um die identifizierten Textsegmente erstellen und die geänderte PDF-Datei speichern.

#### F: Wie kann ich den Text angeben, nach dem ich suchen möchte, und wie kann ich Rechtecke darum zeichnen?

 A: Um den Text anzugeben, nach dem Sie suchen möchten, und um Rechtecke zu zeichnen, erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie sein Muster mit fest`Text` Parameter. Ersetzen Sie das Standardmuster`@"[\S]+"` im Code des Tutorials mit Ihrem gewünschten regulären Ausdrucksmuster.

#### F: Wie aktiviere ich die Suche nach regulären Ausdrücken für Text?

 A: Die Suche nach regulären Ausdrücken wird durch Erstellen eines aktiviert`TextSearchOptions` Objekt und setzt seinen Wert auf`true` . Ordnen Sie dieses Objekt dem zu`TextSearchOptions` Eigentum der`TextFragmentAbsorber` Beispiel. Dadurch wird sichergestellt, dass bei der Textsuche das reguläre Ausdrucksmuster verwendet wird.

#### F: Wie zeichne ich Rechtecke um den gefundenen Text?

 A: Nach der Identifizierung der Textsegmente mithilfe von`TextFragmentAbsorber` , bietet das Tutorial eine Schleife zum Durchlaufen dieser Segmente. Das Tutorial zeigt für jedes Textsegment, wie Sie mithilfe von ein Rechteck um dieses erstellen`DrawBox` -Methode und legen Sie das Erscheinungsbild des Rechtecks fest.

#### F: Welche Schritte sind erforderlich, um das geänderte PDF mit gezeichneten Rechtecken zu speichern?

A: Nachdem Sie Rechtecke um die gewünschten Textsegmente gezeichnet haben, verwenden Sie die`Document` Klasse`Save` Methode zum Speichern des geänderten Dokuments. Der Beispielcode des Tutorials zeigt, wie Sie die bearbeitete PDF-Datei speichern und eine Erfolgsmeldung anzeigen.

#### F: Kann ich das Erscheinungsbild der gezeichneten Rechtecke anpassen?

 A: Ja, Sie können das Aussehen der gezeichneten Rechtecke anpassen. Im Beispielcode des Tutorials ist die`DrawBox` Die Methode wird zum Erstellen von Rechtecken verwendet. Sie können Eigenschaften wie Farbe, Stil und Dicke ändern, um das Erscheinungsbild der gezeichneten Rechtecke anzupassen.