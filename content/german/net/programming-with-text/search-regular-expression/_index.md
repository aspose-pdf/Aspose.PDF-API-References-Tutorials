---
title: Suche nach regulären Ausdrücken in PDF-Datei
linktitle: Suche nach regulären Ausdrücken in PDF-Datei
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mithilfe regulärer Ausdrücke Text in PDF-Dateien suchen und abrufen.
type: docs
weight: 440
url: /de/net/programming-with-text/search-regular-expression/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text suchen und abrufen, der einem regulären Ausdruck in einer PDF-Datei entspricht. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Suche mit regulären Ausdrücken

 Erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie das reguläre Ausdrucksmuster fest, um alle Phrasen zu finden, die dem Muster entsprechen:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Wie 1999-2000
```

 Ersetzen`"\\d{4}-\\d{4}"` mit Ihrem gewünschten regulären Ausdrucksmuster.

## Schritt 5: Textsuchoptionen festlegen

 Erstellen Sie ein`TextSearchOptions` Objekt und setzen Sie es auf den`TextSearchOptions` Eigentum der`TextFragmentAbsorber` Objekt zum Aktivieren der Verwendung regulärer Ausdrücke:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Schritt 6: Auf allen Seiten suchen

Akzeptieren Sie den Absorber für alle Seiten des Dokuments:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 7: Extrahierte Textfragmente abrufen

 Holen Sie sich die extrahierten Textfragmente mit dem`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 8: Durchlaufen der Textfragmente

Durchlaufen Sie die abgerufenen Textfragmente und greifen Sie auf ihre Eigenschaften zu:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Sie können den Code innerhalb der Schleife ändern, um für jedes Textfragment weitere Aktionen auszuführen.

### Beispiel-Quellcode für die Suche nach regulären Ausdrücken mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Wie 1999-2000
// Legen Sie die Textsuchoption fest, um die Verwendung regulärer Ausdrücke anzugeben
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
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

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text suchen und abrufen, der einem regulären Ausdruck in einem PDF-Dokument entspricht. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textfragmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um erweiterte Textsuchen in PDF-Dateien durchzuführen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Reguläre Ausdrücke in PDF-Dateien suchen“?

A: Das Tutorial „Reguläre Ausdrücke in PDF-Datei suchen“ soll zeigen, wie Sie mit der Aspose.PDF-Bibliothek für .NET nach Text suchen und diesen extrahieren können, der einem angegebenen regulären Ausdrucksmuster in einer PDF-Datei entspricht. Das Tutorial bietet umfassende Anleitungen und Beispiel-C#-Code zur Demonstration des Vorgangs.

#### F: Wie hilft dieses Tutorial bei der Textsuche mithilfe regulärer Ausdrücke in einem PDF-Dokument?

A: Dieses Tutorial bietet eine schrittweise Anleitung zur Verwendung der Aspose.PDF-Bibliothek, um Textsuchen in einem PDF-Dokument basierend auf einem regulären Ausdrucksmuster durchzuführen. Es beschreibt detailliert, wie Sie das Projekt einrichten, das PDF-Dokument laden, ein reguläres Ausdrucksmuster definieren und die übereinstimmenden Textfragmente abrufen.

#### F: Welche Voraussetzungen müssen für die Teilnahme an diesem Tutorial erfüllt sein?

A: Bevor Sie mit diesem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder NuGet verwenden, um sie in Ihr Projekt zu integrieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Auf diese Weise können Sie die Funktionen der Bibliothek in Ihrem Projekt nutzen.

#### F: Kann ich reguläre Ausdrücke verwenden, um in einem PDF-Dokument nach Text zu suchen?

 A: Ja, dieses Tutorial zeigt, wie man mit regulären Ausdrücken nach Text in einem PDF-Dokument sucht und diesen extrahiert. Dabei wird der`TextFragmentAbsorber` Klasse und Angabe eines regulären Ausdrucksmusters, um Phrasen zu finden, die dem bereitgestellten Muster entsprechen.

#### F: Wie definiere ich das reguläre Ausdrucksmuster für die Textsuche?

 A: Um ein reguläres Ausdrucksmuster für die Textsuche zu definieren, erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie sein Muster mit dem`Text` Parameter. Ersetzen Sie das Standardmuster`"\\d{4}-\\d{4}"` im Code des Tutorials mit Ihrem gewünschten regulären Ausdrucksmuster.

#### F: Wie kann ich die Verwendung regulärer Ausdrücke für die Textsuche aktivieren?

 A: Die Verwendung regulärer Ausdrücke wird aktiviert durch die Erstellung eines`TextSearchOptions` Objekt und setzt seinen Wert auf`true` Ordnen Sie dieses Objekt dem`TextSearchOptions` Eigentum der`TextFragmentAbsorber` Instanz. Dadurch wird sichergestellt, dass das reguläre Ausdrucksmuster während der Textsuche angewendet wird.

#### F: Kann ich Textfragmente abrufen, die dem regulären Ausdrucksmuster entsprechen?

 A: Absolut. Nachdem Sie die reguläre Ausdruckssuche auf das PDF-Dokument angewendet haben, können Sie die extrahierten Textfragmente mithilfe des`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt. Diese Textfragmente enthalten die Textsegmente, die dem angegebenen regulären Ausdrucksmuster entsprechen.

#### F: Auf welche Informationen kann ich aus den abgerufenen Textfragmenten zugreifen?

A: Von den abgerufenen Textfragmenten aus können Sie auf verschiedene Eigenschaften zugreifen, wie z. B. den übereinstimmenden Textinhalt, die Position (X- und Y-Koordinaten), Schriftinformationen (Name, Größe, Farbe) und mehr. Der Beispielcode in der Schleife des Tutorials zeigt, wie Sie auf diese Eigenschaften zugreifen und sie anzeigen.

#### F: Wie kann ich Aktionen für die extrahierten Textfragmente anpassen?

A: Sobald Sie die extrahierten Textfragmente haben, können Sie den Code innerhalb der Schleife anpassen, um zusätzliche Aktionen für jedes Textfragment auszuführen. Dazu kann das Speichern des extrahierten Textes, das Analysieren von Mustern oder das Implementieren von Formatierungsänderungen basierend auf Ihren Anforderungen gehören.