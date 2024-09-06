---
title: Suchen und Abrufen einer Textseite in einer PDF-Datei
linktitle: Suchen und Abrufen einer Textseite in einer PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf einer bestimmten Seite einer PDF-Datei suchen und abrufen können.
type: docs
weight: 430
url: /de/net/programming-with-text/search-and-get-text-page/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text von einer bestimmten Seite in einer PDF-Datei suchen und abrufen können. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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

## Schritt 3: Laden Sie das PDF-Dokument

 Legen Sie den Pfad zu Ihrem PDF-Dokumentverzeichnis fest und laden Sie das Dokument mit dem`Document` Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Suchen und Extrahieren von Text auf einer Seite

 Erstellen Sie ein`TextFragmentAbsorber`Objekt, um alle Vorkommen der eingegebenen Suchphrase auf einer bestimmten Seite zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Ersetzen`"Figure"` durch den eigentlichen Text, nach dem Sie suchen möchten.

## Schritt 5: Auf einer bestimmten Seite suchen

Akzeptieren Sie den Absorber für eine bestimmte Seite des Dokuments:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 6: Extrahierte Textfragmente abrufen

Holen Sie sich die extrahierten Textfragmente mit dem`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 7: Durchlaufen Sie die Textfragmente und -segmente

Durchlaufen Sie die getd-Textfragmente und ihre Segmente und greifen Sie auf ihre Eigenschaften zu:

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

Sie können den Code innerhalb der Schleife ändern, um für jedes Textsegment weitere Aktionen auszuführen.

### Beispielquellcode für die Seite „Suchen und Text abrufen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufen der Fragmente
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

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text von einer bestimmten Seite eines PDF-Dokuments suchen und abrufen können. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textsegmente. Sie können jetzt

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Seite „Suchen und Text abrufen““?

A: Das Tutorial „Textseite suchen und abrufen“ soll veranschaulichen, wie Sie mit der Aspose.PDF-Bibliothek für .NET nach Text auf einer bestimmten Seite in einer PDF-Datei suchen und diesen abrufen können. Das Tutorial enthält detaillierte Anweisungen und Beispiel-C#-Code zur Demonstration des Vorgangs.

#### F: Wie hilft dieses Tutorial beim Extrahieren von Text aus einer bestimmten Seite in einem PDF-Dokument?

A: Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus einer bestimmten Seite eines PDF-Dokuments mithilfe der Aspose.PDF-Bibliothek. Es beschreibt die erforderlichen Schritte und bietet C#-Code zum Suchen nach einer bestimmten Textphrase auf der ausgewählten Seite und zum Abrufen zugehöriger Textsegmente.

#### F: Welche Voraussetzungen müssen für die Teilnahme an diesem Tutorial erfüllt sein?

A: Bevor Sie mit diesem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder NuGet verwenden, um sie in Ihr Projekt zu integrieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek in Ihrem Projekt nutzen.

#### F: Kann ich auf einer bestimmten Seite des PDF-Dokuments nach Text suchen?

A: Ja, dieses Tutorial zeigt, wie man auf einer bestimmten Seite eines PDF-Dokuments nach Text sucht. Dazu wird das`TextFragmentAbsorber` Klasse, um Instanzen einer bestimmten Textphrase auf der ausgewählten Seite zu finden.

#### F: Wie greife ich auf die extrahierten Textsegmente der jeweiligen Seite zu?

 A: Nachdem Sie auf der angegebenen Seite nach dem Text gesucht haben, können Sie die extrahierten Textsegmente über das`TextSegments` Eigentum der`TextFragment` Objekt. Diese Eigenschaft bietet Zugriff auf eine Sammlung von`TextSegment` Objekte, die den extrahierten Text und zugehörige Informationen enthalten.

#### F: Welche Informationen kann ich aus den extrahierten Textsegmenten abrufen?

A: Sie können aus den extrahierten Textsegmenten verschiedene Details abrufen, darunter Textinhalt, Position (X- und Y-Koordinaten), Schriftinformationen (Name, Größe, Farbe usw.) und mehr. Der Beispielcode des Tutorials zeigt, wie Sie auf diese Details für jedes Textsegment zugreifen und sie drucken können.

#### F: Kann ich benutzerdefinierte Aktionen für die extrahierten Textsegmente ausführen?

A: Natürlich. Sobald Sie die extrahierten Textsegmente haben, können Sie den Code innerhalb der Schleife anpassen, um zusätzliche Aktionen für jedes Segment auszuführen. Dazu könnte das Speichern des extrahierten Textes, das Analysieren von Textmustern oder das Anwenden von Formatierungsänderungen gehören.