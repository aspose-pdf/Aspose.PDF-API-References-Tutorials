---
title: Alle Texte suchen und abrufen
linktitle: Alle Texte suchen und abrufen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen.
type: docs
weight: 420
url: /de/net/programming-with-text/search-and-get-text-all/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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

## Schritt 3: Laden Sie das PDF-Dokument

 Legen Sie den Pfad zu Ihrem PDF-Dokumentverzeichnis fest und laden Sie das Dokument mit`Document` Klasse:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Unbedingt austauschen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Text suchen und extrahieren

 Ein ... kreieren`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen Suchbegriffs zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Ersetzen`"text"` mit dem eigentlichen Text, nach dem Sie suchen möchten.

## Schritt 5: Suchen Sie auf allen Seiten

Akzeptieren Sie den Absorber für alle Seiten des Dokuments:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 6: Extrahierte Textfragmente abrufen

Holen Sie sich die extrahierten Textfragmente mit`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 7: Gehen Sie die Textfragmente in einer Schleife durch

Durchlaufen Sie die getd-Textfragmente und greifen Sie auf ihre Eigenschaften zu:

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

Sie können den Code innerhalb der Schleife ändern, um weitere Aktionen für jedes Textfragment auszuführen.

### Beispielquellcode für Search And Get Text All mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
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

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textfragmente. Sie können diesen Code nun in Ihre eigenen C#-Projekte integrieren, um Textinhalte in PDF-Dateien zu analysieren und zu verarbeiten.