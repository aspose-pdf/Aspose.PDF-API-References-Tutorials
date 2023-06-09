---
title: Alle Texte ersetzen
linktitle: Alle Texte ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET den gesamten Text in einem PDF-Dokument ersetzen.
type: docs
weight: 350
url: /de/net/programming-with-text/replace-text-all/
---

In diesem Tutorial erklären wir, wie Sie den gesamten Text in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zusammen mit dem notwendigen C#-Quellcode zur Verfügung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Aspose.PDF für .NET-Bibliothek installiert.
- Grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Legen Sie den Pfad zu dem Verzeichnis fest, in dem Sie die Eingabe-PDF-Datei haben. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir` Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das PDF-Dokument

 Laden Sie das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Schritt 3: Text suchen und ersetzen

 Ein ... kreieren`TextFragmentAbsorber`-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden. Akzeptieren Sie den Absorber für alle Seiten des PDF-Dokuments, um die Textfragmente zu extrahieren.

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

## Schritt 5: Speichern Sie das geänderte PDF

Speichern Sie das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Alles ersetzen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualisieren Sie Text und andere Eigenschaften
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

In diesem Tutorial haben Sie gelernt, wie Sie den gesamten Text in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF-Dokument laden, nach dem gewünschten Text suchen, ihn ersetzen und das geänderte PDF speichern.