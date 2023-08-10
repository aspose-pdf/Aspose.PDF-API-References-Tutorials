---
title: Ersetzen Sie das erste Vorkommen
linktitle: Ersetzen Sie das erste Vorkommen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET das erste Vorkommen von Text in einem PDF-Dokument ersetzen.
type: docs
weight: 330
url: /de/net/programming-with-text/replace-first-occurrence/
---

In diesem Tutorial erklären wir, wie Sie das erste Vorkommen eines bestimmten Textes in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Wir gehen Schritt für Schritt durch den Prozess des Öffnens eines PDF-Dokuments, des Suchens des ersten Vorkommens des Suchbegriffs, des Ersetzens des Textes, des Aktualisierens von Eigenschaften und des Speicherns der geänderten PDF-Datei mithilfe des bereitgestellten C#-Quellcodes.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Die Aspose.PDF für .NET-Bibliothek installiert.
- Ein grundlegendes Verständnis der C#-Programmierung.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein

 Zuerst müssen Sie den Pfad zu dem Verzeichnis festlegen, in dem sich die Eingabe-PDF-Datei befindet. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im`dataDir`Variable mit dem Pfad zu Ihrer PDF-Datei.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Öffnen Sie das PDF-Dokument

 Als nächstes öffnen wir das PDF-Dokument mit`Document` Klasse aus der Aspose.PDF-Bibliothek.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Schritt 3: Finden Sie das erste Vorkommen des Suchbegriffs

 Wir erstellen ein`TextFragmentAbsorber` Objekt und akzeptieren Sie es für alle Seiten des PDF-Dokuments, um alle Vorkommen des Suchbegriffs zu finden.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Schritt 4: Ersetzen Sie den Text

Wenn der Suchbegriff im PDF-Dokument gefunden wird, rufen wir das erste Vorkommen des Textfragments ab und aktualisieren seine Eigenschaften mit dem neuen Text und der neuen Formatierung.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Schritt 5: Speichern Sie das geänderte PDF

Abschließend speichern wir das geänderte PDF-Dokument in der angegebenen Ausgabedatei.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Beispielquellcode für „Ersetzen des ersten Vorkommens“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
//Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für alle Seiten
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Ermitteln Sie das erste Vorkommen von Text und ersetzen Sie ihn
	TextFragment textFragment = textFragmentCollection[1];
	// Aktualisieren Sie Text und andere Eigenschaften
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Abschluss

In diesem Tutorial haben Sie gelernt, wie Sie das erste Vorkommen eines bestimmten Textes in einem PDF-Dokument mithilfe der Aspose.PDF-Bibliothek für .NET ersetzen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten C#-Code ausführen, können Sie ein PDF-Dokument öffnen, das erste Vorkommen eines Suchbegriffs finden, den Text ersetzen, Eigenschaften aktualisieren und das geänderte PDF speichern.