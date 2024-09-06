---
title: Gesamten Text in PDF-Datei ersetzen
linktitle: Gesamten Text in PDF-Datei ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text in einer PDF-Datei ersetzen.
type: docs
weight: 350
url: /de/net/programming-with-text/replace-text-all/
---
In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text in einer PDF-Datei ersetzen. Wir stellen eine Schritt-für-Schritt-Anleitung sowie den erforderlichen C#-Quellcode bereit.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.PDF für .NET-Bibliothek installiert.
- Grundlegende Kenntnisse der C#-Programmierung.

## Schritt 1: Einrichten des Dokumentverzeichnisses

 Legen Sie den Pfad zum Verzeichnis fest, in dem sich die PDF-Eingabedatei befindet. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit dem`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Schritt 3: Text suchen und ersetzen

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden. Akzeptieren Sie den Absorber für alle Seiten des PDF-Dokuments, um die Textfragmente zu extrahieren.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 4: Text ersetzen

Durchlaufen Sie die extrahierten Textfragmente und ersetzen Sie den Text nach Bedarf. Aktualisieren Sie den Text und andere Eigenschaften wie Schriftart, Schriftgröße, Vordergrundfarbe und Hintergrundfarbe.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Schritt 5: Speichern Sie die geänderte PDF-Datei

Speichert das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Text ersetzen – Gesamten Text ersetzen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufen der Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualisieren von Text und anderen Eigenschaften
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Speichern Sie das resultierende PDF-Dokument.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET den gesamten Text in einem PDF-Dokument ersetzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF-Dokument laden, nach dem gewünschten Text suchen, ihn ersetzen und das geänderte PDF speichern.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text in PDF-Datei vollständig ersetzen“?

A: Das Tutorial „Text in PDF-Datei komplett ersetzen“ führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek für .NET, um alle Instanzen eines bestimmten Textes in einem PDF-Dokument zu ersetzen. Es bietet eine Schritt-für-Schritt-Anleitung sowie Beispiel-C#-Code.

#### F: Warum sollte ich sämtliche Textvorkommen in einem PDF-Dokument ersetzen wollen?

A: Das Ersetzen aller Vorkommen eines bestimmten Textes in einem PDF-Dokument kann erforderlich sein, wenn Sie den Inhalt im gesamten Dokument aktualisieren oder standardisieren müssen. Dieser Vorgang kann besonders nützlich sein, um die Konsistenz von Dokumentinhalt und Formatierung sicherzustellen.

#### F: Wie richte ich das Dokumentverzeichnis ein?

A: So richten Sie das Dokumentverzeichnis ein:

1.  Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zum Verzeichnis, in dem sich Ihre Eingabe-PDF-Datei befindet.

#### F: Wie ersetze ich alle Textvorkommen in einem PDF-Dokument?

A: Das Tutorial führt Sie durch die folgenden Schritte:

1.  Laden Sie das PDF-Dokument mit dem`Document` Klasse.
2.  Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden. Akzeptieren Sie den Absorber für alle Seiten des PDF-Dokuments, um die Textfragmente zu extrahieren.
3. Durchlaufen Sie die extrahierten Textfragmente und ersetzen Sie den Text. Aktualisieren Sie bei Bedarf andere Eigenschaften wie Schriftart, Schriftgröße, Vordergrundfarbe und Hintergrundfarbe.
4. Speichern Sie das geänderte PDF-Dokument.

#### F: Kann ich Text basierend auf einer Groß-/Kleinschreibung beachtenden Suche ersetzen?

 A: Ja, Sie können die`TextFragmentAbsorber` Suchtext, um eine Suche unter Beachtung der Groß- und Kleinschreibung durchzuführen. Geben Sie einfach den genauen Text ein, nach dem Sie suchen möchten, und der Absorber gleicht ihn entsprechend ab.

#### F: Ist der Schriftartenaustausch beim Ersetzen von Text optional?

A: Ja, der Schriftartenaustausch ist optional. Wenn Sie keine neue Schriftart angeben, behält der Text die Schriftart des ursprünglichen Textfragments bei.

#### F: Wie kann ich Text in bestimmten Abschnitten des PDF-Dokuments ersetzen?

A: Sie können die Schleife durch die Textfragmente anpassen, um bedingte Anweisungen basierend auf der Position der Textfragmente einzuschließen. Auf diese Weise können Sie Text nur in bestimmten Abschnitten der PDF-Datei ersetzen.

#### F: Was ist das erwartete Ergebnis der Ausführung des bereitgestellten Codes?

A: Indem Sie dem Tutorial folgen und den bereitgestellten C#-Code ausführen, ersetzen Sie alle Instanzen des angegebenen Textes im PDF-Dokument. Der ersetzte Text hat die von Ihnen angegebenen Eigenschaften, wie Schriftart, Schriftgröße, Vordergrundfarbe und Hintergrundfarbe.

#### F: Kann ich diesen Ansatz verwenden, um nicht-textliche Elemente wie Bilder oder Anmerkungen zu ersetzen?

A: Nein, dieses Tutorial konzentriert sich speziell auf das Ersetzen von Text in einem PDF-Dokument. Wenn Sie nicht-textliche Elemente ersetzen müssen, müssen Sie andere Verfahren befolgen oder andere Aspose.PDF-Funktionen verwenden.