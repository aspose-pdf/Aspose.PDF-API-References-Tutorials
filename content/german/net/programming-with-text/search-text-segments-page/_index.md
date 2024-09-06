---
title: Seite „Textsegmente in PDF-Datei suchen“
linktitle: Seite „Textsegmente in PDF-Datei suchen“
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Textsegmenten auf einer Seite in einer PDF-Datei suchen und deren Eigenschaften abrufen.
type: docs
weight: 470
url: /de/net/programming-with-text/search-text-segments-page/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten auf einer Seite einer PDF-Datei suchen und deren Eigenschaften abrufen können. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Ersetzen`"SearchTextSegmentsPage.pdf"` durch den tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 5: Erstellen Sie einen TextFragmentAbsorber

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Ersetzen`"text"` mit Ihrem gewünschten Suchbegriff.

## Schritt 6: Akzeptieren Sie den Absorber für eine bestimmte Seite

Akzeptieren Sie den Absorber für die gewünschte Seite des Dokuments:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Ersetzen`2` mit der gewünschten Seitenzahl (1er-Index).

## Schritt 7: Abrufen der extrahierten Textsegmente

 Holen Sie sich die extrahierten Textsegmente mit dem`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 8: Durchlaufen der Textsegmente

Durchlaufen Sie die abgerufenen Textsegmente und greifen Sie auf ihre Eigenschaften zu:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Ändern Sie den Code innerhalb der Schleife, um bei Bedarf weitere Aktionen für jedes Textsegment auszuführen.

### Beispiel-Quellcode für die Seite „Textsegmente durchsuchen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufen der Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten auf einer Seite eines PDF-Dokuments suchen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textsegmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um erweiterte Textsegmentsuchen in PDF-Dateien durchzuführen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Seite „Textsegmente in PDF-Datei suchen““?

A: Das Tutorial „Textsegmente in PDF-Datei suchen“ bietet eine umfassende Anleitung zur Verwendung der Aspose.PDF-Bibliothek für .NET, um nach bestimmten Textsegmenten auf einer bestimmten Seite eines PDF-Dokuments zu suchen. Es behandelt den Prozess des Einrichtens eines Projekts, des Ladens eines PDF-Dokuments, der Suche nach Textsegmenten und des Abrufens ihrer Eigenschaften mithilfe von C#-Code.

#### F: Wie hilft dieses Tutorial bei der Suche nach bestimmten Textsegmenten in einem PDF-Dokument?

A: Dieses Tutorial zeigt, wie Sie bestimmte Textsegmente auf einer bestimmten Seite eines PDF-Dokuments finden und extrahieren. Indem Sie die bereitgestellten Schritte und Codebeispiele befolgen, können Benutzer effektiv nach gewünschten Textsegmenten suchen und Informationen zu deren Eigenschaften abrufen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Suchen und Arbeiten mit PDF-Dokumenten nutzen.

#### F: Kann ich mit diesem Tutorial auf einer beliebigen Seite einer PDF-Datei nach bestimmten Textsegmenten suchen?

A: Ja, dieses Tutorial enthält Anweisungen zum Suchen nach bestimmten Textsegmenten auf einer ausgewählten Seite eines PDF-Dokuments. Es führt Benutzer durch das Einrichten eines Projekts, das Laden einer PDF-Datei und die Verwendung der Aspose.PDF-Bibliothek zum Suchen und Abrufen der Eigenschaften der gewünschten Textsegmente.

#### F: Wie gebe ich in diesem Tutorial den Text an, nach dem ich suchen möchte?

 A: Um den Text anzugeben, nach dem Sie suchen möchten, erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie dessen Suchparameter mit dem`Text` Eigenschaft. Ersetzen Sie die Standardeinstellung`"text"` im Code des Tutorials mit Ihrem gewünschten Suchbegriff.

#### F: Wie rufe ich Eigenschaften der extrahierten Textsegmente ab?

Nach der Annahme der`TextFragmentAbsorber` Für eine bestimmte Seite des PDFs können Sie die extrahierten Textsegmente abrufen mit dem`TextFragments` Eigenschaft des Absorberobjekts. Dies ermöglicht den Zugriff auf eine Sammlung von Textfragmenten, von denen jedes mehrere Textsegmente enthält.

#### F: Kann ich den Code anpassen, um für jedes Textsegment zusätzliche Aktionen auszuführen?

A: Absolut. Der Beispielcode des Tutorials bietet eine Schleife, um die abgerufenen Textsegmente zu durchlaufen. Sie können den Code innerhalb dieser Schleife anpassen, um basierend auf Ihren Projektanforderungen zusätzliche Aktionen für jedes Textsegment auszuführen.

#### F: Wie speichere ich das geänderte PDF-Dokument, nachdem ich Textsegmente extrahiert habe?

A: Dieses Tutorial konzentriert sich hauptsächlich auf die Suche nach Textsegmenten und das Abrufen ihrer Eigenschaften. Wenn Sie Änderungen an der PDF-Datei vornehmen möchten, können Sie in anderen Aspose.PDF-Dokumentationen nachlesen, wie Sie das Dokument entsprechend Ihren spezifischen Anforderungen bearbeiten und speichern können.