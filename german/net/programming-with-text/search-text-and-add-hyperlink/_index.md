---
title: Text durchsuchen und Hyperlink hinzufügen
linktitle: Text durchsuchen und Hyperlink hinzufügen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie in einer PDF-Datei nach Text suchen, Hyperlinks zum gefundenen Text hinzufügen und das geänderte Dokument mit Aspose.PDF für .NET speichern.
type: docs
weight: 450
url: /de/net/programming-with-text/search-text-and-add-hyperlink/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.PDF für .NET nach einem bestimmten Text in einem PDF-Dokument suchen, einen Hyperlink zum gefundenen Text hinzufügen und das geänderte Dokument speichern. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Schritt 3: Legen Sie den Pfad zum Dokumentverzeichnis fest

 Legen Sie den Pfad zu Ihrem Dokumentverzeichnis mit fest`dataDir` Variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Erstellen Sie einen TextFragmentAbsorber

 Ein ... kreieren`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen Suchbegriffs zu finden:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Ersetzen`"\\d{4}-\\d{4}"` mit Ihrem gewünschten Muster für reguläre Ausdrücke.

## Schritt 5: Aktivieren Sie die Suche nach regulären Ausdrücken

Aktivieren Sie die Suche nach regulären Ausdrücken, indem Sie Folgendes festlegen`TextSearchOptions` Eigenschaft des Absorbers:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Schritt 6: Öffnen und binden Sie das PDF-Dokument

 Ein ... kreieren`PdfContentEditor` Objekt und binden Sie es an die Quell-PDF-Datei:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Ersetzen`"SearchRegularExpressionPage.pdf"` mit dem tatsächlichen Namen Ihrer PDF-Datei.

## Schritt 7: Akzeptieren Sie die Seite für die Seite

Akzeptieren Sie den Absorber für die gewünschte Seite des Dokuments:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Ersetzen`1` mit der gewünschten Seitenzahl.

## Schritt 8: Fügen Sie Hyperlinks zum gefundenen Text hinzu

Durchlaufen Sie die abgerufenen Textfragmente und fügen Sie ihnen Hyperlinks hinzu:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Erstellen Sie ein Rechteck basierend auf der Position des Textfragments
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Fügen Sie dem Rechteck einen Weblink hinzu
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

 Unbedingt austauschen`"SearchTextAndAddHyperlink_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Text suchen und Hyperlink hinzufügen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Erstellen Sie ein Absorber-Objekt, um alle Vorkommen des eingegebenen Suchbegriffs zu finden
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Aktivieren Sie die Suche nach regulären Ausdrücken
absorber.TextSearchOptions = new TextSearchOptions(true);
// Dokument öffnen
PdfContentEditor editor = new PdfContentEditor();
//Binden Sie die PDF-Quelldatei
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Akzeptieren Sie den Absorber für die Seite
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Durchlaufe die Fragmente
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, blau, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET nach einem bestimmten Text in einem PDF-Dokument suchen, Hyperlinks zum gefundenen Text hinzufügen und das geänderte Dokument speichern. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Einrichten des Projekts bis zur Durchführung der erforderlichen Aktionen. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um Text zu bearbeiten und Hyperlinks in PDF-Dateien hinzuzufügen.