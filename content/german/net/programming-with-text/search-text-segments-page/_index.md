---
title: Durchsuchen Sie die Seite „Textsegmente“ in einer PDF-Datei
linktitle: Durchsuchen Sie die Seite „Textsegmente“ in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Textsegmenten auf einer Seite in einer PDF-Datei suchen und deren Eigenschaften abrufen.
type: docs
weight: 470
url: /de/net/programming-with-text/search-text-segments-page/
---
In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten auf einer Seite einer PDF-Datei suchen und deren Eigenschaften abrufen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Ersetzen`"SearchTextSegmentsPage.pdf"` mit dem tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 5: Erstellen Sie einen TextFragmentAbsorber

 Ein ... kreieren`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen Suchbegriffs zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Ersetzen`"text"` mit Ihrem gewünschten Suchbegriff.

## Schritt 6: Akzeptieren Sie den Leitfaden für eine bestimmte Seite

Akzeptieren Sie den Absorber für die gewünschte Seite des Dokuments:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Ersetzen`2` mit der gewünschten Seitenzahl (1-basierter Index).

## Schritt 7: Rufen Sie die extrahierten Textsegmente ab

 Rufen Sie die extrahierten Textsegmente mit ab`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 8: Durchlaufen Sie die Textsegmente

Durchlaufen Sie die abgerufenen Textsegmente und greifen Sie auf deren Eigenschaften zu:

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

### Beispielquellcode für die Seite „Suchtextsegmente“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
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

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach bestimmten Textsegmenten auf einer Seite eines PDF-Dokuments suchen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textsegmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um erweiterte Textsegmentsuchen in PDF-Dateien durchzuführen.

### FAQs

#### F: Was ist der Zweck des Tutorials „Seite mit Textsegmenten in einer PDF-Datei durchsuchen“?

A: Das Tutorial „Suche nach Textsegmenten auf einer Seite in einer PDF-Datei“ bietet eine umfassende Anleitung zur Verwendung der Aspose.PDF-Bibliothek für .NET, um nach bestimmten Textsegmenten auf einer bestimmten Seite eines PDF-Dokuments zu suchen. Es umfasst den Prozess des Einrichtens eines Projekts, des Ladens eines PDF-Dokuments, der Suche nach Textsegmenten und des Abrufens ihrer Eigenschaften mithilfe von C#-Code.

#### F: Wie hilft dieses Tutorial bei der Suche nach bestimmten Textsegmenten in einem PDF-Dokument?

A: Dieses Tutorial demonstriert den Prozess des Suchens und Extrahierens bestimmter Textsegmente auf einer bestimmten Seite eines PDF-Dokuments. Durch Befolgen der bereitgestellten Schritte und Codebeispiele können Benutzer effektiv nach gewünschten Textsegmenten suchen und Informationen über deren Eigenschaften abrufen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus muss die Bibliothek Aspose.PDF für .NET installiert sein. Sie können es von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Bibliothek Aspose.PDF für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Suchen und Arbeiten mit PDF-Dokumenten nutzen.

#### F: Kann ich dieses Tutorial verwenden, um auf einer beliebigen Seite einer PDF-Datei nach bestimmten Textsegmenten zu suchen?

A: Ja, dieses Tutorial enthält Anweisungen zum Suchen nach bestimmten Textsegmenten auf einer ausgewählten Seite eines PDF-Dokuments. Es führt Benutzer durch das Einrichten eines Projekts, das Laden einer PDF-Datei und die Verwendung der Aspose.PDF-Bibliothek zum Suchen und Abrufen von Eigenschaften der gewünschten Textsegmente.

#### F: Wie spezifiziere ich den Text, nach dem ich in diesem Tutorial suchen möchte?

 A: Um den Text anzugeben, nach dem Sie suchen möchten, erstellen Sie einen`TextFragmentAbsorber` Objekt und legen Sie seinen Suchparameter mit fest`Text` Eigentum. Ersetzen Sie die Standardeinstellung`"text"` Geben Sie im Code des Tutorials den gewünschten Suchbegriff ein.

#### F: Wie rufe ich Eigenschaften der extrahierten Textsegmente ab?

Nach Annahme der`TextFragmentAbsorber` Für eine bestimmte Seite der PDF-Datei können Sie die extrahierten Textsegmente mithilfe von abrufen`TextFragments` Eigenschaft des Absorberobjekts. Dies ermöglicht den Zugriff auf eine Sammlung von Textfragmenten, die jeweils mehrere Textsegmente enthalten.

#### F: Kann ich den Code anpassen, um zusätzliche Aktionen für jedes Textsegment auszuführen?

A: Absolut. Der Beispielcode des Tutorials bietet eine Schleife zum Durchlaufen der abgerufenen Textsegmente. Sie können den Code innerhalb dieser Schleife anpassen, um basierend auf Ihren Projektanforderungen zusätzliche Aktionen für jedes Textsegment auszuführen.

#### F: Wie speichere ich das geänderte PDF-Dokument nach dem Extrahieren von Textsegmenten?

A: Dieses Tutorial konzentriert sich hauptsächlich auf die Suche nach Textsegmenten und das Abrufen ihrer Eigenschaften. Wenn Sie beabsichtigen, Änderungen an der PDF-Datei vorzunehmen, können Sie in anderen Aspose.PDF-Dokumentationen nachlesen, wie Sie das Dokument entsprechend Ihren spezifischen Anforderungen bearbeiten und speichern können.