---
title: Durchsuche Text mit Dot Net Regex
linktitle: Durchsuche Text mit Dot Net Regex
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET mithilfe von .NET-regulären Ausdrücken in einem PDF-Dokument nach Text suchen.
type: docs
weight: 480
url: /de/net/programming-with-text/search-text-with-dot-net-regex/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET mithilfe von .NET-regulären Ausdrücken nach Text in einem PDF-Dokument suchen. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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

## Schritt 4: Erstellen Sie ein .NET Regex-Objekt

 Erstellen Sie ein`.NET Regex` Objekt zum Definieren des Suchmusters:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Ersetzen`@"[\S]+"` mit Ihrem gewünschten regulären Ausdrucksmuster.

## Schritt 5: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit dem`Document` Klasse:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Ersetzen`"SearchTextRegex.pdf"` durch den tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 6: Eine bestimmte Seite abrufen

Holen Sie sich die gewünschte Seite des Dokuments:

```csharp
Page page = document.Pages[1];
```

 Ersetzen`1` mit der gewünschten Seitenzahl (1er-Index).

## Schritt 7: Erstellen Sie einen TextFragmentAbsorber

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen regulären Ausdrucks zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Schritt 8: Akzeptieren Sie den Absorber für die Seite

Akzeptieren Sie den Absorber für die Seite:

```csharp
page.Accept(textFragmentAbsorber);
```

## Schritt 9: Abrufen der extrahierten Textfragmente

 Holen Sie sich die extrahierten Textfragmente mit dem`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 10: Durchlaufen der Textfragmente

Durchlaufen Sie die abgerufenen Textfragmente und führen Sie die gewünschten Aktionen aus:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Ändern Sie den Code innerhalb der Schleife, um bei Bedarf weitere Aktionen für jedes Textfragment auszuführen.

### Beispielquellcode für die Textsuche mit Dot Net Regex unter Verwendung von Aspose.PDF für .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein Regex-Objekt, um alle Wörter zu finden
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Dokument öffnen
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Eine bestimmte Seite abrufen
Page page = document.Pages[1];
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen des Eingabe-Regex zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Akzeptieren Sie den Absorber für die Seite
page.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufen der Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit .NET-regulären Ausdrücken in einem PDF-Dokument mit Aspose.PDF für .NET nach Text suchen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung, vom Einrichten des Projekts bis zum Zugriff auf die extrahierten Textfragmente. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um erweiterte Textsuchen in PDF-Dateien durchzuführen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text mit Dot Net Regex durchsuchen“?

A: Das Tutorial „Text mit Dot Net Regex durchsuchen“ soll Benutzern die Verwendung der Aspose.PDF-Bibliothek für .NET erklären, um mithilfe von .NET-regulären Ausdrücken nach Text in einem PDF-Dokument zu suchen. Das Tutorial enthält schrittweise Anleitungen und C#-Codebeispiele zur Demonstration des Vorgangs.

#### F: Wie hilft dieses Tutorial bei der Textsuche in einer PDF-Datei mithilfe von .NET-regulären Ausdrücken?

A: Dieses Tutorial hilft Benutzern zu verstehen, wie sie die Funktionen von Aspose.PDF für .NET nutzen können, um mit .NET-regulären Ausdrücken in einem PDF-Dokument nach Text zu suchen. Indem sie die bereitgestellten Schritte und Codebeispiele befolgen, können Benutzer effektiv nach Textmustern suchen, die ihren angegebenen regulären Ausdrücken entsprechen.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie mit dem Tutorial beginnen, sollten Sie über Grundkenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben. Sie können sie von der Aspose-Website herunterladen oder mit NuGet in Ihrem Projekt installieren.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE) und fügen Sie einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu. Dadurch können Sie die Funktionen der Bibliothek zum Suchen und Arbeiten mit PDF-Dokumenten nutzen.

#### F: Kann ich dieses Tutorial verwenden, um mit regulären .NET-Ausdrücken nach einem bestimmten Texttyp zu suchen?

 A: Ja, dieses Tutorial enthält Anweisungen zum Suchen nach Text mithilfe von regulären .NET-Ausdrücken in einem PDF-Dokument. Sie können die`.NET Regex` Objekt, um das spezifische Suchmuster zu definieren, das Sie verwenden möchten.

#### F: Wie gebe ich das .NET-reguläre Ausdrucksmuster an, nach dem in diesem Tutorial gesucht werden soll?

 A: Um das .NET-Regular-Expression-Muster anzugeben, nach dem Sie suchen möchten, erstellen Sie ein`.NET Regex` Objekt und legen Sie sein Muster mit der entsprechenden regulären Ausdruckssyntax fest. Ersetzen Sie den Standard`@"[\S]+"` im Code des Tutorials durch den gewünschten regulären Ausdruck.

#### F: Wie rufe ich die Eigenschaften der extrahierten Textfragmente ab?

 A: Nach der Annahme der`TextFragmentAbsorber` für eine bestimmte Seite der PDF-Datei können Sie die extrahierten Textfragmente abrufen mit dem`TextFragments` Eigenschaft des Absorberobjekts. Dies ermöglicht den Zugriff auf eine Sammlung von Textfragmenten, die dem angegebenen .NET-regulären Ausdruck entsprechen.

#### F: Kann ich den Code anpassen, um für jedes extrahierte Textfragment zusätzliche Aktionen auszuführen?

A: Natürlich. Der Beispielcode des Tutorials enthält eine Schleife, um die abgerufenen Textfragmente zu durchlaufen. Sie können den Code innerhalb dieser Schleife anpassen, um basierend auf Ihren Projektanforderungen zusätzliche Aktionen für jedes extrahierte Textfragment auszuführen.

#### F: Wie speichere ich das geänderte PDF-Dokument, nachdem ich Textfragmente extrahiert habe?

A: Dieses Tutorial konzentriert sich hauptsächlich auf die Textsuche mit .NET-regulären Ausdrücken und das Abrufen von Textfragmenten. Wenn Sie Änderungen an der PDF-Datei vornehmen möchten, können Sie in anderen Aspose.PDF-Dokumentationen nachlesen, wie Sie das Dokument entsprechend Ihren spezifischen Anforderungen bearbeiten und speichern können.