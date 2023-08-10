---
title: Ersetzen Sie Text im regulären Ausdruck
linktitle: Ersetzen Sie den regulären Texton-Ausdruck
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text basierend auf einem regulären Ausdruck in einem PDF-Dokument ersetzen.
type: docs
weight: 360
url: /de/net/programming-with-text/replace-text-on-regular-expression/
---

In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text basierend auf einem regulären Ausdruck in einem PDF-Dokument ersetzen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zusammen mit dem notwendigen C#-Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.PDF für .NET-Bibliothek installiert.
- Grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Legen Sie den Pfad zu dem Verzeichnis fest, in dem Sie die Eingabe-PDF-Datei haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir`Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Schritt 3: Suchen und ersetzen Sie Text mithilfe eines regulären Ausdrucks

 Ein ... kreieren`TextFragmentAbsorber` Objekt und geben Sie das reguläre Ausdrucksmuster an, um alle Phrasen zu finden, die dem Muster entsprechen. Legen Sie die Textsuchoption fest, um die Verwendung regulärer Ausdrücke zu aktivieren.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Wie 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Schritt 4: Text ersetzen

Durchlaufen Sie die extrahierten Textfragmente und ersetzen Sie den Text nach Bedarf. Aktualisieren Sie den Text und andere Eigenschaften wie Schriftart, Schriftgröße, Vordergrundfarbe und Hintergrundfarbe.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Schritt 5: Speichern Sie das geänderte PDF

Speichern Sie das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Texton Regular Expression ersetzen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Phrasen zu finden, die dem regulären Ausdruck entsprechen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Wie 1999-2000
// Legen Sie die Textsuchoption fest, um die Verwendung regulärer Ausdrücke anzugeben
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Akzeptieren Sie den Absorber für eine einzelne Seite
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualisieren Sie Text und andere Eigenschaften
	textFragment.Text = "New Phrase";
	// Auf eine Instanz eines Objekts setzen.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie mithilfe der Aspose.PDF-Bibliothek für .NET Text basierend auf einem regulären Ausdruck in einem PDF-Dokument ersetzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF-Dokument laden, mithilfe eines regulären Ausdrucks nach Text suchen, ihn ersetzen und die geänderte PDF-Datei speichern.