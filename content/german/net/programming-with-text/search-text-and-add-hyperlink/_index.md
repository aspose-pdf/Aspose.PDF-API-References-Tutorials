---
title: Text durchsuchen und Hyperlink hinzufügen
linktitle: Text durchsuchen und Hyperlink hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET nach Text in einer PDF-Datei suchen, dem gefundenen Text Hyperlinks hinzufügen und das geänderte Dokument speichern.
type: docs
weight: 450
url: /de/net/programming-with-text/search-text-and-add-hyperlink/
---
Dieses Tutorial erklärt, wie Sie mit Aspose.PDF für .NET nach bestimmtem Text in einem PDF-Dokument suchen, dem gefundenen Text einen Hyperlink hinzufügen und das geänderte Dokument speichern. Der bereitgestellte C#-Quellcode demonstriert den Vorgang Schritt für Schritt.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Schritt 3: Pfad zum Dokumentverzeichnis festlegen

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest mit dem`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Erstellen Sie einen TextFragmentAbsorber

 Erstellen Sie ein`TextFragmentAbsorber` Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Ersetzen`"\\d{4}-\\d{4}"` mit Ihrem gewünschten regulären Ausdrucksmuster.

## Schritt 5: Suche mit regulären Ausdrücken aktivieren

 Aktivieren Sie die Suche mit regulären Ausdrücken, indem Sie`TextSearchOptions` Eigenschaft des Absorbers:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Schritt 6: PDF-Dokument öffnen und binden

 Erstellen Sie ein`PdfContentEditor` Objekt und binden Sie es an die Quell-PDF-Datei:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Ersetzen`"SearchRegularExpressionPage.pdf"` durch den tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 7: Akzeptieren Sie den Absorber für die Seite

Akzeptieren Sie den Absorber für die gewünschte Seite des Dokuments:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Ersetzen`1` mit der gewünschten Seitenzahl.

## Schritt 8: Hyperlinks zum gefundenen Text hinzufügen

Durchlaufen Sie die abgerufenen Textfragmente und fügen Sie ihnen Hyperlinks hinzu:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Erstellen Sie ein Rechteck basierend auf der Position des Textfragments
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Fügen Sie dem Rechteck einen Weblink hinzu
    editor.CreateWebLink(rect, "http://www.aspose.com“, 1, System.Drawing.Color.Blue);
}
```

 Ersetzen`"http://www.aspose.com"` mit der gewünschten Hyperlink-URL.

## Schritt 9: Speichern und schließen Sie das geänderte Dokument

Speichern Sie das geänderte Dokument und schließen Sie den Editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Ersetzen Sie unbedingt`"SearchTextAndAddHyperlink_out.pdf"` durch den gewünschten Ausgabedateinamen.

### Beispielquellcode zum Suchen von Text und Hinzufügen von Hyperlinks mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Absorberobjekt erstellen, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Suche mit regulären Ausdrücken aktivieren
absorber.TextSearchOptions = new TextSearchOptions(true);
// Dokument öffnen
PdfContentEditor editor = new PdfContentEditor();
// Quell-PDF-Datei binden
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Akzeptieren Sie den Absorber für die Seite
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Durchlaufen der Fragmente
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blau, Aktionsname);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach bestimmtem Text in einem PDF-Dokument suchen, dem gefundenen Text Hyperlinks hinzufügen und das geänderte Dokument speichern. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung, vom Einrichten des Projekts bis zum Ausführen der erforderlichen Aktionen. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um Text zu bearbeiten und Hyperlinks in PDF-Dateien hinzuzufügen.

### Häufig gestellte Fragen

#### F: Was ist der Zweck des Tutorials „Text suchen und Hyperlink hinzufügen“?

A: Das Tutorial „Text suchen und Hyperlink hinzufügen“ soll zeigen, wie Sie mit der Aspose.PDF-Bibliothek für .NET nach bestimmtem Text in einem PDF-Dokument suchen, dem gefundenen Text Hyperlinks hinzufügen und das geänderte Dokument dann speichern. Das Tutorial bietet eine umfassende Anleitung und C#-Codebeispiele, um den schrittweisen Prozess zu veranschaulichen.

#### F: Wie hilft dieses Tutorial beim Hinzufügen von Hyperlinks zu bestimmtem Text in einem PDF-Dokument?

A: Dieses Tutorial führt Sie durch den Prozess der Verwendung der Aspose.PDF-Bibliothek, um bestimmten Text in einem PDF-Dokument zu finden, einen Hyperlink auf den identifizierten Text anzuwenden und das geänderte PDF zu speichern. Es behandelt wichtige Schritte wie das Einrichten des Projekts, das Laden des Dokuments, das Aktivieren der Suche mit regulären Ausdrücken und das Hinzufügen von Hyperlinks zum gefundenen Text.

#### F: Welche Voraussetzungen sind erforderlich, um diesem Tutorial folgen zu können?

A: Bevor Sie beginnen, sollten Sie über grundlegende Kenntnisse der Programmiersprache C# verfügen. Darüber hinaus müssen Sie die Bibliothek Aspose.PDF für .NET installiert haben, die Sie von der Aspose-Website beziehen oder mit NuGet in Ihrem Projekt installieren können.

#### F: Wie richte ich mein Projekt ein, um diesem Tutorial zu folgen?

A: Beginnen Sie mit der Erstellung eines neuen C#-Projekts in Ihrer bevorzugten integrierten Entwicklungsumgebung (IDE). Fügen Sie dann einen Verweis auf die Aspose.PDF-Bibliothek für .NET hinzu, damit Sie die Funktionen der Bibliothek in Ihrem Projekt nutzen können.

#### F: Kann ich mit diesem Tutorial Hyperlinks zu bestimmten Texten hinzufügen?

A: Ja, dieses Tutorial konzentriert sich speziell auf das Hinzufügen von Hyperlinks zu bestimmten Texten in einem PDF-Dokument. Es zeigt, wie Sie den gewünschten Text mithilfe regulärer Ausdrücke finden und extrahieren, mit den Textfragmenten verknüpfte Hyperlinks erstellen und das geänderte PDF speichern.

#### F: Wie definiere ich den Text, nach dem ich suchen und dem ich einen Hyperlink hinzufügen möchte?

 A: Um den Text anzugeben, nach dem Sie suchen und dem Sie einen Hyperlink hinzufügen möchten, erstellen Sie ein`TextFragmentAbsorber` Objekt und legen Sie sein Muster mit dem`Text` Parameter. Ersetzen Sie das Standardmuster`"\\d{4}-\\d{4}"` im Code des Tutorials mit Ihrem gewünschten regulären Ausdrucksmuster.

#### F: Wie kann ich die Suche nach Text mit regulären Ausdrücken aktivieren?

 A: Die Suche mit regulären Ausdrücken wird aktiviert durch die Erstellung eines`TextSearchOptions` Objekt und setzt seinen Wert auf`true` Ordnen Sie dieses Objekt dem`TextSearchOptions` Eigentum der`TextFragmentAbsorber` Instanz. Dadurch wird sichergestellt, dass das reguläre Ausdrucksmuster während der Textsuche angewendet wird.

#### F: Wie füge ich dem gefundenen Text Hyperlinks hinzu?

 A: Nach der Identifizierung der Textfragmente mithilfe der`TextFragmentAbsorber` bietet das Tutorial eine Schleife, um diese Fragmente zu durchlaufen. Für jedes Textfragment zeigt das Tutorial, wie man die Textfarbe auf Blau setzt und einen Hyperlink erstellt, indem man`CreateWebLink` Verfahren.

#### F: Welche Schritte sind erforderlich, um die geänderte PDF-Datei mit Hyperlinks zu speichern?

 A: Nachdem Sie Hyperlinks zu den gewünschten Textfragmenten hinzugefügt haben, verwenden Sie die`PdfContentEditor` Klasse, um das geänderte Dokument zu speichern. Der Beispielcode des Tutorials zeigt, wie die bearbeitete PDF-Datei gespeichert, der Editor geschlossen und eine Erfolgsmeldung angezeigt wird.