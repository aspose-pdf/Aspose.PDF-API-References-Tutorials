---
title: Textseite ersetzen
linktitle: Textseite ersetzen
second_title: Aspose.PDF für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.PDF für .NET Text auf einer bestimmten Seite eines PDF-Dokuments ersetzen.
type: docs
weight: 370
url: /de/net/programming-with-text/replace-text-page/
---

In diesem Tutorial wird erklärt, wie Sie Aspose.PDF für .NET verwenden, um Text auf einer bestimmten Seite eines PDF-Dokuments zu ersetzen. Der bereitgestellte C#-Quellcode demonstriert den Prozess Schritt für Schritt.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

 Unbedingt austauschen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 4: Text suchen und ersetzen

 Ein ... kreieren`TextFragmentAbsorber` Objekt, um alle Instanzen des eingegebenen Suchbegriffs zu finden:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Ersetzen`"text"` durch den eigentlichen Text, den Sie suchen und ersetzen möchten.

## Schritt 5: Geben Sie die Zielseite an

 Akzeptieren Sie den Absorber für eine bestimmte Seite, indem Sie auf zugreifen`Pages` Sammlung der`pdfDocument` Objekt und Aufruf des`Accept` Methode:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Ersetzen`2` Geben Sie die Seitenzahl ein, auf der Sie den Text ersetzen möchten. Beachten Sie, dass die Seitenzahlen auf Null basieren`0` stellt die erste Seite dar.

## Schritt 6: Extrahierte Textfragmente abrufen

 Holen Sie sich die extrahierten Textfragmente mit`TextFragments` Eigentum der`TextFragmentAbsorber` Objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Schritt 7: Durchlaufen Sie die Textfragmente

Durchlaufen Sie die abgerufenen Textfragmente und aktualisieren Sie den Text und andere Eigenschaften nach Bedarf:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

 Ersetzen Sie im obigen Codeausschnitt`"New Phrase"`mit dem Ersatztext, den Sie verwenden möchten. Sie können auch andere Eigenschaften wie Schriftart, Schriftgröße, Vordergrundfarbe und Hintergrundfarbe anpassen.

## Schritt 8: Speichern Sie das geänderte PDF

 Speichern Sie das geänderte PDF-Dokument mit in einer neuen Datei`Save` Methode:

```csharp
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

 Unbedingt austauschen`"ReplaceTextPage_out.pdf"` mit dem gewünschten Ausgabedateinamen.

### Beispielquellcode für „Textseite ersetzen“ mit Aspose.PDF für .NET 
```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokument öffnen
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Erstellen Sie ein TextAbsorber-Objekt, um alle Instanzen der eingegebenen Suchphrase zu finden
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Akzeptieren Sie den Absorber für eine bestimmte Seite
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Holen Sie sich die extrahierten Textfragmente
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Durchlaufe die Fragmente
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Aktualisieren Sie Text und andere Eigenschaften
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
pdfDocument.Save(dataDir + "ReplaceTextPage_out.pdf");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.PDF für .NET Text auf einer bestimmten Seite eines PDF-Dokuments ersetzen. Dieses Tutorial bietet eine Schritt-für-Schritt-Anleitung vom Laden des Dokuments bis zum Speichern der geänderten Version. Sie können diesen Code jetzt in Ihre eigenen C#-Projekte integrieren, um die Textersetzung in PDF-Dateien zu automatisieren.