---
title: Suchen und Text abrufen Alle
linktitle: Suchen und Text abrufen Alle
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen können.
type: docs
weight: 420
url: /de/net/programming-with-text/search-and-get-text-all/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET Text auf allen Seiten eines PDF-Dokuments suchen und abrufen können. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Ersetzen Sie unbedingt`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Text suchen und extrahieren

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Ersetzen`"text"` durch den eigentlichen Text, nach dem Sie suchen möchten.

## Schritt 5: Auf allen Seiten suchen

Akzeptieren Sie den Absorber für alle Seiten des Dokuments:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 6: Extrahierte Textfragmente abrufen

 Holen Sie sich die extrahierten Textfragmente mit dem`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 7: Durchlaufen der Textfragmente

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

Sie können den Code innerhalb der Schleife ändern, um für jedes Textfragment weitere Aktionen auszuführen.

### Beispielquellcode für „Search And Get Text All“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text aus allen Seiten eines PDF-Dokuments suchen und abrufen können. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Zugriff auf die extrahierten Textfragmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um Textinhalte in PDF-Dateien zu analysieren und zu verarbeiten.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Suchen und gesamten Text abrufen“?

A: Das Tutorial „Suchen und gesamten Text abrufen“ zeigt, wie Sie die Aspose.PDF-Bibliothek für .NET nutzen, um Text auf allen Seiten eines PDF-Dokuments zu suchen und zu extrahieren. Das Tutorial enthält schrittweise Anleitungen sowie Beispiel-C#-Code zum Durchführen von Textsuche und -abruf.

#### F: Wie hilft dieses Tutorial beim Extrahieren von Text aus PDF-Dokumenten?

A: Dieses Tutorial führt Sie durch den Prozess des Extrahierens von Text aus allen Seiten eines PDF-Dokuments. Es verwendet die Aspose.PDF-Bibliothek, um bestimmte Textphrasen zu finden und zugehörige Informationen wie Position, Schrifteigenschaften und Farben abzurufen.

#### F: Welche Voraussetzungen müssen für die Teilnahme an diesem Tutorial erfüllt sein?

A: Bevor Sie mit diesem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder NuGet verwenden, um sie in Ihr Projekt zu integrieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Dadurch können Sie in Ihrem Projekt auf die Funktionen der Bibliothek zugreifen.

#### F: Wie suche ich in einem PDF-Dokument nach bestimmtem Text?

 A: Sie können die`TextFragmentAbsorber`Klasse, um Instanzen eines bestimmten Suchbegriffs im PDF-Dokument zu finden. Indem Sie eine Instanz dieser Klasse erstellen und den Zieltext angeben, können Sie alle Vorkommen dieses Textes erfassen.

#### F: Kann ich auf allen Seiten des PDF-Dokuments nach Text suchen?

 A: Ja, das Tutorial zeigt, wie man auf allen Seiten des PDF-Dokuments nach Text sucht. Die`pdfDocument.Pages.Accept(textFragmentAbsorber)` Mit dieser Methode wird der Absorber für alle Seiten übernommen, so dass auf jeder Seite nach dem gewünschten Text gesucht werden kann.

#### F: Wie greife ich auf die extrahierten Textfragmente zu?

 A: Nach der Suche nach dem Text können Sie auf die extrahierten Textfragmente zugreifen über`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt. Diese Eigenschaft bietet Zugriff auf eine Sammlung von`TextFragment` Objekte, die den extrahierten Text und zugehörige Informationen enthalten.

#### F: Welche Informationen kann ich aus den extrahierten Textfragmenten abrufen?

A: Sie können aus den extrahierten Textfragmenten verschiedene Details abrufen, z. B. den eigentlichen Textinhalt, die Position (X- und Y-Koordinaten), Schriftinformationen (Name, Größe, Farbe usw.) und mehr. Der Beispielcode des Tutorials zeigt, wie Sie auf diese Details zugreifen und sie drucken können.

#### F: Kann ich mit den extrahierten Textfragmenten weitere Aktionen durchführen?

A: Absolut. Sobald Sie die extrahierten Textfragmente haben, können Sie den Code innerhalb der Schleife ändern, um benutzerdefinierte Aktionen für jedes Fragment auszuführen. Dazu könnte das Speichern des extrahierten Textes, das Analysieren von Textmustern oder das Anwenden von Formatierungsänderungen gehören.